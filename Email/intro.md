# Email templates

## Best practices

The best idea when working with email templates is to use the editor within Magento's admin. This section can be found at `system > transactional emails`.

### To create a new email template:

**From the transactional emails section**

1. Click "Add new template" in the top right
2. Under 'Load default template', choose the template you wish to base yours upon.
3. Click 'Load Template' to populate the remaining fields with the template's contents

### Best practices for styling templates

Unfortunately email design can be frustrating, and Magento doesn't do much to assist other than provide a nice interface. 
I recommend *testing* styles by adding them in the 'Template Styles' section, it's way faster than inline styling and 
great for rapid prototyping. However I would never do this in production environments, as inline styles are simply the 
best way to ensure that your emails appear consistent in all clients.


### Snoop around!

You're probably going to want to take a look at the template files to figure out what's going on. Some times it 
can be a pain to figure out what's going on and you may want to take a look at the files Magento is using to construct
these base templates. In some cases, where the templates are rendered through the use of variables, it is impossible to
add inline styles to these elements. Such examples I have encountered include:

* The credit card information block on orders

Take a look at the "locating_files.md" file within this directory for help with finding these files.


## Nice references for email design

1. [The Html Email Boilerplate](http://htmlemailboilerplate.com/): This is pretty awesome, everyone doing email design should
study this.