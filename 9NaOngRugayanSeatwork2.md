# Seatwork #2 - Getting to know CSS Position and z-index.
### This seatwork will ask you to implement the different CSS position on a given code.
### short link to this .md file is: https://bit.ly/4c61P9K
#### Resources (also found in Khub week 5)
- [4 Minute Youtube Video on CSS Position](https://www.youtube.com/watch?v=YEmdHbQBCSQ)
- [CSS Position Tutorial](https://roycan.github.io/CssPositioningZIndexLab/)

### Instructions: 
1. This is individual submission in khub, but you can work with a partner.  When you submit in khub please place both your names in the submission bin.
2. Guided Activity (30 minutes), please follow what is being required.  

    - Make a copy of this .md file to your Q4 repository and name it as *SectionLNseatwork2.md* example *9LiCruzSeatwork2.md*. Place it in your q4 repository vscode local computer. Committing frequently to your Github repository.  
    - Copy the code below and paste it inside a new file (name it as SectionLNseatwork2.html). Place this file in the same location where the .md file is saved. 
    - Change the content values of the meta tags to your names for author/s and the date today for revised.
    - Please do the following tasks that will ask you to reposition HTML elements then answer the guided question for each task on the .md file. Commit changes to the .md file and to the .html file as well.
    *- This seatwork is worth 20pts and should be submitted by the end of the period* The link to [KHub submission bin](https://khub.mc.pshs.edu.ph/mod/assign/view.php?id=15481).
      - Submit the links to your .md file and .html file.

<!DOCTYPE html>
<html>
<head>
  <meta name="author" content="<your names>" />
  <meta name="revised" content="<date today>" />
  <style>
    body { font-family: Arial, sans-serif; }
    .header, .footer {
      background: lightblue;
      padding: 10px;
    }
    .footer {
       opacity: 0.5;
    }
    .sidebar {
      background: lightgreen;
      width: 150px;
      height: 200px;
    }
    .content {
      background: lightyellow;
      width: 300px;
      height: 200px;
    }    
  </style>
</head>
<body>
  <div class="header">Header</div>
  <div class="sidebar">Sidebar</div>
  <div class="content">Main Content</div>
  <div class="footer">Footer</div>
</body>
</html>
### Step 1 (Static vs Relative):

- Add in css 
position: relative; top: 20px; left: 20px;``` to .sidebar.

- Guided Question: What changed compared to the default static positioning? Try to give different values to top and left or you can change it to bottom, right.
- Answer: Default static positioning always places elements to the uppermost left part of the screen. Applying relative positioning allows you to change the position of the sidebar relative to the top, bottom, right and left of the viewport.

### Step 2 (Fixed):

- Add in css ```position: fixed; bottom: 0; width: 100%;``` to .footer.

- Guided Question: What happens when you scroll the page? Why does the footer behave differently from position relative?
- Answer: The footer stays at the bottom. It behaves differently from position relative because fixed makes the element that it's applied to stay where it's positioned no matter how much you scroll, relative is affected by scrolling.

### Step 3 (Absolute):

- Add in css ```position: absolute; top: 66px; left: 200px;``` to .content.

- Guided Question: What is the effect of position: absolute on an element? How is it different from fixed?
- Answer: position: absolute changes the position of an element based on its most recently positioned ancestor. Fixed positioning changes the position based on the viewport, and the element stays in its position even when you scroll, while absolute moves with the page when you scroll.

### Step 4 : (Absolute)

- Add in html ```<div class="notice">Notice!</div>``` and include the css below:

```css
.notice {
    position: absolute;
    top: 60px;
    left: 400px;
    background: orange;
    padding: 10px;
    z-index: 2;
}

- Give .content a z-index: 1.

- Guided Question: Why does the notice appear on top of the content? What happens if you swap the z‑index values?
- Answer: The notice appeared on top of the content because it has a higher z-index than the content, z-index affects the layering or the stacking of the elements, moving an element further to the front or to the back. If the z-index values are swapped, the content will cover the notice.

- Challenge: 
    * What changes that you have to do on the code that will position .notice box on the top right corner of the .content box? Please write the code on paper as well (both html and css on the part of .notice and .content).
    * Try to change the position of .content to relative then to fixed. What do you observed each time?
    * What do you observe on about the effect of z-index on .notice and .content boxes?

3. Please answer the following reflection questions (15 minutes)

    a. Could you summarize the differences between the CSS position values (static, relative, absolute, fixed)? 

    We have 4 possible CSS position values: First, the static is meant to be the default value and has zero effect on the element; however, when we use the other values (relative, absolute, and fixed), we can use other properties: top, bottom, left, right, and z-index to position our element. Next, using relative, we can offset the element relative to itself (if the element was static). Third, absolute uses a "parent" and "child element, and it is positioned relative to its nearest ancestor (that has a specified position). It allows us to position elements inside other elements. Lastly, position fixed will "glue" the element to the window. As the user scroll, the element will follow the user around as it sticks on another layer above everything else. Additionally, for fixed, the properties (top, left, right, bottom) are relative to the entire window.
 
    b. How does absolute positioning depend on its parent element?

    When we use absolute positioning, the child element depends on its parent element (aka: the nearest ancestor) that has a positioned at another value other than static. The child element has a position of absolute within/inside the parent element (that is best positioned at relative); however, if we lack the position: relative to the parent element, the absolute element will be positioned to the body. To sum, it lets us position elements inside/overlay other elements. It has a new stacking context, but the layers can be controlled using the z-index roperty.

    c. How do you differentiate sticky from fixed (you can research on sticky)?

   First, fixed will sticks the element to the window. As the user scroll, the element will follow the user around as it sticks on another layer above everything else and will not move under any circumstances. Additionally, for fixed, the properties (top, left, right, bottom) are relative to the entire window. On the hand, for sticky, acts like a normal element unless it is in a scrollable websit. It will scroll with the user unless it hits a specified position, it will stick to it (similar to a fixed element, with a new stacking context). The "sticking point" can be specified using top, left, right, and bottom.

    d. If you were designing a webpage for a school event, how might you use positioning to highlight important information? Please give concrete examples.

    If we were to create a webpage for a school event, such as a fair we can use positioning to highlight important information such as announcements and more by stacking elements on top of eachother. An important reminder to have during school events is a clear schedule/calendar that everyone can easily access and view, so I belive that we can utilize fixed positioning because no matter where you view it on the page, it is still visible. Second, a tab/platform where posts and images of the events can be shared (like social media) should be added to share a preview of what's happening. For this, we can use absolute to position elements inside other elements (we will use absolute since the posts will be placed inside a sepaprate element for a organized look). Lastly, we can use sticky to only show partially important announcements relevant to specified events. As we scroll through the specified event, the reminder will follow us; however, when we have scrolls past the event, the element will stay in that fixed position unless the user returns.
