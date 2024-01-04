## WPF - Custom Control 

/* 
8.4 Add events to the form such as clear button should work, text box should be editable.
*/   

### ReusableTextBox.xaml
```html
<UserControl x:Class="CodeWithHeeren.View.CustomControls.ReusableTextBox"
             xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
             xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
             xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" 
             xmlns:d="http://schemas.microsoft.com/expression/blend/2008" 
             xmlns:local="clr-namespace:CodeWithHeeren.View.CustomControls"
             mc:Ignorable="d" 
             d:DesignHeight="40" d:DesignWidth="250">
    <Grid Background="white">
        <TextBox x:Name="txtInput"  VerticalAlignment="Center" FontSize="18" FontWeight="Light" 
                 HorizontalAlignment="Left" Width="250" Background="Transparent" TextChanged="txtInput_TextChanged"  />
        <TextBlock x:Name="tbPlaceholder" Text="{Binding Placehoder}" FontSize="14" FontWeight="Light" Height="16"
                   VerticalAlignment="Center" Foreground="LightGray" Margin="5,0,0,0" 
                   Panel.ZIndex="-1"></TextBlock>
        <Button x:Name="btnClear" Width="30" HorizontalAlignment="Right" Content="X" FontSize="20"
                FontWeight="Medium" Background="Transparent" Foreground="LightGray" 
                BorderThickness="0" Click="btnClear_Click"/>
    </Grid>
</UserControl>

```
---
### ReusableTextBox.xaml.cs
```cs
using System.Windows;
using System.Windows.Controls;

namespace CodeWithHeeren.View.CustomControls
{
    public partial class ReusableTextBox : UserControl
    {
        public ReusableTextBox()
        {
            InitializeComponent();
        }

        private string placeholder;

        public string Placeholder
        {
            get { return placeholder; }
            set
            {
                placeholder = value;
                // But we should not use this approach , we should use only onPropertyChanged()
                tbPlaceholder.Text = placeholder;
            }
        }

        private void btnClear_Click(object sender, RoutedEventArgs e)
        {
            txtInput.Clear();
            txtInput.Focus();
        }

        private void txtInput_TextChanged(object sender, TextChangedEventArgs e)
        {
            if (string.IsNullOrEmpty(txtInput.Text))
                tbPlaceholder.Visibility = Visibility.Visible;
            else
                tbPlaceholder.Visibility = Visibility.Hidden;
        }
    }
}

```
---
### MainWindow.xaml
```html
<Window x:Class="CodeWithHeeren.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:CodeWithHeeren"
        xmlns:userControls="clr-namespace:CodeWithHeeren.View.CustomControls"
        mc:Ignorable="d"
               Title="MainWindow" Height="300" Width="300">
    <Grid>
        <Grid.RowDefinitions >
            <RowDefinition />
            <RowDefinition />
            <RowDefinition />
            <RowDefinition />
        </Grid.RowDefinitions>
        <userControls:ReusableTextBox Grid.Row="0" Height="30" Width="250" HorizontalAlignment="Center" VerticalAlignment="Center" Placeholder="First Name"/>
        <userControls:ReusableTextBox Grid.Row="1" Height="30" Width="250" HorizontalAlignment="Center" VerticalAlignment="Center" Placeholder="Last Name"/>
        <userControls:ReusableTextBox Grid.Row="2" Height="30" Width="250" HorizontalAlignment="Center" VerticalAlignment="Center" Placeholder="Contact"/>
        <userControls:ReusableTextBox Grid.Row="3" Height="30" Width="250" HorizontalAlignment="Center" VerticalAlignment="Center" Placeholder="Address"/>
    </Grid>
</Window>

```
---
