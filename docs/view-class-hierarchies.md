---
layout: docs
title: View Class Hierarchies
---

exVim allow user generate the hierarchies pictures for specific class. This is done
by [ex-hierarchy](http://github.com/exvim/ex-hierarchy) plugin. 

The exVim generate an inherits file when you run `:Update` command. This file will  
extract the inherit information from your ctags generates. It records the inherit 
relationship of the classes in your proejct.

The [ex-hierarchy](http://github.com/exvim/ex-hierarchy) plugin will parse the inherit 
file when you input a class. It then generate a graphviz-dot file and use graphviz draw
a .png picture. At the end you have the picture for the hierarchies of the specific class.  

Currently, [ex-hierarchy](http://github.com/exvim/ex-hierarchy) supports c++, java, python
and so on. 

Here is an example of the `exPlane` class in ex2D:

![hv-explane]({{site.baseurl}}docs/images/hv-explane.png)

## Show Class Hierarchies 

[ex-hierarchy](http://github.com/exvim/ex-hierarchy) has three commands to print and show
class hierarchy.

 1. `:HV <class>`: will show the parents and childrent of `<class>`. 
 1. `:HVP <class>`: will show only the parents of `<class>`.
 1. `:HVC <class>`: will show only the childrent of `<class>`.

Let's take the picture above as example. The picture is generated by `:HV exPlane` command.
When we use `:HVP exPlane` instead, the result is:

![hvp-explane]({{site.baseurl}}docs/images/hvp-explane.png)

And `:HVC exPlane` result in:

![hvc-explane]({{site.baseurl}}docs/images/hvc-explane.png)

You also can use `<leader>hv` key mappings to run `:HV` command generated the current word's
hierarchies.

**NOTE:** The generated picture is stored in `.exvim.your-project/hv.png`, exVim will try 
to open it by your default picture viewer.