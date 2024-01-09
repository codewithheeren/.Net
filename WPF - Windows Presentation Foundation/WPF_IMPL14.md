## WPF - Grid Splitter Implementation

/* 
15.2 Implement veritcal Expender to see further information .
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
        <Grid.ColumnDefinitions>
            <ColumnDefinition />
            <ColumnDefinition Width="auto" />
        </Grid.ColumnDefinitions>
        <StackPanel>
            <TextBlock Text="Console" />
            <Expander Header="More Details">
                <TextBlock Text="Bug 203- I am use to expend and see further information" FontSize="12" />
            </Expander>
            <Button x:Name="dtlBtn" Background="LightBlue" Content="Show Details" Width="90" Click="dtlBtn_Click"/>
        </StackPanel>
        <Expander x:Name="expendDtl" Background="Gray" Grid.Column="1" ExpandDirection="Left" BorderThickness="0">
            <Rectangle Fill="Gray" Width="125"/>
        </Expander>
    </Grid>
</Window>

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

        private void dtlBtn_Click(object sender, RoutedEventArgs e)
        {
            expendDtl.IsExpanded = !expendDtl.IsExpanded;
        }
    }
}
```
---