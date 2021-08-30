## Create dynamic lists with RecyclerView   

- RecyclerView makes it easy to efficiently display large sets of data
- supply the data and define how each item looks
-  RecyclerView library dynamically creates the elements when they're needed.

>  RecyclerView recycles those individual elements. When an item scrolls off the screen, RecyclerView doesn't destroy its view. Instead, RecyclerView reuses the view for new items that have scrolled onscreen. 


## Key classes
- RecyclerView is the ViewGroup that contains the views corresponding to your data. 
- Each individual element in the list is defined by a view holder object. 
- The RecyclerView requests those views, and binds the views to their data, by calling methods in the adapter. 
- The layout manager arranges the individual elements in your list. 

### Steps for implementing your RecyclerView
1. decide what the list or grid is going to look like. 
2. Design how each element in the list is going to look and behave. 
3. Define the Adapter that associates your data with the ViewHolder views.


## Plan your layout
- The items in your RecyclerView are arranged by a LayoutManager class. 

The RecyclerView library provides three layout managers, which handle the most common layout situations:

> LinearLayoutManager arranges the items in a one-dimensional list.
> GridLayoutManager arranges all items in a two-dimensional grid:

> StaggeredGridLayoutManager is similar to GridLayoutManager, but it does not require that items in a row have the same height (for vertical grids) or items in the same column have the same width (for horizontal grids). The result is that the items in a row or column can end up offset from each other.

## Implementing your adapter and view holder
Implementing your adapter and view holder:

1. onCreateViewHolder(): RecyclerView calls this method whenever it needs to create a new ViewHolder. 

2. onBindViewHolder(): RecyclerView calls this method to associate a ViewHolder with data. 

3. getItemCount(): RecyclerView calls this method to get the size of the data set. 