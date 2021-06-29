# Vitalsource-Casebook-Font-Fix
CSS (used with Stylus extension) to make the text larger in Vitalsource textbooks with broken formatting

### Instllation
Install the [Stylus extension](https://add0n.com/stylus.html)

Click [here](https://github.com/Lithovox/Vitalsource-Casebook-Font-Fix/raw/main/vitalsource.user.css) to install the style.

### Editing
This is meant for people with no CSS experience, i.e. the average user, and possibly whoever at Vitalsource decided that formatting each line in a textbook using a different class unaffected by the user's preferences was a good idea.

#### Adding new text classes
Since Vitalsource uses so many different classes to refer to text, it's inevitable that some text doesn't get resized. To make the code automatically resize additional types of text:

- Right click on the text you want resized. Click "Inspect".  
- In the inspection pane that pops up, look in the top left pane for the highlighted line of code.   
- This line should begin with "<p class=". If it does not, find the nearest line of code above the highlighted one that does begin that way.  
- At this point copy the text inside the first set of quotes in that line. For example, if the line of code begins "<p class="className"", copy "className".  
- Paste the following code block just below the line in the style which says "Add additional classes here", replacing className with the text that you copied before.

      .className {
          font-size: var(--myfontsize) !important;
          line-height: var(--mylineheight) !important;
      }

#### Changing the font size
Change the values of --myfontsize and --mylineheight to your preferred values. To make a certain type of text have a different font size, replace the "var(--myfontsize)" or "var (--mylineheight)" for that class with an exact value; for example:

    .box-para {
        font-size: 12pt !important;
        line-height: 12pt !important;
    }
