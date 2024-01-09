## WPF - Open new window on click on button.  

![image](https://github.com/codewithheeren/.Net/assets/87074236/70ab5e37-b38c-4275-9cea-8449bc34d545)

/* 
18.1 Open custom window with show and show dialog opetions. 
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
        <StackPanel >
            <Button x:Name="btnNormal" Content="Normal" Width="100" Height="40" Margin="5" Click="btnNormal_Click"/>
            <Button x:Name="btnModal" Content="Modal" Width="100" Height="40" Margin="5" Click="btnModal_Click" />
            <TextBox x:Name="txtInput" Width="200" Height="40" FontSize="20" Margin="5" />
        </StackPanel>
    </Grid>
</Window>

```
---
### MainWindow.xaml.cs

```cs
using System.Windows;
using CodeWithHeeren.view;
namespace CodeWithHeeren
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }

        private void btnNormal_Click(object sender, RoutedEventArgs e)
        {
            NormalWindow normalWindow = new NormalWindow(); 
            normalWindow.Show();
        }

        private void btnModal_Click(object sender, RoutedEventArgs e)
        {
            ModalWindow modalWindow = new ModalWindow();    
            modalWindow.ShowDialog(); 
        }
    }
}
```
---
