## WPF - OpenFileDialog (File Picker)

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
        Title="MainWindow" Height="250" Width="750">
    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition/>
            <RowDefinition/>
        </Grid.RowDefinitions>
        <Button Name="btn" Content="Open File" VerticalAlignment="Center"
                HorizontalAlignment="Center" Width="90" Height="30" Click="btn_Click"/>
        <TextBlock Name="tbInfo" Grid.Row="1" VerticalAlignment="Center" FontSize="16"
                   HorizontalAlignment="Center" />
    </Grid>
</Window>
```
---
### MainWindow.xaml.cs
```cs
using Microsoft.Win32;
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
            OpenFileDialog fileDialog = new OpenFileDialog();
            fileDialog.Filter = "C# files only | *.cs";
            fileDialog.Title = "Please pick a CS file...";
            fileDialog.Multiselect = false;
            bool? success = fileDialog.ShowDialog();
            if (success == true)
            {
                //when multiselect is not true
                string filePath = fileDialog.FileName;
                tbInfo.Text = filePath;
                //when multiselect is true
                //string[] paths = fileDialog.FileNames;
                //string[] fileNames = fileDialog.SafeFileNames; //verify that using break point 
            }
            else
            {
                // File didn't selected.
            }
        }
    }
}

```
---
