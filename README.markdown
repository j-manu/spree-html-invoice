SUMMARY
=======

This extension provides a "Print Invoice" button on the Admin Orders view screen which opens a prinatble html page with the order details.

You have to set up your computer for printing, or PDF generation. Off course, if you cave a mac that is as easy as pressing the print + save as pdf buttons.

If you need server-side pdf generation, use the spree-print-invoice extension.
 
INSTALLATION
============

For spree 0.7, ie using deface and rails 3.1. There is a brach 0.60 for an older version.
As I don't release gems, for better version control you may wish to clone the repository. 
If you have improvements, please send pull though.

1. To install you need to add the following lines to your Gemfile (no external dependendies)

    gem 'spree_html_invoice' , :git => 'git://github.com/dancinglightning/spree-html-invoice.git'

2. run bundler

    bundle install

3. Configure your logo and footer text or more. It's easy as it's html.

4. Enjoy!


Configuration
==============

1. Set the logo path preference to include your store / company logo.

    Spree::Config.set(:html_invoice_logo_path => "company-logo.png")
    
    Somewhere in your asset path

2. Add your own own footer texts to the locale. The current footer works with :footer_left , :footer_left2 and :footer_right, :footer_right2 where the 1 version is on the left in bold, and the 2 version the "value" on the right.

3. Override any of the partial templates. they are address, footer, totals, header, thanks , and the line_items. The whole tanks is wrapped in a thanks hook, so replace or add at will.

4. Set :suppress_anonymous_address option to get blank addresses for anonymous email addresses (as created by my spree_last_address extension for empty/unknown user info)

5. Enable packaging slips, by setting 

  Spree::Config.set(:html_buttons => "invoice,packaging_slip"  #comma separated list

 Use above feature for your own template if you want. For each button_name, define a subsection with header, print, and thanks, in your locale.


Extra
=====

There is now a receipt template, for a normal receipt printer (ie 70mm). This works for us, but is not quite finished.

Barcodes have gone to their own package spree-product-barcodes a(and they are starting to work too)

Contributions welcome

Torsten