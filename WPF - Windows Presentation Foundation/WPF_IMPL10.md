## WPF - OpenFolderDialog (Folder Picker)

/* 
12. Generate folder browser dialog box on click of button
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
        Title="MainWindow" Height="450" Width="800">
    <Grid>
        <Button Name="btn" Content="Open File" VerticalAlignment="Center"
                HorizontalAlignment="Center" Width="90" Height="30" Click="btn_Click"/>
    </Grid>
</Window>
```
---
### MainWindow.xaml.cs
```cs
using System.Windows;
using WinForms = System.Windows.Forms;

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
            //Folder Browser Dialog is not in wpf its in win forms.
            //To enable win forms you need rightclick on project -> properties -> click on enable window forms and make sure you will also save this.
            //Now if you open project on file explorer and open csproj file in notpad++ you will add this line - <UseWindowsForms>true</UseWindowsForms> 
            WinForms.FolderBrowserDialog dialog = new WinForms.FolderBrowserDialog(); // using this user can only browse folder not files.
            dialog.InitialDirectory = "C:\\D";
            WinForms.DialogResult result = dialog.ShowDialog();
            if (result == WinForms.DialogResult.OK)
            {
                string folder = dialog.SelectedPath; // check output using debug breakpoint
            }
            else { 
            }
            //MessageBox.Show();  // This is also same for wpf and windows form
        }
    }
}

```
---
### App.xaml.cs
```cs
using Application = System.Windows.Application;

namespace CodeWithHeeren
{
    public partial class App : Application
    {
    }

}
```
---