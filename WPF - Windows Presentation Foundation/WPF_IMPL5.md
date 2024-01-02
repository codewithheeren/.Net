## WPF - Grid Layout

/* 
7. Create a wpf with menu bar (File(inside file menu -> Exit), Edit) , just below the menu within header create button and textbox.
*/ 
### MainWindow.xaml
```html
<Window x:Class="CodeWithHeeren.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:CodeWithHeeren"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition Height="60"/>
            <RowDefinition />
            <RowDefinition Height="20"/>
        </Grid.RowDefinitions>
        <!-- Grid.Row = 0 or column = 0 is always optional-->
        <Grid Grid.Row="0"> 
            <Grid.RowDefinitions>
                <RowDefinition Height="30"/>
                <RowDefinition Height="30"/>
            </Grid.RowDefinitions>
            <Menu Grid.Row="0">
                <MenuItem  Header="File" FontSize="18">
                    <MenuItem Header="Exit" />
                </MenuItem>
                <MenuItem  Header="Edit" FontSize="18"/>
            </Menu>
            <Grid Grid.Row="1">
                <Grid.ColumnDefinitions>
                    <ColumnDefinition Width="Auto"/>
                    <ColumnDefinition Width="Auto"/>
                </Grid.ColumnDefinitions>
                <Button Width="50" Margin="5" Content="Search"/>
                <TextBox Width="100" Margin="5" Grid.Column="1"/>
            </Grid>
        </Grid>
    </Grid>
</Window>

```
---