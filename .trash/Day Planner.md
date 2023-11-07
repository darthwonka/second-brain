# Day Planner

<% await tp.file.move("/Day Planners/Day Planner-" + tp.file.creation_date('YYMMDD')) %>

> [!info]
>  created: <% tp.file.creation_date("YYYY-MM-DD hh:mm") %>
>  modified: <%+ tp.file.last_modified_date("YYYY-MM-DD hh:mm") %>

##  Current open tasks

```tasks
not done
path does not include z_template
```

## Journal




---

<< [["Day Planner-" + <% tp.date.now("YYYYMMDD", -1) %>]] | [[ "Day Planner-" + <% tp.date.now("YYYYMMDD", 1) %>]] >>