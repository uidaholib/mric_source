---
layout: page
title: Home
---
{% assign items = site.data.fridayletters %}

<link href="{{ site.baseurl }}/css/vanilla-dataTables.min.css" rel="stylesheet" type="text/css">

## Browse The Friday Letter Archive

Malcolm M. Renfrew Interdisciplinary Colloquium is a long standing lecture series by distinguished members of the University of Idaho community presenting and describing their approach to teaching and research in their disciplines.
This web archive preserves access to a record of past lectures as presented on the MRIC website, often including an abstract and video recordings.
For information about MRIC and this project, please visit the [About page](about.html).

This table provides sorting and basic search of the archive contents. 
Click on the "Read" link to see the full abstract.

<table id="letter-table" class="display">
    <thead>
        <tr>
            <th>Date</th>
            <th>Subject</th>
            <th>Body</th>
        </tr>
    </thead>
    <tbody>
{% for item in items %}        
        <tr>
            <td>{{ item.date }}</td>
            <td>{{ item.title }}</td>
            <td>{{ item.body | strip_html | truncatewords: 40 }} <a href="{{ site.baseurl }}/letters/{{ item.date }}.html">Read</a></td>
        </tr>
{% endfor %}
    </tbody>
</table>

<script src="{{ site.baseurl }}/css/vanilla-dataTables.min.js" type="text/javascript"></script>

<script>
    var dataTable = new DataTable("#letter-table", {
        perPage: 20,
    });
</script>
