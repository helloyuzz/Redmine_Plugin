# _list.html
```html
  <tr id="issue-<%= issue.id %>" 
      class="hascontextmenu <%= cycle('odd', 'even') %> <%= issue.css_classes %> <%= level > 0 ? "idnt idnt-#{level}" : nil %>">
    <td class="checkbox hide-when-print"><%= check_box_tag("ids[]", issue.id, false, :id => nil) %></td>
    <% query.inline_columns.each do |column| %>   
      <% case column.name%>
        <% when :tracker%>
          <%= content_tag('td', column_content(column, issue), :class => issue.tracker) %>
		<% when :priority%>
          <%= content_tag('td', column_content(column, issue), :class => issue.priority) %>
        <% else %>
          <%= content_tag('td', column_content(column, issue), :class => column.css_classes) %>
      <% end %>
    <% end %>
    <td class="buttons"><%= link_to_context_menu %></td>
  </tr>
```


```application.css
td.Story {
	background: url(../images/Story.png) no-repeat 2px 50%;font: 0/0 caption;  
	background-position-x: center;min-width: 40px;
	}
td.Bug {
	background: url(../images/Bug.png) no-repeat 2px 50%;font: 0/0 caption;  
	background-position-x: center;min-width: 40px;
	}
td.Task {
	background: url(../images/Task.png) no-repeat 2px 50%;font: 0/0 caption;  
	background-position-x: center;min-width: 40px;
	}
td.CodeReview{
	background: url(../images/CodeReview.png) no-repeat 2px 50%;font: 0/0 caption;  
	background-position-x: center;min-width: 40px;
	}
```

<img src="https://github.com/helloyuzz/Redmine/blob/master/screenshot.png?raw=true" width="800px">
