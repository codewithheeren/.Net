## WPF - Grid Splitter Implementation

/* 
15.1 Implement Expender to see further information .
*/   


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
        <Grid.ColumnDefinitions>
            <ColumnDefinition />
            <ColumnDefinition Width="150" />
        </Grid.ColumnDefinitions>
        <StackPanel>
            <TextBlock Text="Console" />
            <Expander Header="More Details">
                <TextBlock Text="Bug 203- I am use to expend and see further information" FontSize="12" />
            </Expander>
        </StackPanel>
        <Rectangle Grid.Column="1" Fill="LightGray" />
    </Grid>
</Window>

<!--
  Simple implementation of Expender 
-->

```
---
