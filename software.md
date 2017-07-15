---
layout: page
title: Software
permalink: /software/
---
{::nomarkdown}

<div id='github-projects'></div>
<script type="text/javascript">
$.getJSON('//api.github.com/users/thejordanprice/repos',{},function(data){
    var element = document.getElementById('github-projects');
    for(let repo in data) {
        // organize from api
        var name = data[repo].name.toString();
        var full = data[repo].full_name.toString();
        var star = data[repo].stargazers_count.toString();
        // make a string
        var string = "<p><a href='https://github.com/" + full + "'>" + full + "</a></p>";
        element.innerHTML += string;
    };
    // console.log(data);
});
</script>
{:/}