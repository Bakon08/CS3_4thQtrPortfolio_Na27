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

### Step 1 (Static vs Relative):

- Add in css ```position: relative; top: 20px; left: 20px;``` to .sidebar.

- Guided Question: What changed compared to the default static positioning? Try to give different values to top and left or you can change it to bottom, right.
    - It first changes the position of the sidebar from static to relative. This means it can now be offset from it's normal positioning using lines of code such as top, left, right, and bottom.

### Step 2 (Fixed):

- Add in css ```position: fixed; bottom: 0; width: 100%;``` to .footer.

- Guided Question: What happens when you scroll the page? Why does the footer behave differently from position relative?
    - Adding that line of code to .footer moves the footer completely out of the normal document flow and positions it relative to the viewport. Bottom: 0 makes it stay glued to the bottom of the screen and width: 100% makes the footer span the full width. With relative, the sidebar moves but it will stay in the document flow. However with fixed, the footer stays locked to the viewport as you scroll the page.

### Step 3 (Absolute):

- Add in css ```position: absolute; top: 66px; left: 200px;``` to .content.

- Guided Question: What is the effect of position: absolute on an element? How is it different from fixed?
    - Position:absolute takes the element completely out of the normal document flow and positions it relative to its nearest positioned ancestor. So according to the code, it's supposed to position the element 66px down from the top of its references point and 200px to the right from the left of its reference point. When you scroll on the page, an absolutely positioned element scrolls with the content, but a fixed element stays locked to the screen.

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
    - This is because .notice has a z-index of 2, while content has a lower z-index of 1. Thus, the one with the higher z-index will be the one displayed in front. Following this logic, if you swap the values, the content box would appear on top of the notice box instead.

- Challenge: 
    * What changes that you have to do on the code that will position .notice box on the top right corner of the .content box? Please write the code on paper as well (both html and css on the part of .notice and .content).
    * Try to change the position of .content to relative then to fixed. What did you observe each time?
        - In relative, .notice stays positioned within .content, and scrolling moves both together. In fixed, .content becomes the reference point for absolute positioning, but if .content is fixed, the .notice will also appear fixed to the viewport since it's positioned relative to its parent.
    * What do you observe on about the effect of z-index on .notice and .content boxes?
        - I've observed that z-index only works on positioned elements. Since both .notice and .content are absolutely positioned, z-index controls which one appears on top. Higher z-index also layers on top of lower value ones. 

3. Please answer the following reflection questions (15 minutes)

    a. Could you summarize the differences between the CSS position values (static, relative, absolute, fixed)? 
        - Static is sort of like the default, it keeps elements in the document flow (top/bottom/right/left doesn't work on static). Relative has the element stay in the document flow but it can be offset using the code the doesn't work with static. Absolute removes the element from the document flow completely and positions it relative to its nearest parent. Fixed also has the element removed from the document flow and positions it relative to the viewport. The element also stays in place when scrolling.

    b. How does absolute positioning depend on its parent element?
        - Absolute positioning is relative to the nearest ancestor with position other than static. If no positioned parent exist, it is relative to the document body.

    c. How do you differentiate sticky from fixed (you can research on sticky)?
        - Fixed always stays locked to the viewport and doesn't move with scrolling, whereas sticky stays in the document flow normally until you scroll. It sticks to a specific position on the viewport (basically combining relative and fixed positions)

    d. If you were designing a webpage for a school event, how might you use positioning to highlight important information? Please give concrete examples.
        - For a header with the event logo that stays visible while scrolling, I'd use fixed. To make use of absolute positioning, I'd combine it with a high z-index to overlay important event info. Details like registration and dates are needed to offset accent graphics, thus I'd use relative. Finally, I'd use fixed positioning once more for a bottom footer than spans the entire viewport to show different sponsors. 
