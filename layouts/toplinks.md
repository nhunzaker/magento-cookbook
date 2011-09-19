# Editing the top links in Magento

Note: This is pretty beta, I'll flesh this out at a later time

**In local.xml**

    <layout version="0.1.0">
        <default>
        
            <!-- Handle Top Links in Navigation -->
            <reference name="root">
                <reference name="top.links">
                    
                    <!-- Removes the Checkout cart link -->
                    <remove name="checkout_cart_link"/>
                    
                </reference>
            </reference>
            
        </default>
        
        
        <!-- Conditions for if a user is not logged in -->
        <customer_logged_out>
            <reference name="top.links">
                
                <!-- Remove the account link -->
                <action method="removeLinkByUrl"><url helper="customer/getAccountUrl"/></action>
                
                <!-- Adds a sign in link -->
                <action method="addLink">
                    <title>Sign In</title>
                    <url helper="customer/getLoginUrl"/>
                </action>
            </reference>
        </customer_logged_out>
        
        <!-- Conditions for if a user logged in -->
        <customer_logged_in>
        
            <!-- Adds a sign out link -->
            <reference name="top.links">
                <action method="addLink">
                    <title>Sign Out</title>
                    <url helper="customer/getLogoutUrl"/>
                </action>
            </reference>
        </customer_logged_in>
    </layout>

    