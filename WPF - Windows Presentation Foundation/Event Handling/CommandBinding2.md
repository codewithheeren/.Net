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
    <Window.Resources>
        <local:ViewModel x:Key="vm"/>
    </Window.Resources>
    <Grid >
        <Button Content="Click" Width="90" Height="30" Command="{Binding MyCommand, Source={StaticResource vm}}" VerticalAlignment="Center" HorizontalAlignment="Center" />
    </Grid>
</Window>

```
---
### CustomCommand.cs

```cs
using System.Windows.Input;

namespace CodeWithHeeren
{
    public class CustomCommand : ICommand
    {
        Action<Object> executeMethod;
        Func<object, bool> canExecuteFunction;
        public CustomCommand(Action<Object> executeMethod, Func<object, bool> canExecuteFunction)
        {
            this.executeMethod = executeMethod;
            this.canExecuteFunction = canExecuteFunction;
        }
        public bool CanExecute(object? parameter)
        {
            return true;
        }

        public void Execute(object? parameter)
        {
            executeMethod(parameter);
        }

        public event EventHandler? CanExecuteChanged;
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
    public class ViewModel
    {
        public ICommand MyCommand { get; set; }
        public ViewModel()
        {
            MyCommand = new CustomCommand(Execute, CanExecute);
        }
        public void Execute(object? parameter)
        {
            MessageBox.Show("Command Message invoke");
        }
        public bool CanExecute(object parameter)
        {
            return true;
        }
    }
}

```
---