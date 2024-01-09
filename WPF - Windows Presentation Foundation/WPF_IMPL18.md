## WPF - Open new window on click on button.  

![image](https://github.com/codewithheeren/.Net/assets/87074236/70ab5e37-b38c-4275-9cea-8449bc34d545)

/* 
18.2 Open custom window with show and show dialog opetions. 
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
            ModalWindow modalWindow = new ModalWindow(this);
            Opacity = 0.4;
            modalWindow.ShowDialog();
            Opacity = 1;
            if (modalWindow.success) { 
            txtInput.Text = modalWindow.input;
            }
        }
    }
}
```
---

### ModalWindow.xaml
```html
<Window x:Class="CodeWithHeeren.view.ModalWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:CodeWithHeeren.view"
        mc:Ignorable="d" WindowStyle="None" WindowStartupLocation="CenterOwner" 
        Title="ModalWindow" Height="150" Width="250">
    <Grid>
        <StackPanel VerticalAlignment="Center">
            <TextBox x:Name="txtInput" Width="200" Height="40" FontSize="20" Margin="5" TextChanged="txtInput_TextChanged"/>
            <StackPanel Orientation="Horizontal" HorizontalAlignment="Center">
                <Button x:Name="okBtn" Content="OK" Width="100" Height="40" Margin="5" Click="okBtn_Click"
                        IsEnabled="False"/>
                <Button x:Name="cancelBtn" Content="Cancel" Width="100" Height="40" Margin="5" Click="cancelBtn_Click"  />
            </StackPanel>
        </StackPanel>
    </Grid>
</Window>
```
---
### ModalWindow.xaml.cs

```cs
using System.Windows;
using System.Windows.Controls;

namespace CodeWithHeeren.view
{
    public partial class ModalWindow : Window
    {
        public bool success { get; set; }
        public string input { get; set; }
        public ModalWindow(Window parentWindow)
        {
            Owner = parentWindow;
            InitializeComponent();
        }

        private void okBtn_Click(object sender, RoutedEventArgs e)
        {
            success = true;
            input = txtInput.Text;
            Close();
        }

        private void cancelBtn_Click(object sender, RoutedEventArgs e)
        {
            Close();

        }

        private void txtInput_TextChanged(object sender, TextChangedEventArgs e)
        {
            if (!string.IsNullOrEmpty(txtInput.Text))
                okBtn.IsEnabled = true;
            else
                okBtn.IsEnabled = false;
        }
    }
}


```
---
