# RandomJavascriptMethods
Some Random Functions i used that i wanted to keep for future reference on certain items not really meant to be a project or anything serious but random solutions i implemented for certain issues i experienced that we could not solve with our server side velocity language in dotCMS (definately possible just temp fixes until we can do the proper fix)


//reorganizing news cards (2-20-2020 found way to do this with velocity when pulling from 2 sources create new array of object using same key values then loop over that array and display) 
<script>
    //selecting published dates
    let cards = document.getElementsByClassName('news-card');
    
    //creating array from cards then sorting
    Array.from(cards).sort((a,b)=> {
        // setting to date object based off date attribute on each card using value of to get primitive date value
        a = new Date(a.attributes[0].nodeValue).valueOf() 
        b = new Date(b.attributes[0].nodeValue).valueOf() 
  
        
        return a-b
//organizing for each element inside sorted array we will add that element into the news resources.. 
    }).forEach(el => {
  document.getElementById('NewsResources').prepend(el);
    })
    
</script>
