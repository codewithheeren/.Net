## WPF - Custom styles for entire application.  

/* 
19.2 Create Cutom styles and apply them to entire application.
*/   
### Directory Structure -  
![image](https://github.com/codewithheeren/.Net/assets/87074236/21f46039-0e14-4f94-b0f4-068650371bfb)  

### Note - Add Resoure Dictonary file to Styles folder and add Styles there.
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

### App.xaml
```html
<Application x:Class="CodeWithHeeren.App"
             xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
             xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
             xmlns:local="clr-namespace:CodeWithHeeren"
             StartupUri="MainWindow.xaml">
    <Application.Resources>
        <ResourceDictionary>
            <ResourceDictionary.MergedDictionaries>
                <ResourceDictionary Source="Styles/ButtonStyles.xaml" />
                <ResourceDictionary Source="Styles/TextBoxStyles.xaml" />
            </ResourceDictionary.MergedDictionaries>
        </ResourceDictionary>
    </Application.Resources>
</Application>

```
---

### ButtonStyles.xaml
```html
<ResourceDictionary xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
                    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
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
</ResourceDictionary>

```
---
### TextBoxStyles.xaml
```html
<ResourceDictionary xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
                    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
    <Style TargetType="TextBox">
        <Setter Property="Width" Value="200" />
        <Setter Property="Height" Value="30" />
        <Setter Property="FontSize" Value="20" />
        <Setter Property="Margin" Value="2" />
        <Setter Property="FontWeight" Value="Light" />
    </Style>
</ResourceDictionary>

```
---
