# Custom Variables

Custom variables allow you to store specific values within the administrative panel
in order to reference them within your theme files, email templates, etc...


## How to store them:

Custom variables can be created in `System > Custom Variables`


## How to use them:

Custom variables can be accessed in a number of ways:


### In template files:

#### Load variables by id (key value):

` $myCustomVar = Mage::getModel('core/variable')->load(1);`


#### Load variables by code name:

` $myCustomVar = Mage::getModel('core/variable')->loadByCode('my_custom_var');`


#### Access information:

##### Get the html:
`Mage::getModel('core/variable')->loadByCode('variable_code')->getValue('html')`

##### Get the text:
`Mage::getModel('core/variable')->loadByCode('variable_code')->getValue('text')`

##### Get the name:
`Mage::getModel('core/variable')->loadByCode('variable_code')->getName()`

##### Get the codename:
`Mage::getModel('core/variable')->loadByCode('variable_code')->getCode()`


## In email templates:

// Write something....