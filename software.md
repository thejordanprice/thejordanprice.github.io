---
layout: page
title: Software
permalink: /software/
---

<div id='github-projects'></div>
<script type="text/javascript">
$.getJSON('//api.github.com/users/thejordanprice/repos',{},function(data){
    var element = document.getElementById('github-projects');
    element.innerHTML = data;
    console.log(data);
});
</script>