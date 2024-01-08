### Practice problems to get familier with WPF
1. Write 'Hello World' label on window form.   
-- Change the label hello world to hi world on loading of form.  
-- show the label in center of the page.  
Note - If you directly drag and drop form component then it will automatically add hardcoded margins to component  definition in xaml file which results not a responsive form.So its recommand to write form by your own.
2. Change the label hello world to hi world on clicking on button.
3. Make a toggel button which change label from running to stop and along with that button label should also change.
4. Create a form with grid of 3x2 where each ractangle filled with different color.
5. Create a form with three rows of different color assuming that 1st row will be menu bar and second row is content pane and last row will be footer and then fix the size of first and last row in responsive design. 
6. In extention of task5 second row (content pane) divide that in to 3 columns with different colors and their size proposional should be as 40% , 40%, 20% each resepectivly.
7. Create a wpf with menu bar (File(inside file menu -> Exit), Edit) , just below the menu within header create button and textbox.
8. Create a form to get customer details such as name, address,contact, pincode.
    1. Create form with out using custom control for text box.
    2. Create a custom text box .
    3. Implement Custom Controls in User form page.
    4. Add events to the form such as clear button should work, text box should be editable.  
9. Create following design where on typing in text field same value should show in textblock and on clicking on button a value will set to property but that will not reflect on text field.
    
![image](https://github.com/codewithheeren/.Net/assets/87074236/a5bc8f16-20fe-4a0c-a78d-230e49e78b19)

After Click on SetValue button  

![image](https://github.com/codewithheeren/.Net/assets/87074236/e234a843-0d63-46e1-a786-d365658e63ea)

10. Generate message box on click of button like given below.
    
![image](https://github.com/codewithheeren/.Net/assets/87074236/4c209c47-8953-43d1-8851-33367ad64cef)


11. Generate open file dialog on click on button as shown in given image.

![image](https://github.com/codewithheeren/.Net/assets/87074236/1064547e-64af-4a08-9b7c-0b9276074ffb)  

12. Generate folder browser dialog box on click of button
  
Some Important properties - 
button -
Button Name="btn" Content="Click Me" Height="30" Width="80"  VerticalAlignment="Center" HorizontalAlignment="Center"
FontSize="18"
