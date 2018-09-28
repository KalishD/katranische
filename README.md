# README

Методики необходимые для проекта:

---=-=-=-=-=-=- Grid/List Toggle -=-=-=-=-=-=---

### In controller

def index
  # ... code here
  @partial = params[:view] || "default" # "grid", "list", etc.
end
### In index.html.erb:

<%= render @partial %>

_grid.html.erb, _list.html.erb, and _default.html.erb

---### Edit

### In controller

def index
  @partial = whitelisted_partial || 'default'
end

def whitelisted_partial
  %w(grid list).detect { |str| str == params[:view] }
end 

render partial: @partial, locals: { product: @product}

<%= link_to "Grid", products_path(view: "grid") %>
<%= link_to "List", products_path(view: "list") %>
---=-=-=-=-=-=- Sticky Sidebar -=-=-=-=-=-=---

### 
Search;
Accordion:
- List of categories --default
- List of brands;

---=-=-=-=-=-=- Ajaxify New/Create action -=-=-=-=-=-=---

https://rubyplus.com/articles/4211-Using-Ajax-and-jQuery-in-Rails-5-Apps
