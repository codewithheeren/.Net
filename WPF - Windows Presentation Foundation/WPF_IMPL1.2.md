## WPF - C#

### MainWindow.xaml.cs

```cs
/* 
3. Make a toggel button which change label from running to stop and along with that button label should also change.
*/ 
using System.Windows;

namespace CodeWithHeeren
{

    public partial class MainWindow : Window
    {
        bool flag = false;
        public MainWindow()
        {
            InitializeComponent();
        }

        private void Button_Click(object sender, RoutedEventArgs e)
        {
            if (!flag)
            {
                label1.Text = "Application Stopped.";
                btn.Content = "Run";
            }
            else {
                label1.Text = "Application Running.";
                btn.Content = "Stop";
            }
            flag = !flag;   
        }
    }
}

```
---
### MainWindow.xaml
```html
<Grid>
<TextBlock Name="label1" Text="" FontSize="30" />
<Button Name="btn" Content="Click Me" Height="30" Width="80" 
    VerticalAlignment="Center" HorizontalAlignment="Center"
    FontSize="18" Click="Button_Click"  />
</Grid>
```
---