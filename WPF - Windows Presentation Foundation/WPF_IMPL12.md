## WPF - Grid Splitter Implementation

/* 
14. Implement horizontal and vertical grid splitter.
*/   

### Horizontal Splitter
### MainWindow.xaml
```html
<Window x:Class="CodeWithHeeren.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:CodeWithHeeren"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="400">
    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition Height="50"/>
            <RowDefinition />
            <RowDefinition Height="5" />
            <RowDefinition Height="10"/>
        </Grid.RowDefinitions>
        <Rectangle Fill="Red" />
        <Rectangle Grid.Row="1" Fill="green" />
        <GridSplitter Grid.Row="2" HorizontalAlignment="Stretch"/>
        <Rectangle Grid.Row="3" Fill="blue" />
    </Grid>
</Window>

<!--
   Use to split grid at some row or some column.
   After Implementing we are able to stractch blue box. 
-->

```
---

### Combination of Vertical and horizontal Splitter 


### MainWindow.xaml
```html
<Window x:Class="CodeWithHeeren.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:CodeWithHeeren"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="400">
    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition Height="50"/>
            <RowDefinition />
            <RowDefinition Height="5" />
            <RowDefinition Height="30"/>
        </Grid.RowDefinitions>
        <Rectangle Fill="Red" />
        <Grid Grid.Row="1">
            <Grid.ColumnDefinitions>
                <ColumnDefinition />
                <ColumnDefinition Width="5"/>
                <ColumnDefinition />
                <ColumnDefinition Width="5"/>
                <ColumnDefinition />
            </Grid.ColumnDefinitions>
            <Rectangle Fill="Yellow"/>
            <GridSplitter Grid.Column="1" HorizontalAlignment="Stretch"/>
            <Rectangle Grid.Column="2" Fill="Gray"/>
            <GridSplitter Grid.Column="3" HorizontalAlignment="Stretch"/>
            <Rectangle Grid.Column="4" Fill="Green"/>
        </Grid>
        <GridSplitter Grid.Row="2" HorizontalAlignment="Stretch"/>
        <Rectangle Grid.Row="3" Fill="blue" />
    </Grid>
</Window>
```
---