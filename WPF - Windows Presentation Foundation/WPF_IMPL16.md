## WPF - Grid Splitter Implementation

/* 
17. Implement custom window minimize,maimize and close button , also on left click window could be drag.
*/   

### MainWindow.xaml

```html
<Window x:Class="CodeWithHeeren.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:CodeWithHeeren"  Background="LightGray"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="400" WindowStyle="None" MouseLeftButtonDown="Window_MouseLeftButtonDown">
    <WindowChrome.WindowChrome>
        <WindowChrome GlassFrameThickness="0" CornerRadius="0" CaptionHeight="0" />
    </WindowChrome.WindowChrome>
    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition Height="40"/>
            <RowDefinition Height="40"/>
        </Grid.RowDefinitions>
        <StackPanel Orientation="Horizontal" HorizontalAlignment="Right">
            <Button x:Name="btnMinimize" Content="_" Width="40" Height="40" BorderBrush="Transparent" 
                    Background="Transparent" Click="btnMinimize_Click" Foreground= "white"/>
            <Button x:Name="btnMaximize" Content="🗖" Width="40" Height="40" BorderBrush="Transparent" 
                    Background="Transparent" Click="btnMaximize_Click" Foreground= "white"/>
            <Button x:Name="btnClose" Content="X" Width="40" Height="40" BorderBrush="Transparent" 
                    Background="Transparent" Click="btnClose_Click" Foreground= "white"/>
        </StackPanel>
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

        private void Window_MouseLeftButtonDown(object sender, System.Windows.Input.MouseButtonEventArgs e)
        {
            DragMove();
        }

        private void btnClose_Click(object sender, RoutedEventArgs e)
        {
            Close(); // only close specific window (Mostly Used.)
            //Application.Current.ShutDown(); // Close the entire application 
        }

        private void btnMaximize_Click(object sender, RoutedEventArgs e)
        {
            if (WindowState == WindowState.Maximized)
                WindowState = WindowState.Normal;
            else
                WindowState = WindowState.Maximized;
        }

        private void btnMinimize_Click(object sender, RoutedEventArgs e)
        {
            WindowState = WindowState.Minimized;
        }
    }
}
```
---