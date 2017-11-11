$(document).ready( function() {
  
		var subreddit = 'Furry'; 
		var aRandomNum = Math.floor((Math.random() * 25) + 1); 
		
		$.getJSON('http://www.reddit.com/r/'+subreddit+'.json?jsonp=?&show=all&limit=25', function(data) {
			$.each(data.data.children, function(i,item){
				if (i == aRandomNum) {
					$("<img/>").attr("src", item.data.url).appendTo("#image");
					return false;
				}
			});
		});
		
});
