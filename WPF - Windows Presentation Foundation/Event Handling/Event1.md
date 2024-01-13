## WPF - C#

### MainWindow.xaml.cs

```cs
/* 
1. Create two buttons , one button will bind for click event from xaml file and for another button click event bind from cs class. 
on clicking on each button it should open message box with some message. 
*/ 
public partial class MainWindow : Window
  {
      public MainWindow()
      {
          InitializeComponent();
          btn2.Click += btn2_Event;
      }

      private void btn1_Click(object sender, RoutedEventArgs e)
      {
          MessageBox.Show("Event binding from xml");
      }

      private void btn2_Event(object sender, RoutedEventArgs e)
      {
          MessageBox.Show("Event binding from CS class");
      }
  }

```
---
### MainWindow.xaml
```html
<Grid>
    <StackPanel >
        <Button x:Name="btn1" Content="xml event" Width="90" Height="30" Margin="5" Click="btn1_Click"/>
        <Button x:Name="btn2" Content="class event" Width="90" Height="30"/>

    </StackPanel>
</Grid>
```
---