# jlbiketest

<html>
<head>
<script type="text/javascript" src="http://code.jquery.com/jquery-latest.min.js"></script>
  <script src="http://www.kryogenix.org/code/browser/sorttable/sorttable.js"></script>
</head>
<body>
<script>

$(function() {

   var items = [];

   $.getJSON('https://raw.githubusercontent.com/jujhars13/jujhars13/master/bikes.json', function(data) {
       $.each(data.items, function(i, f) {
         var tblRow = "<tr>" + "<td>" + "<img src="+ f.image.thumb + "/>" + "</td>" + "<td>" + f.name + "</td>" + "<td>" + f.description + "</td>" +  "<td>" + f.class + "</td>" + "</tr>"
           $(tblRow).appendTo("#bikedata tbody");
     });

   });
  
});  
</script>
</head>

<body>
<script language="javascript" type="text/javascript">
	var bikeFilters = {
		btn: true,
		col_0: "none",
		col_3: "select",
		btn_text: "  Filter  "
	}
	setFilterGrid("bikedata",3,bikeFilters);
</script>
<div class="wrapper">
<div class="profile">
     <table id= "bikedata" border="1" cellspacing="0" class="sortable">
  <thead>
    <th>Image</th>        
    <th>Name</th>
            <th>Description</th>
            
            <th>Class</th>
        </thead>
      <tbody>

       </tbody>
   </table>

</div>
</div>

</body>
</html>


I have assumed that by filterable information you also require the facility to sort the data. 
I have therefore tried to build a simple table based page fulfilling the data requirements.

Things i would do if i had more time and more insight would be:

Exploring why filtering was not available with the setup i have created. I have attempted to introduce multiple filtering formats. The amendments would either not change anything or completely break the table.

With a more advanced build with more options and items, i would also consider entering a comparison system to the selection.

Another issue that i have come across is that even in my build the thumbnails/large versions do not seem to appear within the grid and displays a broken image file. However the file format does work when looked at seperately.

My final struggle was working out the refresh rule. I have tried but the page when you reload the webpage resets to the standard appearance. So my final version has had the rule removed.
