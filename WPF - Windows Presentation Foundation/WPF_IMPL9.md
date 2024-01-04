## WPF - Event Handling

/* 
10 Generate message box on click of button
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
        Title="MainWindow" Height="250" Width="300">
    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition/>
            <RowDefinition/>
        </Grid.RowDefinitions>
        <Button Name="btn" Content="Send Message" VerticalAlignment="Center"
                HorizontalAlignment="Center" Width="90" Height="30" Click="btn_Click"/>
        <TextBlock Name="tbInfo" Grid.Row="1" VerticalAlignment="Center" FontSize="16"
                   HorizontalAlignment="Center" />
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

        private void btn_Click(object sender, RoutedEventArgs e)
        {
            //MessageBox.Show("Show your message here.",,,,,);
            //MessageBox.Show("File doesn't exist on give location.", "Error!", MessageBoxButton.OK, MessageBoxImage.Error);
            MessageBoxResult result = MessageBox.Show("Do you agree ?", "Acceptance", MessageBoxButton.YesNo, MessageBoxImage.Question);
            if (result == MessageBoxResult.Yes)
                tbInfo.Text = "Agreed";
            else
                tbInfo.Text = "Not Agreed";
        }
    }
}

```
---
