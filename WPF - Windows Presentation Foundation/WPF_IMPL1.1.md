## WPF - C#

### MainWindow.xaml.cs

```cs
/* 
1. Write 'Hello World' label on window form.
-- Change the label hello world to hi world on loading of form.
-- show the label in center of the page.
*/ 
using System.Windows;

namespace WPF1
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            Loaded += MainWindow_Loaded;
        }
        private void MainWindow_Loaded(object sender, RoutedEventArgs e)
        {
            HelloText.Text = "Hi World";
        }
    }
}

```
---
### MainWindow.xaml
```html
<Window x:Class="WPF1.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:WPF1"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <Grid>
        <TextBlock x:Name="HelloText" Text="Hello World" FontSize="18" FontWeight="Bold"  VerticalAlignment="Center" HorizontalAlignment="Center"/>
    </Grid>
</Window>

```
---