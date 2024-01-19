## WPF - Custom Event

### 4. Create an employee form to take firstname,lastname,fullname. when user change first name or last name , full name full change automatically using INotifyPropertyChange event . 

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
        <Grid Margin="10">
            <StackPanel Orientation="Vertical" VerticalAlignment="Center">
                <Label Content="First Name:" Width="100"  Height="30" VerticalAlignment="Center"/>
                <TextBox x:Name="FirstNameTextBox" Text="{Binding Path=FirstName , Mode=TwoWay}" Width="200"  Height="30"/>

                <Label Content="Last Name:" Width="100" Height="30" VerticalAlignment="Center"/>
                <TextBox x:Name="LastNameTextBox" Text="{Binding Path=LastName , Mode=TwoWay}" Width="200" Height="30"/>

                <Label Content="Full Name:" Width="100" Height="30" VerticalAlignment="Center"/>
                <TextBox x:Name="FullNameTextBox" Text="{Binding Path=FullName , Mode=TwoWay}" Width="200"  Height="30"/>
            </StackPanel>
        </Grid>
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
        Employee employee;
        public MainWindow()
        {
            InitializeComponent();
            employee = new Employee() { FirstName = "Heeren" , LastName = "S." , FullName = "Heeren S."};
            this.DataContext = employee;
        }
    }
}
```
---
### Employee.cs

```cs
using System.ComponentModel;

namespace CodeWithHeeren
{
    public class Employee : INotifyPropertyChanged
    {
        public event PropertyChangedEventHandler? PropertyChanged;
        private string firstName;
        private string lastName;
        private string fullName;
        public string FirstName
        {
            get
            {
                return firstName;
            }
            set
            {
                firstName = value;
                OnPropertyChanged("FirstName");
                OnPropertyChanged("FullName");
            }
        }

        public string LastName
        {
            get
            {
                return lastName;
            }
            set
            {
                lastName = value;
                OnPropertyChanged("LastName");
                OnPropertyChanged("FullName");
            }
        }

        public string FullName
        {
            get
            {
                return fullName = firstName + " " + lastName;
            }
            set
            {
                fullName = value;
                OnPropertyChanged("FullName");
            }
        }

        private void OnPropertyChanged(string propertyName)
        {
            PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
        }
    }
}

```
---