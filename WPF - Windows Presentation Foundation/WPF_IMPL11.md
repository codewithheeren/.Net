## WPF - OpenFileDialog (File Picker)

/* 
13. Implement Stack Panel , Nested stack panel with different orientations.
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
        <Grid.RowDefinitions>
            <RowDefinition Height="75"/>
            <RowDefinition />
        </Grid.RowDefinitions>
        <StackPanel Grid.Row="0" Orientation="Horizontal" HorizontalAlignment="Center">
            <Button Height="40" Width="75" Margin="2" Content="A" /> 
            <Button Height="40" Width="75" Margin="2" Content="B" />
            <Button Height="40" Width="75" Margin="2" Content="C" />
        </StackPanel>
        <StackPanel Grid.Row="1" Margin="5">
            <StackPanel Orientation="Horizontal" HorizontalAlignment="Center">
                <Label Content="Enter Value:" FontSize="16"/>
                <TextBox Width="150" />
                <Button Content="Start" Width="50"/>
            </StackPanel>
            <StackPanel Orientation="Horizontal" HorizontalAlignment="Center">
                <Label Content="Enter Value:" FontSize="16"/>
                <TextBox Width="150" />
                <Button Content="Start" Width="50"/>
            </StackPanel>
            <TextBox Width="170" Height="30" Margin="2" />
            <ComboBox Width="170" Height="30" Margin="2" />
            <TextBox Width="170" Height="30" Margin="2" />
            <TextBox Width="170" Height="30" Margin="2" />
            <TextBox Width="170" Height="30" Margin="2" />
            <TextBox Width="170" Height="30" Margin="2" />
        </StackPanel>
    </Grid>
</Window>

<!-- Line14 - If one value of margin define then that means that is the margin for all 4 sides.-->

```
---
### MainWindow.xaml.cs
```cs
using System.Windows;

namespace CodeWithHeeren
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }
    }
}

```
---
