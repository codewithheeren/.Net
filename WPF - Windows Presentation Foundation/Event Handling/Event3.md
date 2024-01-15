## WPF - Custom Event

### 3. Create a custom event class , where on click on button a proprty of cutom event class change and message popup show saying - poperty get changed.

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
        <Button x:Name="Btn1"  Width="90" Height="30" Content="Click Me" Click="Btn1_Click" />
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

        private void Btn1_Click(object sender, RoutedEventArgs e)
        {
            CustomEvent customEvent = new CustomEvent();
            customEvent.OnPropertyChanged += OnPropertyChanged;
            customEvent.Name = "CodeWithHeeren";
        }

        private void OnPropertyChanged(object? sender, EventArgs e)
        {
            MessageBox.Show("Property get changed.");
        }
    }
}
```
---
### CustomEvent.cs

```cs
namespace CodeWithHeeren
{
    internal class CustomEvent
    {
        public event EventHandler OnPropertyChanged;
        private string name;
        public string Name {
            set {
                name = value;
                OnPropertyChanged(this, new EventArgs());
            }          
            get { 
               
               return name;
            } 
        }
    }
}

```
---