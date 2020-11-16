LVM stands for Logical Volume Management, its a concept by which we can extend or reduce storage space to system as space for storage required. In other word, we can say LVM concept provides us a kind of flaxible(Elastic) storage space. 
I am gonna integrate LVM concept with hadoop(datanode) to achive elasticity in terms of storage space.  

First of all to Integrate LVM concept with hadoop we need to attach some additional storage units, and need to craete a logical volume space. 

I attach two disk of 6GiB and 8Gib but we can attach more as we need.

![](1.png)

Two hard disk are successfully attached to my system.

![](2.png)

physical volume of 8Gib created successfully.

![](3.png)

physical volume of 6Gib created successfully.

![](4.png)

A Volume Group with name myvg craeated successfully.

![](5.png)

A Logical Volume with name mylv and size 9GiB craeated.

![](6.png)

Successfully created, a directory with name lvolume to mount logical volume mylv.

![](7.png)

Format process of mylv done successfully.

![](8.png)

Successfully mylv is mounted on lvolume.

![](9.png)

Attachment of lvolume drive(dir) in datanode configuration file.

![](10.png)

Configured capacity of datanode with around 9GiB storage space.

![](11.png)

Command to extend the capacity of datanode with size 3GiB
lvextend --size +3G /dev/myvg/mylv

![](12.png)

Finally, i have extended datanode storage space capacity with 3GiB.

![](13.png)


