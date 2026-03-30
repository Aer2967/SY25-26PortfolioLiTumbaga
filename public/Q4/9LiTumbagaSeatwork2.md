# Seatwork #2 - Getting to know CSS Position and z-index.
### This seatwork will ask you to implement the different CSS position on a given code.
### short link to this .md file is: https://bit.ly/4c61P9K
#### Resources (also found in Khub week 5)
- [4 Minute Youtube Video on CSS Position](https://www.youtube.com/watch?v=YEmdHbQBCSQ)
- [CSS Position Tutorial](https://roycan.github.io/CssPositioningZIndexLab/)

### Instructions: 
1. This is individual submission in khub, but you can work with a partner.  When you submit in khub please place both your names in the submission bin.
2. Guided Activity (30 minutes), please follow what is being required.  

    - Make a copy of this .md file to your Q4 repository and name it as **SectionLNseatwork2.md** example **9LiCruzSeatwork2.md**. Place it in your q4 repository vscode local computer. Committing frequently to your Github repository.  
    - Copy the code below and paste it inside a new file (name it as SectionLNseatwork2.html). Place this file in the same location where the .md file is saved. 
    - Change the content values of the meta tags to your names for author/s and the date today for revised.
    - Please do the following tasks that will ask you to reposition HTML elements then answer the guided question for each task on the .md file. Commit changes to the .md file and to the .html file as well.
    **- This seatwork is worth 20pts and should be submitted by the end of the period** The link to [KHub submission bin](https://khub.mc.pshs.edu.ph/mod/assign/view.php?id=15481).
      - Submit the links to your .md file and .html file.

```html
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
```
### Step 1 (Static vs Relative):

- Add in css ```position: relative; top: 20px; left: 20px;``` to .sidebar.

- Guided Question: What changed compared to the default static positioning? Try to give different values to top and left or you can change it to bottom, right.

Under the position: relative value, adjusting the values for the top and left increase the change relative to its original positioning. A higher px value for the top and left part means that the box would go down and right, respectively. This also applies to when you apply bottom and right to the css.

### Step 2 (Fixed):

- Add in css ```position: fixed; bottom: 0; width: 100%;``` to .footer.

- Guided Question: What happens when you scroll the page? Why does the footer behave differently from position relative?

Using the position: fixed value, the element stays relative to the viewport. This means that even if you scroll down the page, the element - in this case, the footer - will not be affected by the scrolling and will stay in its designated position in the screen, while all the elements not using the fixed position will be affected by the scrolling.

### Step 3 (Absolute):

- Add in css ```position: absolute; top: 66px; left: 200px;``` to .content.

- Guided Question: What is the effect of position: absolute on an element? How is it different from fixed?

Using the position: absolute value, the box's position and size is specified with the 'top', 'right', 'bottom', and 'left' properties. These properties specify the adjustments based on the box's 'containing block', which is relative to its nearest ancestor.

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
```

- Give .content a z-index: 1.

- Guided Question: Why does the notice appear on top of the content? What happens if you swap the z‑index values?

The notice appears on top of the content box because z-values determine how "high" the elements would show on top of your output. For example, assigning a z-index value to .header with 1 and assigning a z-index value to .sidebar with 2 will make the side bar appear on top of the header. In this case, since notice was the only one to have a z-index in its css, it's put above everything else, which leads to it appearing on top of the content.

- Challenge: 
    * What changes that you have to do on the code that will position .notice box on the top right corner of the .content box? Please write the code on paper as well (both html and css on the part of .notice and .content).
To place the .notice box at the top-right of the .content box, set .content to position: relative and .notice to position: absolute, then use top: 0; right: 0;. This makes .notice position itself based on the boundaries of .content, so it stays inside the box at the top-right corner.

    * Try to change the position of .content to relative then to fixed. What do you observed each time?
When .content is position: relative, it stays in its normal place in the layout and .notice positions itself inside it. When changed to position: fixed, .content is removed from the normal flow and stays fixed on the screen even when scrolling, and .notice still stays at the top-right of .content, but now the whole container is pinned to the viewport.

    * What do you observe on about the effect of z-index on .notice and .content boxes?
The z-index controls which element appears on top. If .notice has a higher z-index than .content, it will appear in front; if it is lower, it can be covered by .content. This only works when the elements have a position property.

3. Please answer the following reflection questions (15 minutes)

    a. Could you summarize the differences between the CSS position values (static, relative, absolute, fixed)? 
    The static value is the default position for all HTML elements, where top, right, left, and bottom have no effect. The relative value is positioned in normal flow too but can be shifted relative to its original position; you can therefore assign values to top, left, right, and bottom to move it. The absolute value positions the element relative to its nearest ancestor based on the specifications or values one gives to the top, left, right, and bottom. Lastly, using the fixed value stays in its position relative to the viewport even when you scroll through the webpage.

    b. How does absolute positioning depend on its parent element?
    Absolute positioning depends on its parent element by applying the values for distance set within the css relative to the parent element. If there is no parent element, it will usually be applied to viewport.

    c. How do you differentiate sticky from fixed (you can research on sticky)?
    The sticky positioning behaves similar to the fixed positioning when scrolling. The difference between them is that using position: sticky will stick within its parent container when a defined offset/scroll threshold and then it will stay. or "stick" like when you use a position: relative value. When you scroll again, the element with position: sticky will also move alongside it.

    d. If you were designing a webpage for a school event, how might you use positioning to highlight important information? Please give concrete examples.
    I can use positioning to highlight important information by making the content boxes itself easier for the eyes to see and view. For example, I can use the relative positiioning for background information/trivia, while the most important ones can use fixed positioning. I can also use sticky in order to keep the text until a certain scroll threshold is met, so it can match with images/examples that comes with it. Lastly, I can also apply the z-index in order to format the way each information is presented by order. 
