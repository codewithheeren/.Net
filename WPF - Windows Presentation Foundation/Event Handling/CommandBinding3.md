## WPF - Commmand Binding

###  1. On click on button , populate a message box saying HI. but this should be done using command class binding. 

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
     <StackPanel Orientation="Vertical" VerticalAlignment="Center">
         <TextBlock Text ="{Binding Message, Mode=TwoWay}" FontSize="16"/>
         <Button Content="Click me" VerticalAlignment="Center" HorizontalAlignment="Center" Command="{Binding MyCommand}" />
     </StackPanel>
 </Grid>
</Window>

```
---
### CustomCommand.cs

```cs
using System.Windows.Input;

namespace CodeWithHeeren
{
    using System.Windows.Input;

namespace WpfApp1
{
    public class DisplayDataCommand : ICommand
    {
        private Action exceuteOperation;
        private Func<bool> canExecuteOperation;

        public DisplayDataCommand(Action exceuteOperation, Func<bool> canExecuteOperation)
        {
            this.exceuteOperation = exceuteOperation;
            this.canExecuteOperation = canExecuteOperation;
        }

        public bool CanExecute(object? parameter)
        {
            return (bool)canExecuteOperation();
        }

        public void Execute(object? parameter)
        {
            exceuteOperation();
        }

        public event EventHandler? CanExecuteChanged;

    }
}

}

```
---
### ViewModel.cs

```cs
using System.Windows;
using System.Windows.Input;

namespace CodeWithHeeren
{
    using System.ComponentModel;

namespace WpfApp1
{
    public class AppInfo : INotifyPropertyChanged
    {
        public event PropertyChangedEventHandler? PropertyChanged;
        public DisplayDataCommand MyCommand { get; set; }
        public AppInfo()
        {
            MyCommand = new DisplayDataCommand(ExceuteOperation, CanExecuteOperation);
        }
        public void ExceuteOperation()
        {
            Message = "Welcome to the project";
        }
        public bool CanExecuteOperation()
        {
            return true;
        }

        private string message;
        public string Message
        {
            get
            {
                return message;
            }
            set
            {
                this.message = value;
                OnPropertyChanged("Message");
            }
        }
        public void OnPropertyChanged(string propertyName)
        {
            if (propertyName != null)
            {
                PropertyChanged(this, new PropertyChangedEventArgs(propertyName));
            }
        }

    }
}

}

```
---

### MainWindow.xaml.cs
```cs
namespace CodeWithHeeren
{
    public class MainWindow
    {
       public AppInfo appInfo;
       public MainWindow()
        {
             InitializeComponent();
             appInfo = new AppInfo();
             DataContext = appInfo;
        }
    }
}

```
---