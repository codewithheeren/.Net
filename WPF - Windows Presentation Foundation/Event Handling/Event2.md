## WPF - Bubble Event (Event Routing)

### MainWindow.xaml.cs

```cs
/* 
2. Create two buttons , One button will be inside other button , on click is inner button message box outer and message box of inner button will show one after another,that is bubble event . 
*/ 
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }
        private void Btn1_Click(object sender, RoutedEventArgs e)
        {
            MessageBox.Show("Outer Button");
        }
        private void Btn2_Click(object sender, RoutedEventArgs e)
        {
            MessageBox.Show("Inner Button");
        }
    }
```
---
### MainWindow.xaml
```html
 <Grid>
     <Button x:Name="Btn1"  Width="190" Height="70" Click="Btn1_Click" >
         <Button x:Name="Btn2" Content="Inner Button" Width="90" Height="30" Click="Btn2_Click" />
     </Button>
 </Grid>
```
---