# jlbiketest

<!DOCTYPE html>
<html>
<head>
<script type="text/javascript" src="http://code.jquery.com/jquery-latest.min.js"></script>
  <script src="http://www.kryogenix.org/code/browser/sorttable/sorttable.js"></script>
<title>HTML5, CSS3 and JavaScript demo</title>
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
     <table id= "bikedata" border="0" cellspacing="0" class="sortable">
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
