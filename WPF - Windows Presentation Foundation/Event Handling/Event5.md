## WPF - Custom Event

### 4. Create an simple implementaion of data binding. for text block , text comes from MainWindow class property..

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
        <TextBlock x:Name="textBlock" Text="{Binding ElementName = textbox, Path=Text}"  />
        <TextBox x:Name="textbox" Width="200" Height="30" FontSize="18"  VerticalAlignment="Center" HorizontalAlignment="Center" />
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
    }
}
```
---
