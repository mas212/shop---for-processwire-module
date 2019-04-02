1.download zip shop for processwire module
2.Install Shopping Cart
3.Add sc_price field to your product template (can be added into multiple templates)
4.Edit few of your products and give them price
5.Add get("ShoppingCart")->renderAddToCart(); ?> to your product template. If you don't like the markup it generates, you can put the wanted markup directly into template.
6.At this point you can add products to your cart. If you want to show somewhere how many products there is in your cart, do this in your template: echo $modules->get('ShoppingCart')->getNumberOfItems(false); // Total number of items or echo $modules->get('ShoppingCart')->getNumberOfItems(); // Different items only, ie. qty doesn't matter
7.How about the actual cart page, where you can see all the products in your cart? Add this to any of your templates where you want to see it: example
<?php $page->get("ShoppingCart")->renderCart(); ?>
<?php $page->get("ShoppingCheckout")->renderCheckout();?> 
8.If you need to customize the fields etc, you can do that in certain degree by editing the ShoppingCheckout module. Also, pw-shop is fully multilang, so you probably do want to translate the module files.
9.Checkout doesn't let you go through unless you install at least one payment method. So do so if you want to continue.
10.You might want to show checkout steps (kind of a breadcrumb). That is possible with yet another module. Just put this to your sc-checkout template: example 
<?php $page->get("ShoppingStepsMarkup")->render(); ?>
