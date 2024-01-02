## WPF - Grid Layout

/* 
6. In extention of task5 second row (content pane) divide that in to 3 columns with different colors and their size proposional should be as 40% , 40%, 20% each resepectivly.
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
            <RowDefinition/>
            <RowDefinition Height="30"/>
        </Grid.RowDefinitions>
        <!-- Menu Bar -->
        <Rectangle Grid.Row="0" Fill="red" />
        <!-- Content Pane -->
        <Grid Grid.Row="1">
            <Grid.ColumnDefinitions>
                <ColumnDefinition Width="40*"/>
                <ColumnDefinition Width="40*"/>
                <ColumnDefinition Width="20*"/>
            </Grid.ColumnDefinitions>
            
            <Rectangle Grid.Column="0" Fill="Gray" />
            <Rectangle Grid.Column="1" Fill="black" />
            <Rectangle Grid.Column="2" Fill="MintCream" />
        </Grid>
        <!-- Footer -->
        <Rectangle Grid.Row="2" Fill="Orange" />
    </Grid>
</Window>

```
---