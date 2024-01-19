## WPF - Data Binding

### 3. Create a form which takes information and make two way binding , on making changes in property, changes should display in alert on click on show data button.

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
        <Grid.ColumnDefinitions >
            <ColumnDefinition />
            <ColumnDefinition />
        </Grid.ColumnDefinitions>
        <Label x:Name="NameLabel" Content="Name :" FontSize="16" VerticalAlignment="Center" HorizontalAlignment="Right"/>
        <Label x:Name="ContactLabel" Content="Contact :"  FontSize="16" VerticalAlignment="Center" HorizontalAlignment="Right" Margin="0,40,0,0"/>
        <Label x:Name="AddressLabel" Content="Address :"  FontSize="16" VerticalAlignment="Center" HorizontalAlignment="Right" Margin="0,80,0,0"/>
        
        <TextBox x:Name="NameText" Text="{Binding Name, Mode=TwoWay}" Grid.Column="1" FontSize="16" Width="90" Height="20" VerticalAlignment="Center" HorizontalAlignment="Left"/>
        <TextBox x:Name="ContactText" Text="{Binding Contact  Mode=OneWay}"  Grid.Column="1" FontSize="16" Width="90" Height="20" VerticalAlignment="Center" HorizontalAlignment="Left" Margin="0,40,0,0" />
        <TextBox x:Name="AddressText" Text="{Binding Address}" Grid.Column="1" FontSize="16" Width="90" Height="20" VerticalAlignment="Center" HorizontalAlignment="Left" Margin="0,80,0,0"/>

        <Button x:Name="ShowData" Content="Show Data" Click="ShowData_Click" Width="90" Height="30" Grid.Column="1" RenderTransformOrigin="0.5,0.5" Margin="0,290,310,114" />
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
        private Person person;
        public MainWindow()
        {
            InitializeComponent();
            person = new Person()
            {
                Name = "Heeren",
                Contact = "1234567",
                Address = "Lisbon"
            };
            DataContext = person;
        }

        private void ShowData_Click(object sender, RoutedEventArgs e)
        {
            MessageBox.Show(person.ToString());
        }
    }
    internal class Person
    {
        public String Name { get; set; }
        public String Contact { get; set; }
        public String Address { get; set; }

        public override string? ToString()
        {
            return "Name-" + Name + "Contact-" + Contact + "Address-" + Address;
        }
    }
}
```
---
