+++
title = "Hierarchies"
date = 2021-10-01T09:28:27-05:00
draft = false
weight = 2
+++

Data is oftentimes arranged in a pecking order, mirroring what we see in the outside world. We can rank data just as we would a family tree starting with great grandparents and moving down through the generations. In data, we call this a hierarchical structure. A **hierarchy** in Tableau is the mechanism Tableau uses to allow you to organize your data this way.

When you load your data into a worksheet, Tableau will automatically assemble a hierarchy. If you see something that is off or not how you think it should be organized, then you may want to create a custom hierarchy.

If we still work for an online retailer, but are instead focusing on all sales within the accessories department, we might need to establish a customer hierarchy. We might start with a label for accessory type, then move on to a sub style then to an additional desriptor field. In the case of hoop earrings, the accessory type would be jewelry, the sub style would be earrings, and then the additional descriptor would be hoops.

You can also always remove a custom hierarchy later on.