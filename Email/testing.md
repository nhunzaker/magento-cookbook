# Testing Emails

Testing emails in Magento can be a bit of a pain. Here's what I've come up with:

##Testing New Orders emails

Most of the time when you test a new order email template, it will be in the development environment (we don't want to purchase anything from our 
clients sites on accident -- do we?). The easiest way that I can find to do this is by doing the following:

1. Create a new order with the Magento Admin:
    1. Go to the orders menu at `Sales > Orders`
    2. Click "Create New Order" in the top right
    3. Follow the process for generating a new order, it's rather straightforward
2. Send an email:
    1. Go to the orders menu at `Sales > Orders`
    2. Click on the order you just created
    3. In the top right, there will be a "Send Email" button, click it.
3. Wait…

I've found this to be the most expeditious method of testing, as it is the most replicable and avoid the hassle of the checkout process on the frontend.