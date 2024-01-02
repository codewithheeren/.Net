## WPF - Grid Layout

/* 
5. Create a form with three rows of different color assuming that 1st row will be header and last row will be footer and then fix the size of first and last row in responsive design.
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
        <Rectangle Grid.Row="0" Fill="red" />
        <Rectangle Grid.Row="1" Fill="yellow" />
        <Rectangle Grid.Row="2" Fill="Orange" />
    </Grid>
</Window>
```
---