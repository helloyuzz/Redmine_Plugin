# Redmine
```html
  <tr id="issue-<%= issue.id %>" class="hascontextmenu <%= cycle('odd', 'even') %> <%= issue.css_classes %> <%= level > 0 ? "idnt idnt-#{level}" : nil %>">
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
