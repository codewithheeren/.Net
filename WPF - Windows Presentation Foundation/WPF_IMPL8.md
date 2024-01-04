## WPF - Event Handling

/* 
9 Create following design where on typing in text field same value should show in textblock and on clicking on button a value will set to property but that will not reflect on text field.
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
        Title="MainWindow" Height="250" Width="250">
    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition/>
            <RowDefinition/>
            <RowDefinition/>
        </Grid.RowDefinitions>
        <TextBox Text="{Binding TextBound, UpdateSourceTrigger=PropertyChanged, Mode=OneWayToSource}" VerticalAlignment="Center" 
                 HorizontalAlignment="Center" Width="200" Height="30"/>
        <Button Name="btn" Grid.Row="1" Content="Set Value" Width="70" Height="20" Click="Button_Click" />
        <TextBlock Grid.Row="2" FontSize="16" Text="{Binding TextBound}"
                   VerticalAlignment="Center" HorizontalAlignment="Center" />

    </Grid>
</Window>

```
---
### MainWindow.xaml.cs
```cs
using System.ComponentModel;
using System.Runtime.CompilerServices;
using System.Windows;

namespace CodeWithHeeren
{
    public partial class MainWindow : Window, INotifyPropertyChanged
    {

        public MainWindow()
        {
            DataContext = this;
            InitializeComponent();
        }

        private string textBound;

        public string TextBound
        {
            get { return textBound; }
            set
            {
                textBound = value;
                OnPropertyChanged("TextBound");
            }
        }

        public event PropertyChangedEventHandler? PropertyChanged;
        private void OnPropertyChanged([CallerMemberName] string propertyName = null)
        {
            PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
        }

    private void Button_Click(object sender, RoutedEventArgs e)
    {
        TextBound = "Set From Code";
    }
}
}

```
---
