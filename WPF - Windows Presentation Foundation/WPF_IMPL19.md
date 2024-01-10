## WPF - Define Global styles.  

/* 
19. Create Cutom styles for button and text fields and apply them.
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
        Title="MainWindow" Height="450" Width="400">
    <Window.Resources>
        <Style TargetType="TextBox">
            <Setter Property="Width" Value="200" />
            <Setter Property="Height" Value="30" />
            <Setter Property="FontSize" Value="20" />
            <Setter Property="Margin" Value="2" />
            <Setter Property="FontWeight" Value="Light" />
        </Style>
        <Style TargetType="Button">
            <Setter Property="Width" Value="100" />
            <Setter Property="Content" Value="Normal" />
            <Setter Property="FontSize" Value="20" />
            <Setter Property="Margin" Value="2" />
            <Setter Property="Height" Value="30" />
        </Style>
        <Style TargetType="Button" x:Key="ConfirmationButton">
            <Setter Property="Width" Value="100" />
            <Setter Property="Height" Value="40" />
            <Setter Property="FontSize" Value="20" />
            <Setter Property="Margin" Value="2" />
            <Setter Property="Content" Value="OK" />
            <Setter Property="Foreground" Value="Blue" />
            <Setter Property="Background" Value="LightBlue" />
        </Style>
    </Window.Resources>
    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition />
            <RowDefinition Height="60"/>
        </Grid.RowDefinitions>
        <StackPanel >
            <TextBox />
            <TextBox />
            <TextBox Height="40"/>
            <Button />
            <Button /> 
        </StackPanel>
        <Grid Grid.Row="1">
            <Button Style="{StaticResource ConfirmationButton}"/>
        </Grid>
    </Grid>
</Window>


```
---
### MainWindow.xaml.cs

```cs
using System.Windows;
using CodeWithHeeren.view;
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

