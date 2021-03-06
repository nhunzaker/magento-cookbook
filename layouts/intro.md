# Layouts

## The cardinal rule: Use local.xml. Always. No really.

Every element that has been configured in a [layout].xml file can be edited within a special document called "local.xml". 
Simply place this file within `[your_theme]/layouts/` and start writing some XML (Please try not to vomit in the process).

For example, let's say you want to add Modernizr to our site. You could throw it in the head.phtml file, but that will require duplicating the
head.phtml template file and dropping it into `[theme_directory]/template/page/html/`. This means that if the Magento team makes an update to this file, it will remain
in it's older version until you make the change yourself.

I don't know about you, but given the massive file structure of Magento that is way more work than I care to do.

###To reiterate:

- The more files you add to your theme, the more items you have to support
- The more files you modify, the greater risk you have to break something (which is often mindnumbing to fix, particularly in Magento)

### The pros:
- A single file to edit
- A single file to debug
- Less hassle keeping up with of Magento

### The cons:
- You'll need to develop better understanding of Magento's layout.xml system (hopefully I can help)
- These files can become cumbersome for projects which require heavy modification


Having said that, I genuinely feel that using local.xml is the way to go. Here's a quick sample of how I do it:

<!-- local.xml -->
<layout version="0.1.0">

    <default>
    
        <reference name="head">
        
            <!-- Modernizr (To assist with browser compliance and overall development health) -->
            <action method="addItem">
                <type>skin_js</type>    
                <name>javascript/modernizr.js</name>
            </action>
            
        </reference>
        
    </default>
    
</layout>

If you've read through that properly, a few red flags were probably raised in your mind. The code above runs an action to add an item to the head of the document (for all pages)
which will find the modernizr.js script found in skin/[your_theme]/javascript. We set the <type> attribute to "skin_js" to tell Magento to look here, rather than the js folder found in the root of your installation.