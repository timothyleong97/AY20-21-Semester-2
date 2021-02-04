# CS3223 Lecture - Storage

1. Name the 4 things which a DBMS stores.

   > Answer: Relations, indexes, system catalog (relation metadata), log files
   >
   > <img src="C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210117095922193.png" alt="image-20210117095922193" style="zoom:50%;" />

2. Name three levels of memory and 2 examples from each.

   > Answer: 
   >
   > <img src="C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210117100018277.png" alt="image-20210117100018277" style="zoom:50%;" />

3. Order these 4 types of memory from slow to fast

   - Registers
   - Cache (SRAM)
   - Main memory (DRAM)
   - Disk/SSD

   > Answer: 
   >
   > <img src="C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210117100933589.png" alt="image-20210117100933589" style="zoom:50%;" />

4. Where does the DBMS store information and process information?

   > Answer: The DBMS stores information on non-volatile disks (persistent) and processes data in main memory (RAM)

5. What is a unit of data on a disk called?

   > Answer: A disk page

6. What is a cylinder, platter, track and sector on a disk?

   > Answer: <img src="C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210117101404843.png" alt="image-20210117101404843" style="zoom:50%;" />

7. Block size must be a ____ of sector size.

   > Answer: multiple

8. What are the three delays in disk reading?

   > Answer: 
   >
   > **<img src="C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210117104406170.png" alt="image-20210117104406170" style="zoom:50%;" />**

9. Name the five ways of improving access time of secondary storage

   > Answer: <img src="C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210117104503156.png" alt="image-20210117104503156" style="zoom:67%;" />

10. <img src="C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210117105243644.png" alt="image-20210117105243644" style="zoom:50%;" />

> Answer:
>
> <img src="C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210117105253563.png" alt="image-20210117105253563" style="zoom:50%;" />
>
> > Intuition: When you randomly store records, you can only calculate the average time to extract 1 sector because you don’t know if the rest of the track is useful so 0.4 comes from maximum transfer rate divided by sectors per track
>
> <img src="C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210117105407044.png" alt="image-20210117105407044" style="zoom:50%;" />
>
> > Intuition: To read the first cylinder, the rotation and seek delays are still incurred, and you read in every track of the cylinder.
> >
> > For the next 9 cylinders, you still incur the rotational delay but you now only incur track-to-track seek time instead of average seek time.

11. List two simple ways of memory allocation.

    > Answer: Bitmap and i-nodes

12. For i-nodes, what is the name of the head of the linkedlist that joins all the free blocks?

> Answer: Free space list head

13. What is the term for too much memory loss when pages are too big?

> Answer: Internal fragmentation

14. What is the name for the section in main memory used by the DBMS?

> Buffer pool

15. What is a unit of memory in this section called?

> Buffer frame

Use this website for B+ tree

![image-20210129080340032](C:\Users\User\Documents\AY20-21-Semester-2\CS3223\CS3223 Study Guide.assets\image-20210129080340032.png)