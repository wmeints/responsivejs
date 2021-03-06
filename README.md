Responsive.JS
============

Use this jQuery plugin to enrich a responsive design with Javascript rules.
A responsive design is often build using CSS media queries. However these are 
often not enough to make the website work for the full 100%.

Sometimes you want to switch CSS classes on elements based on the available
width on the page. For example, switch a span9 for a span12 within a website
based on the bootstrap gridsystem, because you want the article content to be
full width on a tablet layout instead of being two columns. With CSS 
mediaqueries you can't do this.

Usage
-------------
To use the plugin, include it in your HTML page right after the jQuery script.
The plugin uses jQuery for various event binding operations, so it is required
to be loaded first.

To create a new rule, simply define a rule like in the sample below.

    $.responsive.rule(0,479, function() {
        // This rule gets called when the resolution of the page
        // is between 0 and 480px
    });
    
    $.responsive.rule(1200,0, function() {
        // This rule gets invoked when the layout is 1200px
        // or wider.
    });
    
Rules are valid when the current width is greater or equal to the minWidth of
the rule or when the current width is smaller or equal to the maxWidth of the 
rule. When you specify 0 for one of the bounds of the rule, that bound is 
disabled. Essentially, you're telling the plugin that you don't care about the
min or max width for that rule.

Advanced usage: Enter/Exit conditions
-------------------------------------
In normal scenarios you should use just a single callback per rule. However 
there are situations where it can be useful to have a callback for when the
screen is coming in range and a different one when the screen size is getting
out of range of the rule.

You can specify both enter and exit callbacks for a rule with the following
syntax:

    $.responsive.rule(1000,1100, {
		enter: function() {
		
		},
		exit: function() {
		
		}
	});
	
The responsive library will invoke the enter callback once when the screen
size comes within range of the rule. The exit callback will be called once
the screen size gets out of range of the rule. 

Problems/questions
---------------------
Feel free to post issues or fork the sources if you want things added or 
changed.