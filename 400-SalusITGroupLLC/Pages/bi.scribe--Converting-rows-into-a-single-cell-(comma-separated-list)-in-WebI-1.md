# bi.scribe: Converting rows into a single cell (comma separated list) in WebI

Created: 2022-05-12 08:35:32 -0600

Modified: 2022-05-12 14:35:33 -0600

---

Clipped from: [https://web.archive.org/web/20181215122651/http://bi.srivatsakr.com/2011/08/converting-rows-into-single-cell-comma.html](https://web.archive.org/web/20181215122651/http:/bi.srivatsakr.com/2011/08/converting-rows-into-single-cell-comma.html)

***This post describes steps on how to concatenate data in multiple rows into a single cell, as a comma separated list.***

I had read a post on this in [forumtopics](https://web.archive.org/web/20181215122651/http:/www.forumtopics.com/busobj/index.php) long back, but could not find it when I needed it now. Hence, I experimented on this for a while based on whatever I remembered and found out the way once again. So, I thought of jotting it down here before I forget it, and hopefully someone finds it useful when they are searching for a similar requirement!!

Let us take an example from eFashion universe. I am picking **[LINES]** and **[CATEGORY]** objects from the Product class for my example:

![Category](../media/Pages-bi.scribe--Converting-rows-into-a-single-cell-(comma-separated-list)-in-WebI-image1.jpg){width="1.8333333333333333in" height="0.4583333333333333in"}

In the result set, I am restricting the rows (for simplicity) for **LINES** = Dresses, Jackets and Leather.

![Lines Dresses Dresses Dresses Dresses IFFkets Jackets Jackets Leather Leather Leather Category Casual dresses Evening wear Sweater dresses Boatwear Fancy fabric Outdoor Jackets Pants Shills](../media/Pages-bi.scribe--Converting-rows-into-a-single-cell-(comma-separated-list)-in-WebI-image2.jpg){width="2.2916666666666665in" height="2.779861111111111in"}

For the above data, what needs to be achieved would look something like below:

![Lines Dresses Jackets Leather Category Sweater dresses, Skills, Evening wear, Casual dresses Outdoor, Fancy fabric, Boatwear Shills, Pants, Jackets](../media/Pages-bi.scribe--Converting-rows-into-a-single-cell-(comma-separated-list)-in-WebI-image3.jpg){width="4.523611111111111in" height="1.0534722222222221in"}

A method on how this can be achieved at report level in WebI is explained below:

- Create a variable **[VAR Max Category] = Max([Category]) In ([Lines])** to find the maximum category, with respect to each Line
- Create a variable **[VAR Concat Category] = [Category] +", "+ Previous(Self)**, to concatenate the category value with it's previous row value

The records would look like this:

![Lines Dresses Dresses Dresses Dresses Jackets Jackets Jackets Leather Leather Leather Category Casual dresses Evening wear Sweater dresses Boatwear Fancy fabric Outdoor Jackets Pants Shills VAR Max Category VAR Concat Category Sweater dresses Sweater dresses Sweater dresses Sweater dresses Outdoor Outdoor Outdoor Shills Shills Shills Casual dresses, Evening wear, Casual dresses, Skills, Evening wear, Casual dresses, Sweater dresses, Skills, Evening wear, Casual dresses, Boatwear, Sweater dresses, Skills, Evening wear, Casual dres Fancy fabric, Boatwear, Sweater dresses, Skills, Evening wear Outdoor, Fancy fabric, Boatwear, Sweater dresses, Skills, Ever Jackets, Outdoor, Fancy fabric, aoatwear, Sweater dresses, Sk Pants, Jackets, Outdoor, Fancy fabric, Boatwear, Sweater Shills, Pants, Jackets, Outdoor, Fancy fabric, aoatwear, SweatE](../media/Pages-bi.scribe--Converting-rows-into-a-single-cell-(comma-separated-list)-in-WebI-image4.jpg){width="6.0in" height="2.3868055555555556in"}

- Create a 3rd variable **[VAR Max Concat Category] = [VAR Concat Category] Where ([Category]=[VAR Max Category])**. This variable basically gives only those rows of [VAR Concat Category], where the value of the category is maximum for that particular Line

On replacing **VAR Concat Category** with **VAR Max Concat Category** column in the above screenshot, we get:

![Lines Dresses Dresses Dresses Dresses IFFkets Jackets Jackets Leather Leather Leather Category Casual dresses Evening wear Sweater dresses Boatwear Fancy fabric Outdoor Jackets Pants Shills VAR Max Category VAR MAX Concat Category Sweater dresses Sweater dresses Sweater dresses Sweater dresses Outdoor Outdoor Outdoor Shills Shills Shills Sweater dresses, Skills, Evening wear, Casual dresses, Sweater dresses, Skills, Evening wear, Casual dresses, Sweater dresses, Skills, Evening wear, Casual dresses, Sweater dresses, Skills, Evening wear, Casual dresses, Outdoor, Fancy fabric, Boatwear, Sweater dresses, Skills, Evening wear, Outdoor, Fancy fabric, aoatwear, Sweater dresses, Skills, Evening wear, Outdoor, Fancy fabric, Boatwear, Sweater dresses, Skills, Evening wear, Shills, Pants, Jackets, Outdoor, Fancy fabric, Boatwear, Sweater dresses, Shills, Pants, Jackets, Outdoor, Fancy fabric, aoatwear, Sweater dresses, Shills, Pants, Jackets, Outdoor, Fancy fabric, Boatwear, Sweater dresses,](../media/Pages-bi.scribe--Converting-rows-into-a-single-cell-(comma-separated-list)-in-WebI-image5.jpg){width="6.0in" height="2.196527777777778in"}

I have displayed **Category** and **Var Max Category** only for illustration purposes. It is actually not required to be present / displayed in the report. On removing those two columns:

![Lines Dresses Jackets Leather Category Sweater dresses, Skirts, Evening wear, Casual dresses, Outdoor, Fancy fabric, Boatwear, Sweater dresses, Skirts, Evening wear, Casual dresses, Shirts, Pants, Jackets, Outdoor, Fancy fabric, Boatwear, Sweater dresses, Skirts, Evening wear, Casual dres±](../media/Pages-bi.scribe--Converting-rows-into-a-single-cell-(comma-separated-list)-in-WebI-image6.jpg){width="6.0in" height="0.8451388888888889in"}

Now, the only pending thing to do is to display those categories that belong to their Lines, against each of their respective Lines. The below formula would do the trick:

- Create a variable **[VAR Category] =If(IsNull(Previous([VAR Max Concat Category]));Substr([VAR Max Concat Category];1;Length([VAR Max Concat Category])-2);Substr([VAR Max Concat Category];1;Pos([VAR Max Concat Category];Previous([VAR Max Concat Category]))-3))**

Basically, the formula checks if the previous value of **VAR Max Concat Category** is NULL.

If **TRUE**, then it just displays **VAR Max Concat Category**.

In the above screenshot, this scenario occurs for LINE = Dresses. There is no value for **VAR Max Concat Category** prior to LINE = Dresses and hence it is NULL.

If **FALSE**, then ***previous row*** value of **VAR Max Concat Category** is removed from the ***present row*** value of **VAR Max Concat Category**.

This scenario occurs for LINE = Jackets and LINE = Leather (and all the rows that may occur below). This is done with the help of ***POS*** (for finding the position where the previous value of VAR Max Concat Category starts), and ***SUBSTR*** functions

This is the final output what we intended to achieve at the beginning of this post:

![Lines Dresses Jackets Leather Category Sweater dresses, Skills, Evening wear, Casual dresses Outdoor, Fancy fabric, Boatwear Shills, Pants, Jackets](../media/Pages-bi.scribe--Converting-rows-into-a-single-cell-(comma-separated-list)-in-WebI-image3.jpg){width="4.523611111111111in" height="1.0534722222222221in"}
