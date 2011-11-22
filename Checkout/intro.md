# Checkout Recipes

## The Cart Summary/Mini-Cart (In the header on Enterprise Edition)

### Configure Settings

#### You want to: 

1. Edit the number of items which display in the cart summary
2. Disable/Enable the cart

#### The solution:
Both settings can be configured with in the Magento admin at the following location:

`System > Configuration > Checkout (Under Sales Sidebar) > Shopping Cart Sidebar`

This is called the sidebar because it will also display on the cart page. Why they don't clarify, I have no idea.

### Redirect back to cart page after deleting an item

#### You want to:

1. Return the user back to the cart after successfully deleting an item from his/her cart.


#### The solution

Currently, the only solution I can come up with is to edit the core files (gross.... I know). I have had success by doing the following:

- Open the `CartController.php` file, found in `app/code/core/Mage/Checkout/controllers/CartController.php`

- Go to roughly line 413, it should be within a function called `deleteAction()`. It should state the following: 

  ```
  $this->_redirectReferer(Mage::getUrl('checkout/'));
  ```

- Change this line to the following:

  ```
  $this->_goBack();
  ```

This will make it so that deleting an item will, by default, return the user to the location they originally clicked the button.