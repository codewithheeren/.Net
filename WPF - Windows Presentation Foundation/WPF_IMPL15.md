## WPF - Scroll Bar Implementation

/* 
16. Add scroll bar when When frame will be resize to smaller size.
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
        Title="MainWindow" Height="450" Width="400">
    <Grid>
        <ScrollViewer VerticalScrollBarVisibility="Auto"
                      HorizontalScrollBarVisibility="Disabled">
        <StackPanel>
            <TextBox Height="30" Width="200" Margin="5"/>
            <TextBox Height="30" Width="200" Margin="5"/>
            <TextBox Height="30" Width="200" Margin="5"/>
            <TextBox Height="30" Width="200" Margin="5"/>
            <TextBox Height="30" Width="200" Margin="5"/>
        </StackPanel>
        </ScrollViewer>
    </Grid>
</Window>

<!--
  Scroll Viewer will show scroll when window will resize to smaller size 
  In order to access UI components.
-->

```
---
