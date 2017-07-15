---
layout: page
title: Software
permalink: /software/
---

<div id='github-projects'></div>
<script type="text/javascript">
$.getJSON('//api.github.com/users/thejordanprice/repos',{},function(data){
    var element = document.getElementById('github-projects');
    for(let repo in data) {
        // organize from api
        var title = data[repo].name.toString();
        var repo  = data[repo].full_name.toString();
        var stars = data[repo].stargazers_count.toString();
        // make a string
        var string = "<p><a href='https://github.com/" + full_name + "'>" + title + "</a><small>" + stars + "</small></p>";
        element.append(string);
    };
    // console.log(data);
});
</script>