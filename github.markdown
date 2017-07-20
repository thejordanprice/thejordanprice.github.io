---
layout: page
permalink: /software/github/
header-img: "img/contact-bg.jpg"
description: "My github repositories."
---

{::nomarkdown}

<div id='github-projects'></div>
<script type="text/javascript">
$.getJSON('//api.github.com/users/thejordanprice/repos',{},function(data){
    var element = document.getElementById('github-projects');
    for(let repo in data) {
        // organize from api
        // console.log(data[repo]);
        var name = data[repo].name.toString();
        var full = data[repo].full_name.toString();
        var desc = data[repo].description.toString();
        var star = data[repo].stargazers_count.toString();
        var push = data[repo].pushed_at.toString();
        var watc = data[repo].watchers_count.toString();
        var clon = data[repo].clone_url.toString();
        // date manipulation
        var date = new Date(push);
        var options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
        var day = date.toLocaleDateString("en-US",options);
        // make a string
        var string = "<div class='container'><div><a href='https://github.com/" + full + "'>" + full + "</a></div><div style='font-size: small;'>" + desc + "</div><div style='font-size: small;'>Stars: " + star + " Watchers: " + watc + "</div><div style='font-size: small;'>Latest: " + day + "</div></div><br>";
        element.innerHTML += string;
    };
    // console.log(data);
});
</script>

{:/}