---
layout: page
title: Home
---
{% assign items = site.data.mric %}

<link href="{{ site.baseurl }}/css/vanilla-dataTables.min.css" rel="stylesheet" type="text/css">

## Browse the MRIC Archives

<img src="images/221x321-UIC-graphic.jpg" style="float:left;width:25%;max-width:150px;margin:5px 15px;">

[Malcolm M. Renfrew Interdisciplinary Colloquium](http://www.uidaho.edu/class/mric) is a long standing lecture series by distinguished members of the University of Idaho community presenting and describing their approach to teaching and research in their disciplines.
This web archive preserves access to a record of past lectures as presented on the MRIC website, often including an abstract and video recordings.

For information about MRIC and the [Web Archive Collections](https://www.lib.uidaho.edu/digital/webarchive/), please visit the [About page](about.html).

<div style="clear:both"></div>

<table id="index-table" class="display">
    <thead>
        <tr>
            <th>Year</th>
            <th>Title</th>
            <th>Abstract</th>
        </tr>
    </thead>
    <tbody>
{% for item in items %}        
        <tr>
            <td>{{ item.date }}</td>
            <td><a href="{{ site.baseurl }}/archive/{{ item.name }}.html">{{ item.title }}</a></td>
            <td>{{ item.body | strip_html | truncatewords: 40 }} <a href="{{ site.baseurl }}/archive/{{ item.name }}.html">View</a></td>
        </tr>
{% endfor %}
    </tbody>
</table>

<script src="{{ site.baseurl }}/css/vanilla-dataTables.min.js" type="text/javascript"></script>

<script>
    var dataTable = new DataTable("#index-table", {
        perPage: 20,
        fixedColumns: true,
        layout: {
            top: "{info}{search}",
            bottom: "{select}{pager}"
        },
        columns: [
            { select: 0, sort: "desc" }
        ]
    });
</script>
