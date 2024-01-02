### WPF Key Points
* Visual studio shows xaml.cs file under xaml file in group together. but both are different files.So its more meaningful to have both together. 
*  By default main method implementation is inside app.xaml.cs comes from parent - application class.
*  In wpf xaml file , inside window tag you can have only one component container for EG. you can not create multiple textblock directly inside window tage so thats the reason bydefault we have grid layout tag inside window and inside grid we can have multiple components.
* Using layout we achive responsive UI degines.
* For three rows of different colors in grid, if you minimize IDE vertically then header and footer will leave their space and middle row of content will only shows which is a responsive degine issue so you can fix the height of first and 3rd row so in case if winodow will minimize first and last row will be fixed with its size.