## WPF - Data Binding

### 1. Create an simple implementaion of data binding. for text block , text comes from MainWindow class property.

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
        <TextBlock x:Name="textBlock" Text="{Binding MyProperty}"  VerticalAlignment="Center" HorizontalAlignment="Center" />
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
            DataContext = this;
            MyProperty = "Initial Value";
        }

        public string MyProperty { get; set; }
     
    }
}
```
---
