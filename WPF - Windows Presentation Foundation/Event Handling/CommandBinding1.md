## WPF - Commmand Binding

###  1. On click on button , populate a message box saying HI. but this should be done using command class binding. 

### MainWindow.xaml
```html
    <Grid>
        <StackPanel>
            <Button x:Name="btn" Content="Show Data" FontSize="16" VerticalAlignment="Center" HorizontalAlignment="Center" Command="{Binding MyCommand}"/>
        </StackPanel>
    </Grid>

```
---
### MainWindow.xaml.cs

```cs
using System.Windows;
using System.Windows.Input;

namespace CodeWIthHeeren
{
    public partial class MainWindow : Window
    {
        public ICommand MyCommand { get; set; }
        public MainWindow()
        {
            InitializeComponent();
            MyCommand = new CustomCommand(MethodInvoke, CanExecute);
            this.DataContext = this;
        }

        public void MethodInvoke()
        {
            MessageBox.Show("Employee Data Chaged.");
        }

        public bool CanExecute()
        {
            return true;
        }
    }
}
```
---
### CustomCommand.cs

```cs
using System.Windows.Input;

namespace CodeWithHeeren
{
    public class CustomCommand : ICommand
    {
        private Action methodInvoke;
        private Func<bool> canExecute;

        public CustomCommand(Action methodInvoke, Func<bool> canExecute)
        {
            this.methodInvoke = methodInvoke;
            this.canExecute = canExecute;
        }

        public bool CanExecute(object? parameter)
        {
            return canExecute();
        }

        public void Execute(object? parameter)
        {
            methodInvoke();
        }
        public event EventHandler? CanExecuteChanged;
    }
}

```
---