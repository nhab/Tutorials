```
:is a XML-based declarative markup language for creating a UI and code behind of it.
:concepts
    - XAML  										 : Declarative UI definition through XAML
    - 'Property Element' syntax : ( Properties can be as  Elements) 
        -Properties are normally written inline as known from XML.
                like 'content' property in this button: <Button Content="OK" />.
            but
            property element syntax allows us to extract the property as an own child element.
            :X
                <Button>
                    <Button.Content>
                        <Image Source="Images/OK.png" Width="50" Height="50" />
                    </Button.Content>
                </Button>

    - Implicit Type convertors   : ( strings to the proper type silently)
        :They convert strings to the proper type silently in the background.
        :x
            <!--
            When you declare a BorderBrush,
            The implicit BrushConverter makes a System.Windows.Media.Brushes.Blue out of the string "Blue"
            -->
            <Border BorderBrush="Blue" BorderThickness="0,10">
            </Border>

    - Markup "Extensions"  ( {} )
        : are dynamic placeholders for attribute values in XAML.
        -they are surrouded by curly braces ( {} )
            :X
                Background="{StaticResource NormalBackgroundBrush}"

        -They resolve the value of a property at runtime
        -WPF has some built-in markup extensions, 
            but you can write your own,
            by deriving from MarkupExtension.
        
        :{built-in markup extensions:
            Binding
                :the way you should glue together your UI with your business object (any data source).
                :To bind the values of two properties together.

                :X
                        a label whose Content is bound to the "Text" of the textbox:
                    <TextBox x:Name="textBox"/>
                    <Label Content="{Binding Text, ElementName=textBox}"/>
                :{

                    Data Binding 
                        {Binding} 
                            Binds the current DataContext
                    Data Binding
                        :connection between the application UI and the business logic.

                        :{Typically, Binding requires four components
                            Target Object
                            Source Object
                            Target Property (Should be a DP, That supports default bindings)
                            Path Value
                        :X
                            <TextBox Name="text1" Text="{Binding MyText}"/>
                            which MyText is
                            public string MyText  
                            {  
                                    get { return (string)GetValue(MyTextProperty); }  
                                    set { SetValue(MyTextProperty, value); }  
                            }  
                    
                            // Using a DependencyProperty as the backing store for MyText.  This enables animation, styling, binding, etc...  
                            public static readonly DependencyProperty MyTextProperty =  
                                    DependencyProperty.Register("MyText", typeof(string), typeof(TextBox), new PropertyMetadata("Tamil Valga! Tamil Valarga!!"));

                    <XmlDataProvider x:Key="name"	Source="filePath" /> 
                                    Added to resources to allow	xml data binding

                    Element Binding
                            :X
                                <TextBox  Name="text1" Text="Tamil Valga! Tamil Valarga!!"/>  
                                <TextBlock Text="{Binding Text, ElementName=text1}" Margin="134,169,135,117"/>

                    {Binding ElementName= elementName	, Path =	propertyName } 
                        Binds to the property of the given element

                    {Binding	propertyName}  
                        Binds the property of the current DataContext

                    Resource Binding
                            {Binding Source={StaticResource resName}, XPath=x	pathValue } 
                                Binds to a an XML node using XPath

                        {Binding Source={StaticResource	resName	}}"
                            Binds to a static resource	such as  a string
                                
                    relative binding
                        :x
                            <Button Content="{Binding RelativeSource={x:Static RelativeSource.Self}, Path=ActualWidth}"/>
                            shows a number inside button
                
                            {Binding RelativeSource={RelativeSource AncestorType ={x:Type	typeName	}}, Path= propertyName	} 
                                Looks up the visual tree to find an ancestor of the given type. Specify AncestorLevel 
                                as an integer to set the level 

                            {Binding RelativeSource={x:Static RelativeSource.Self}, 	Path= propertyName	} 
                                Binds to the current	elements given property.
                    Template Binding
                            :To bind a property of a control template to a dependency property of the control
                            Binds to the template parents given property	inside a ControlTemplate
                            {TemplateBinding	propertyName}
                            
                    


                    IsSynchronizedWithCurrentItem	="True"   
                        Synchronizes elements bound to same data source
                        
            StaticResource
                One time lookup of a resource entry
            DynamicResource
                Auto updating lookup of a resource entry

            x:Static
                Resolve the value of a static property.
            x:Null
                Return null
        Namespaces
            At the beginning of every XAML file you need to include two namespaces:
                1. http://schemas.microsoft.com/winfx/2006/xaml/presentation   :mapped to all wpf controls in System.Windows.Controls.
                2. http://schemas.microsoft.com/winfx/2006/xaml 					:mapped to System.Windows.Markup that defines the XAML keywords.

            The mapping between an XML namespace and a CLR namespace is done by the XmlnsDefinition attribute at assembly level.
            You can also directly include a CLR namespace in XAML by using the clr-namespace: prefix.
                <Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
                xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

                </Window>

    -Templates and Styles 
        :the way you define the behaviour and appearence of your application.
        :parts{
            -styles
                :like html style, they are used to repeat the same color,font,dimention ,.. for multiple elements
                :X
                    <Window x:Class="WpfTutorialSamples.Styles.SimpleStyleSample"
                            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
                            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
                            Title="SimpleStyleSample" Height="200" Width="250">
                        <StackPanel Margin="10">
                            <StackPanel.Resources>
                                    <Style TargetType="TextBlock">
                                        <Setter Property="Foreground" Value="Gray" />
                                        <Setter Property="FontSize" Value="24" />
                                    </Style>
                            </StackPanel.Resources>
                            <TextBlock>Header 1</TextBlock>
                            <TextBlock>Header 2</TextBlock>
                            <TextBlock Foreground="Blue">Header 3</TextBlock>
                        </StackPanel>
                    </Window>
            -templates
        :OPTS{
            -Control Template
                    :visual appearance of a control
            -Data Template
                :defines and specifies the appearance and structure of a collection of data.
    -graphics
        Brushes
            :Brushes and pens are objects used to draw and fill graphics objects
            :opts{
                SolidColorBrush
                    represents the solid color brush in XAML. The Color attribute of the tag represents the color used in the brush.
                    :X
                        For example, the following code creates a solid color brush with blue color.
                        <SolidColorBrush Color="Blue" />

                LinearGradientBrush
                RadialGradientBrush
                DrawingBrush
                Visual Brush
                ImageBrush
    -Animation overview
        https://msdn.microsoft.com/en-us/library/ms752312(v=vs.110).aspx
        -Storyboard
            A Storyboard is a type of container timeline that provides targeting information for the timelines it contains. A Storyboard can contain any type of Timeline, including other container timelines and animations. Storyboard objects enable you to combine timelines that affect a variety of objects and properties into a single timeline tree, making it easy to organize and control complex timing behaviors. For example, suppose you want a button that does these three things.
                Grow and change color when the user selects the button.
                Shrink away and then grow back to its original size when clicked.
                Shrink and fade to 50 percent opacity when it becomes disabled.
            In this case, you have multiple sets of animations that apply to the same object, and you want to play at different times, dependent on the state of the button. Storyboard objects enable you to organize animations and apply them in groups to one or more objects.

    -WPF Content Model
        controls and component that can be used in using(resource)
        :{
            ContentControl
                A single arbitrary object.
                :{
                        Button
                        ButtonBase
                        CheckBox
                        ComboBoxItem
                        ContentControl
                        Frame
                        GridViewColumnHeader
                        GroupItem
                        Label
                        ListBoxItem
                        ListViewItem
                        NavigationWindow
                        RadioButton
                        RepeatButton
                        ScrollViewer
                        StatusBarItem
                        ToggleButton
                        ToolTip
                        UserControl
                        Window
            HeaderedContentControl
                A header and a single item, both of which are arbitrary objects.
                :{
                        Expander
                        GroupBox
                        TabItem
            ItemsControl
                A collection of arbitrary objects.
                :{
                        Menu
                        MenuBase
                        ContextMenu
                        ComboBox
                        ItemsControl
                        ListBox
                        ListView
                        TabControl
                        TreeView
                        Selector
                        StatusBar
            HeaderedItemsControl
                A header and a collection of items, all of which are arbitrary objects.
                :{
                        MenuItem
                        ToolBar
                        TreeViewItem
            panels
                :Classes That Contain a Collection of UIElement Objects
                :{
                        Canvas
                        DockPanel
                        Grid
                        TabPanel
                        ToolBarOverflowPanel
                        ToolBarPanel
                        UniformGrid
                        StackPanel
                        VirtualizingPanel
                        VirtualizingStackPanel
                        WrapPanel
            Decorators
                :Classes That Affect the Appearance of a UIElement
                :{
                        AdornerDecorator
                        Border
                        BulletDecorator
                        ButtonChrome
                        ClassicBorderDecorator
                        InkPresenter
                        ListBoxChrome
                        SystemDropShadowChrome
                        Viewbox
            Adorner
                :Classes That Provide Visual Feedback About a UIElement
            textboxes
                :Classes That Enable Users to Enter Text
                :{
                    TextBox
                    RichTextBox
                    PasswordBox
            Formated Text
                :Classes That Display formatted Text or format the text
                :{
                    FlowDocumentReader
                    FlowDocumentPageViewer
                    FlowDocumentScrollViewer
                    TextBlock
                    TextElement
    -Layout
        :why
            Layout of controls is critical to an applications usability. Arranging controls based on fixed pixel coordinates may work for an limited enviroment, but as soon as you want to use it on different screen resolutions or with different font sizes it will fail. WPF provides a rich set built-in layout panels that help you to avoid the common pitfalls.
        :Parts{
            Grid Panel
                :
                    The grid is a layout panel that arranges its child controls in a tabular structure of rows and columns.
                    Its functionality is similar to the HTML table but more flexible. 
                    A cell can contain multiple controls, they can span over multiple cells and even overlap themselves.
                    The resize behaviour of the controls is defined by the HorizontalAlignment and VerticalAlignment properties who define the anchors. 
                    The distance between the anchor and the grid line is specified by the margin of the control
                :procs:
                    Define Rows and Columns
                        -The grid has one row and column by default.
                        - To create additional rows and columns, 
                            you have to add RowDefinition items to the RowDefinitions collection 
                            and ColumnDefinition items to the ColumnDefinitions collection.
                        :X
                            <Grid>
                                <Grid.RowDefinitions>
                                    <RowDefinition Height="Auto" />
                                    <RowDefinition Height="Auto" />
                                    <RowDefinition Height="*" />
                                    <RowDefinition Height="28" />
                                </Grid.RowDefinitions>

                                <Grid.ColumnDefinitions>
                                    <ColumnDefinition Width="Auto" />
                                    <ColumnDefinition Width="200" />
                                </Grid.ColumnDefinitions>

                                <Label Grid.Row="0" Grid.Column="0" Content="Name:"/>
                                <Label Grid.Row="1" Grid.Column="0" Content="E-Mail:"/>
                                <Label Grid.Row="2" Grid.Column="0" Content="Comment:"/>
                                <TextBox Grid.Column="1" Grid.Row="0" Margin="3" />
                                <TextBox Grid.Column="1" Grid.Row="1" Margin="3" />
                                <TextBox Grid.Column="1" Grid.Row="2" Margin="3" />
                                <Button Grid.Column="1" Grid.Row="3" HorizontalAlignment="Right" 
                                            MinWidth="80" Margin="3" Content="Send"  />
                            </Grid>
            StackPanel
            Dock Panel
            Canvas Panel
            Wrap Panel
            ViewBox
            Custom Layout Panel
        :procs
            Scrolling
                When the content is too big to fit the available size, you can wrap it into a ScrollViewer.
                The ScrollViewer uses two scroll bars to choose the visible area.

                The visibility of the scrollbars can be controlled by the vertical and horizontal ScrollbarVisibility properties.

                <ScrollViewer>
                    <StackPanel>
                        <Button Content="First Item" />
                        <Button Content="Second Item" />
                        <Button Content="Third Item" />
                    </StackPanel>
                </ScrollViewer>
            border control
                :The Border control is a Decorator control that you may use to draw a border, a background, or even both, around another element.
                :X:
                    <Window x:Class="WpfTutorialSamples.Misc_controls.BorderSample"
                    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
                    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
                    Title="BorderSample" Height="170" Width="200">
                <Grid Margin="10">
                                <Border Background="GhostWhite" BorderBrush="Gainsboro" BorderThickness="1">
                                            <StackPanel Margin="10">
                                                    <Button>Button 1</Button>
                                                    <Button Margin="0,10">Button 2</Button>
                                                    <Button>Button 3</Button>
                                            </StackPanel>
                                </Border>
                    </Grid>
            </Window>
```