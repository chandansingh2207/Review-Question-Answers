
How do you implement multilingual stores?
==========================================
Use

Shopify Markets
Language resources (locales)
Translation apps or APIs if required

Example

{{ 'general.search' | t }}
Interview Answer

I enable multiple languages using Shopify Markets and translation resources. I store translatable text in locale files and use Liquid translation filters. I also verify translated URLs, SEO metadata, and currency settings for each market.


🛒 Shopify 2.0 (Official)
=============================

Shopify 2.0 refers to Online Store 2.0, officially released by Shopify in 2021.


✅ Shopify 2.0 Main Features of 
==================================

Sections Everywhere
Earlier, sections were only available on the homepage.
In 2.0, you can use sections on all pages (product, collection, etc.).

App Blocks
Apps can add blocks directly inside themes without editing code.

JSON Templates
New .json template system instead of only .liquid.

Better Theme Customizer
Drag-and-drop editor improved.

Metafields without code
You can add custom fields from admin panel.

Example of 2.0 theme:
Dawn (Official Shopify 2.0 theme)


Dawn Theme  == Version 15.4.1
===================================
December 05, 2025
Dawn 15.4.1 introduces improvements for performance monitoring.

🖼️ 1. Minimal, Product-Focused Design

Dawn uses a clean, modern layout that highlights your products with large, high-resolution images and simple typography — great for visual storytelling and letting the products take center stage.

⚡ 2. Fast Performance & Lightweight

Built with minimal JavaScript and efficient CSS, Dawn loads very quickly and performs well on all devices, improving SEO and customer experience.

🧱 3. Flexible Sections & Blocks (Online Store 2.0)

You can add, reorder, and customize page sections across all pages (home, product, collection, blog, etc.) without coding, thanks to OS 2.0 support.

🔍 4. Enhanced Product Discovery

Includes features like enhanced search, filtering and sorting options, sticky header navigation, and a mega menu to help customers find products faster.

🛍️ 5. Merchandising Tools

Supports product merchandising elements such as color swatches, image galleries, zoom, lookbooks, product videos, and size charts — ideal for showcasing offerings.

🛒 6. Marketing & Conversion Features

Built-in tools like promo banners, recommended products, cross-selling sections, blogs and cart features (e.g., cart notes and quick buy) help boost engagement and sales.

📱 7. Mobile-First & Responsive

Designed to look and work smoothly on mobile devices, ensuring a great experience for most online shoppers.

🔧 8. Seamless Shopify Integration

Works smoothly with Shopify’s inventory, checkout, and app ecosystem — app blocks allow apps to plug in cleanly without manual code edits.

Install Shopify CLI Version 3.0 : 05-03- 2024
==============================================
🛒 Create a New Shopify Theme Project

Using Shopify CLI

✅ Create a new theme

shopify theme init my-theme

This will create a new theme project (based on Dawn by default).

✅ Go inside the folder
cd my-theme

✅ Start development server
shopify theme dev

This will:
Connect to your Shopify store

Upload theme
Give you a preview URL
Enable live reload


🛒 Download Shopify Theme to Local

✅ Step 1: Install Shopify CLI (if not installed)

Check version:

shopify version

If not installed:

npm install -g @shopify/cli @shopify/theme

✅ Step 2: Login to Your Store

shopify login --store your-store-name.myshopify.com

✅ Step 3: Pull (Download) Theme
📥 Download Live Theme

shopify theme pull

This downloads the currently published (live) theme.


Shopify Cli ****  Version 3.51.0 available!
==============================================
A tool we use in the terminal (like Command Prompt or VS Code) to work with Shopify themes and apps.
Makes it easier to develop, preview, and deploy your Shopify store.

What it does
=================
Theme development – Start a new theme, pull/push theme code.
Preview changes – See your updates live without uploading manually.
App development – Create and test Shopify apps.
Automation – Run commands instead of clicking in the Shopify Admin.


Connect with store:
======================
shopify login --store your-store-name.myshopify.com    #A browser window will open → log in with your Shopify account.

shopify whoami   #This will show the store and account you’re connected to.



Example Commands
===================
shopify theme init       # Create a new theme
shopify theme serve      # Preview theme locally
shopify theme push       # Upload changes to the live store
shopify app create       # Start a new app


| Command                     | What It Does                                            | Example                           |
| --------------------------- | ------------------------------------------------------- | --------------------------------- |
| `shopify theme init [NAME]` | Create a new theme                                      | `shopify theme init my-new-theme` |
| `shopify theme serve`       | Preview theme locally in your browser                   | `shopify theme serve`             |
| `shopify theme push`        | Upload your local theme changes to Shopify              | `shopify theme push`              |
| `shopify theme pull`        | Download theme files from Shopify to your local machine | `shopify theme pull`              |
| `shopify theme check`       | Analyze theme for errors, warnings, and best practices  | `shopify theme check`             |
| `shopify theme open`        | Open your theme in the Shopify admin panel              | `shopify theme open`              |
| `shopify theme remove`      | Delete a theme from your store                          | `shopify theme remove`            |


Shopify CLI for Windows : The requirements to install and run Shopify CLI depend on our operating system:
-----------------------------------------------------------------------------------------------------------
1. Node.js 18 or higher.

2. Ruby + Devkit 3.0, installed using RubyInstaller for Windows
(select the MSYS2 component and the MSYS2 base installation option)

3. Git

4. Bundler 2.3.8 or higher


Shopify Cli Features:
=======================================================
Initialize a new theme using Dawn as a starting point.

Safely preview, test, and share changes to themes using development themes.

Shopify CLI accelerates our theme development process with the following features:

Automatically refresh a page on file change, when previewing a theme or hot reload CSS and section changes.

Push and publish themes from the command line.
================================================

shopify theme serve              # Preview theme locally

shopify theme push               Push theme changes to a store

shopify theme pull               Pull a live theme from our store

shopify theme publish            Set a remote theme as the live theme.

Work on multiple themes using environments.

Run Theme Check on our theme:

shopify theme check    === The CLI will scan your theme and list any errors or warnings. 

shopify theme check sections/header.liquid  === check specific file for error

Theme Check will analyze our theme and provide a report of any issues or suggestions. 
Review the output to see if there are any issues you need to address.

Navigate to our Shopify theme directory. If our theme is downloaded locally, you can use the cd command to go to that directory. For example:

cd path/to/our/theme

theme-check  ===== Command

Shopify Cli Requirements:
---------------------------------------------------
You've installed Node.js 18 or higher.

You've installed a Node.js package manager: either npm, Yarn 1.x, or pnpm.

You've installed Git 2.28.0 or higher.

You're using the latest version of Chrome or Firefox.

Setting Up our Development Environment
----------------------------------------
Shopify Commends for CLI

Command                        Description

shopify version                Check the installed version of Shopify CLI
shopify login                  Authenticate with our Shopify account
shopify logout                 Log out from the current Shopify account
shopify whoami                 Display the current authenticated user

Setup Commands

Developing and Managing Shopify Themes
-----------------------------------------

Command                                        Description
------------------                           -------------------------                   

shopify theme init                               Create a new theme

shopify theme dev --store {store-name}           To serve our theme, run the following command, where --store represents the name of the store that you want to use to 
                                                 preview our theme: 

shopify theme serve              It allows you to preview and test changes to our theme before deploying them to our live Shopify store. 

shopify theme push               Push theme changes to a store

shopify theme pull               Pull a live theme from our store

shopify theme publish             Set a remote theme as the live theme.

shopify theme check              Validate our theme with Shopify’s requirements

shopify theme open                Opens the preview of our remote theme.

shopify theme dev                 Uploads the current theme as a development theme to the connected store, then prints theme…

shopify theme info                Print basic information about our theme environment.

shopify theme delete              Delete remote themes from the connected store. This command can't be undone.

shopify theme list                Lists our remote themes.

shopify theme package             Package our theme into a .zip file, ready to upload to the Online Store.
 
shopify theme rename              Renames an existing theme.

shopify theme share               Creates a shareable, unpublished, and new theme on our theme library with a randomized name.
 
shopify upgrade                   Upgrade the Shopify CLI.

shopify version                   Shopify CLI version.

Assign variable is shopify
===========================

{% assign variable_name = value %}

Schema in Shopify:
===================
In simple words:

Schema in Shopify is used so that store owners can dynamically change the content of a section from the theme editor, without touching the code.

Whatever you define in schema → settings & blocks becomes editable in the admin.


Schema is a set of instructions to write in a section file that tells Shopify:

“What can the store owner customize here?”

It is written in JSON between

{% schema %} ... {% endschema %}

3 main parts:
===============

settings → Single options like text, images, checkboxes.

blocks → Repeatable items like slides or FAQs.

presets → Default setup so it shows in “Add section” panel.



{% schema %}

{
  "name": "Banner Section",
  "settings": [

    { 
        "type": "text", 
        "id": "title", 
        "label": "Banner Title"
     },

     { "type": "image_picker", 
       "id": "banner_img",
       "label": "Banner Image"
     }

  ],

  "blocks": [
    {
      "type": "button",
      "name": "Button",
      "settings": [
        { 
        "type": "text", 
        "id": "btn_text", 
        "label": "Button Text" 
        },

        { 
        "type": "url", 
        "id": "btn_link", 
        "label": "Button Link" 
        }
      ]
    }
  ],

  "presets": [{ "name": "Banner with Button" }]
}

{% endschema %}


############################Shopify Cheat Sheet###########################################
==================================================================================
SHOPIFY LIQUID CHEAT SHEET (COPY FRIENDLY)

{% assign my_variable = 5 %}

OUTPUT & LOGIC
===================
{{ variable }}
→ Output value
Example: {{ product.title }}

{% logic %}
→ Run logic
Example: {% if product.available %}

{%- -%}
→ Remove whitespace (both sides)

{{- -}}
→ Trim output whitespace

CONDITIONS
===================

if
Example: {% if product.available %}

elsif
Example: {% elsif product.price > 100 %}

else
Example: {% else %}

unless (opposite of if)
Example: {% unless product.available %}

case / when

Example:
{% case product.type %}
{% when 'Shoes' %}

LOOPS
=======================
for
Example: {% for product in collection.products %}

break
→ Stop loop

continue
→ Skip current iteration

limit
Example: {% for product in collection.products limit: 4 %}

offset
Example: {% for product in collection.products offset: 2 %}

FORLOOP PROPERTIES
===============================
forloop.index → 1-based index
forloop.index0 → 0-based index
forloop.first → true if first
forloop.last → true if last
forloop.length → total items
forloop.rindex → reverse index

VARIABLES
=====================
assign
Example: {% assign price = product.price %}

capture
Example:

{% capture name %}
John
{% endcapture %}

It creates a variable called name
and stores the text inside it.

IMPORTANT OBJECTS
=======================
product.title
product.price
product.available
product.variants

collection.title

cart.total_price

customer.first_name

shop.name

blog.title
article.title

FILTERS
======================
money
Example: {{ product.price | money }}

upcase
downcase
capitalize

strip_html

truncate
Example: {{ product.title | truncate: 20 }}

truncate: 20
→ Cuts the text after 20 characters
→ Adds ... at the end automatically

product.title = "Premium Cotton Oversized T-Shirt"
 {{ product.title | truncate: 20 }}

 Output
 Premium Cotton Ove...

date
Example: {{ article.published_at | date: "%B %d, %Y" }}

json

escape

img_url
Example: {{ product.featured_image | img_url: '500x' }}

PAGINATION
=====================
{% paginate collection.products by 12 %}
=== It enables pagination for products in a collection
and shows 12 products per page.

paginate.pages
paginate.current_page
paginate.next

FORMS
=================
{% form 'product', product %}
{% form 'cart' %}
{% form 'contact' %}
{% form 'customer_login' %}

SECTIONS (SHOPIFY 2.0)
==========================
section.settings.title

{% for block in section.blocks %}

block.settings.text

{% schema %}
JSON settings here
{% endschema %}

{% render 'snippet-name' %}




1️⃣ {{ }} → Output (Print Something)

Called: Output tags

Used to display data on the page.

| Type         | Used For            | Affects Page Design?  | Affects Logic? |
| ------------ | ------------------- | --------------------- | -------------- |
| `{{ }}`      | Showing data        | Yes (content visible) | No             |
| `{% %}`      | Running logic       | Indirectly            | Yes            |
| `-` (hyphen) | Removing whitespace | Yes (clean HTML)      | No             |


Pagination:
============
{% paginate collection.products by 12 %}

  {% for product in collection.products %}
    {{ product.title }}
  {% endfor %}

  {{ paginate | default_pagination }}

{% endpaginate %}

🔹 What Happens Internally

When you use paginate, Shopify creates a paginate object.

You can access:

paginate.pages → total number of pages

paginate.current_page → current page number

paginate.next → next page link

paginate.previous → previous page link

Shopify PLans:
================
| Plan     | Starting Price (USD/month) | Paid Anually 
| -------- | -------------------------- |------------------------------
|                      |
| Basic    | ~$39                       |  $29 /month
| Grow     | ~$105                      |  $79 /month
| Advanced | ~$399                      |  $299 /month
| Plus     | ~$2000+ (custom pricing)   |  $2300 /month

Basic
Most Popular
For solo entrepreneurs
=======================
Standout features

10 inventory locations
24/7 chat support
In-person selling by phone or POS device

Grow
For small teams
=======================
5 staff accounts
Standout features

10 inventory locations
24/7 chat support

In-person selling by phone or POS device

Advanced
For global reach
=======================
10 inventory locations
Standout features

10 inventory locations
Enhanced 24/7 chat support
Local storefronts by market
15 staff accounts
In-person selling by phone or POS device


Plus
For complex businesses
=========================
Unlimited staff accounts
Standout features


200 inventory locations
Priority 24/7 phone support
Local storefronts by market

Fully customizable checkout
Up to 200 POS Pro locations
Sell wholesale/B2B


📌 PLAN SELECTION GUIDELINES
=================================
Shopify Starter → If you only want to sell via social messaging or links.

Basic → If you want a full website + online store with essential features.

Shopify (Grow) → If you’re growing and need better reporting + staff access.

Advanced → For data-driven stores and optimized checkout + shipping.

Plus → For enterprise-level selling, wholesale/B2B, custom checkout, scale.


Shopify Plus Features:
========================


| Feature                        | Shopify Plus Benefit                                   |
| ------------------------------ | ------------------------------------------------------ |
| Support                        | Dedicated migration & strategy support                 |
| Staff Accounts                 | Unlimited users with custom permissions                |
| Store Management               | Centralized multi-store admin interface                |
| Checkout Customization         | Full control via scripts or editor                     |
| Automation & Event Tools       | Shopify Flow, Launchpad, Shopify Functions             |
| API Access                     | Higher limits + exclusive endpoints                    |
| B2B/Wholesale Integration      | Built-in support without third-party tools             |
| International Tools            | Shopify Markets, Avalara, omnichannel sell integration |
| Advanced Reporting & Audiences | Custom analytics & ad targeting via Shopify Audiences  |


To hide products with quantity = 0 from our Shopify storefront, 
=================================================================
{% for product in collection.products limit: 5 %}
  {% if product.available %}
    {{ product.title }}
  {% endif %}
{% endfor %}

✅ product.available is 'true' if the product has at least one variant in stock.


✅ For Basic/Shopify/Advanced Plans
========================================
We're limited to visual customizations only:

🎨 Steps to Edit Checkout Branding:
Go to Shopify Admin > Online Store > Themes

Click Customize
In the theme editor, from the top dropdown, choose “Checkout”

We can customize:
Logo
Banner image
Typography
Colors
Checkout style

⛔ We cannot add custom HTML, JavaScript, or extra input fields on the checkout with these plans.

How We can implement like amazon single product purchase from cart in shopify?
================================================================================
Shopify allows us to link directly to the checkout with one product using a special URL format:

/cart/{variant_id}:1

https://yourstore.myshopify.com/cart/1234567890:1

<a href="/cart/{{ item.variant_id }}:1" class="btn">
  Buy This Item Now
</a>


How many sections,block can we add on a page?

✅ Max 25 sections per page (template)

✅ Max 50 blocks per section



Blocks:
=======
Blocks in Shopify are used to make repeatable, flexible content inside a section.

You can only use blocks inside a section, not standalone.

Think of blocks like small pieces that a store owner can add, remove, or reorder inside a section from the theme editor
without touching the code.

🔹 Key points about blocks
Belong to a section → You can only use blocks inside a section, not standalone.
Repeatable → Merchants can add multiple blocks (e.g., slides, FAQ items, buttons).
Reorderable → In the theme editor, they can drag & drop blocks to change order.
Each block has its own settings → Like text, image, link, icon.

🔹 Key Things About Blocks

type → Defines the type of block (like "question", "slide", "testimonial").
settings → Each block can have its own input fields (text, image, link, richtext, etc.).
max_blocks → Restricts how many blocks a merchant can add.
presets → Makes the section show up in the Theme Editor as a pre-configured block.

🎯 Common Setting Types
"text"
"textarea"
"image_picker"
"url"
"checkbox"
"range"
"select"
"color"


✅ Presets in Shopify (Simple Explanation)
=============================================
In Shopify, presets are used to make our section available in the Theme Editor.

Presets = Makes section visible in "Add section"

👉 Without presets, our section will NOT appear in “Add section”.

Example:
============
If you add a “Hero Banner” section:

A preset might already include:
Sample heading text
A placeholder image
Button text like “Shop Now”

So instead of starting from blank, you get a pre-designed layout instantly.

🧱 Simple Example

{% schema %}

{
  "name": "Custom Banner",
  "settings": [],
  "presets": [
    {
      "name": "Custom Banner"
    }
  ]
}

{% endschema %}

🎯 What Preset Does?

When you go to:

Online Store → Customize → Add section

You will see:

Custom Banner

That name comes from:

"presets": [
  { "name": "Custom Banner" }
]

🧠 Very Simple Meaning

Schema = Section settings
Presets = Makes section visible in "Add section"

Think like this:

Preset = Default template of your section

📌 Real Example (Like Dawn Theme)

In the Dawn theme, every section has presets so merchants can add them easily from the customizer.


Example:
=========

<div class="custom-hero">
  <h1>{{ section.settings.heading }}</h1>
  <p>{{ section.settings.subtext }}</p>
  
  {% if section.settings.button_label != blank %}
    <a href="{{ section.settings.button_link }}" class="btn">
      {{ section.settings.button_label }}
    </a>
  {% endif %}
</div>

{% schema %}
{
  "name": "Custom Hero Section",
  "settings": [
    {
      "type": "text",
      "id": "heading",
      "label": "Heading",
      "default": "Welcome to our store"
    },
    {
      "type": "textarea",
      "id": "subtext",
      "label": "Sub text",
      "default": "Tell your brand story here"
    },
    {
      "type": "text",
      "id": "button_label",
      "label": "Button Label",
      "default": "Shop Now"
    },
    {
      "type": "url",
      "id": "button_link",
      "label": "Button Link"
    }
  ],
  "presets": [
    {
      "name": "Custom Hero Section"
    }
  ]
}
{% endschema %}



Shopify Theme Development requirement with folder structure
============================================================
(LT) (SSC) (AL)

Layout
Templates

Sections
Snippets
Config

Assets
Locales

1. Layout (theme.liquid is the layout file)
============================================
The layout refers to the structure and arrangement of the content on our online store. 

In Shopify, a Layout is the main outer structure of your website.

The layout refers to the structure and arrangement of the content on our online store. 
It's typically controlled through a combination of templates, themes, and liquid files. 

The layout refers to the structure or design of a Shopify store's pages. This typically involves defining how different sections (like headers, footers, and product grids) are arranged on the page. It's where you define the general skeleton or framework that will hold our content and assets. Layouts in Shopify are usually controlled through Liquid templates.

Think of it like this:
🧱 Layout = The frame of our webpage
🧩 Templates & Sections = The content inside the frame

theme.liquid:
=============
📄 What is Inside theme.liquid?

This is where page content loads.

In Shopify, theme.liquid is the main layout file of your theme. 
It acts like the skeleton (base structure) of every page on your store.

content_for_header → Scripts, meta tags, Shopify apps
content_for_layout → Page content (home, product, cart, etc.)

Example:

<!DOCTYPE html>
<html>
  <head>
    {{ content_for_header }}
  </head>
  <body>
    
    {% section 'header' %}

    {{ content_for_layout }}

    {% section 'footer' %}

  </body>
</html>

✅ {{ content_for_layout }}

This is where page content loads.

Example:

If you open product page → product template loads here

If homepage → index template loads here


2. Templates
=============
A Shopify template is a ready-made design for our online store. 
It controls how our store looks (colors, fonts, layout) and sometimes how it works (menus, product display, features).

Think of it like a clothing style for our website — you choose one that fits our brand, and our store will look professional without needing to design it from scratch.

3. Sections  {% section 'section-name' %}
==========================================
Sections in Shopify are building blocks we use to create and customize our store pages.

👉 Sections are the parts we can add, remove, or rearrange in the Theme Editor.

Each section controls a part of the page — like:

Announcement Bar 
A banner at the top
A slideshow of images
A list of products
A section with text or video
A testimonial block
A faq section

Examples of sections:

Header
Slideshow
Featured Products
Testimonials
Footer

You can drag and drop these sections to change the layout without coding. It’s like using blocks in a puzzle to build our web page.

{% section 'custom-ingredients' %} === include section inside templates.

4. Snippets {% include 'snippet-name' %}
=========================================
 Snippets are reusable pieces of code in Shopify that can be inserted into templates or sections.

 They're typically small bits of HTML, CSS, JavaScript, or Liquid that can be used throughout the store. For instance, you might have a snippet for a product carousel or for a common footer structure, which you can easily include in multiple places to maintain consistency across the site.

{% include 'snippet-name' %} === To include the snippet inside a template (e.g., product.liquid):

Section and Snippet Difference:
===============================

| Feature                        | **Section**                       | **Snippet**                      |
| ------------------------------ | --------------------------------- | -------------------------------- |
| Editable in theme editor       | ✅ Yes                             | ❌ No                             |
| Can have schema/settings       | ✅ Yes                             | ❌ No                             |
| Purpose                        | Page block (layout/content block) | Reusable small code piece        |
| Folder location                | `/sections`                       | `/snippets`                      |
| Can be added via JSON template | ✅ Yes                             | ❌ No (must be rendered manually) |


Section
=========
In Shopify, a Section is a customizable content block that you can add, remove, or rearrange in the Theme Editor.

A section is a big, standalone part of a page (like a homepage banner, FAQ, or featured products).

Can have blocks inside it (repeatable items).

Can be added, removed, or rearranged directly in the Shopify Theme Editor.

Usually stored in: sections/your-section.liquid.

{% section 'your-section' %}

Snippet
=========
A snippet is a small reusable piece of code (like a button, icon, or product card).
Cannot be added directly in the Theme Editor.

You include it inside a section, template, or another snippet using {% include 'snippet-name' %}.
Usually stored in: snippets/your-snippet.liquid.


5. Config : 
============
Stores global theme settings like colors, fonts, logos, and layout options.
In Shopify, config usually refers to the theme configuration, which controls the settings and structure of your theme.


The config folder in Shopify stores holds configuration files that define settings and preferences for the store. 
It contains files that dictate things like the store's theme settings, schema definitions, and various other settings that control how the store behaves. 

For example, the settings_schema.json file defines the customization options available in the theme editor.

Diff between settings_schema.json and settings_data.json


settings_schema.json → Form structure

settings_data.json → Filled form values

settings_schema.json
======================
Purpose: Defines what settings the merchant can configure in the theme editor.

Analogy: It’s the form definition — what fields show up, their types, labels, defaults, groups, etc.

Example types: text, textarea, select, checkbox, color, image_picker, etc.

settings_data.json
=====================
Purpose: Stores the current values the merchant has chosen (overrides of the defaults).

Analogy: It’s the filled-in form — what the merchant actually set.


6. Assets
===========
Assets refer to the various files (images, CSS, JavaScript, fonts, etc.) used to design and build a Shopify store. These assets are typically stored in the assets folder of the theme. They control the visual and interactive elements of the site, such as styles, animations, and images.

7. Locales
=============
Locales in Shopify represent the different languages and translations of our store.

This feature allows you to create a multilingual store by storing language-specific translations in the locales folder. The translations can be applied to various strings in our store, such as buttons, product descriptions, and checkout text, based on the customer's selected language.



How to include css & js file ?
---------------------------------
{{ 'custom.css' | asset_url | stylesheet_tag }}

{{ 'script.js' | asset_url | script_tag }}



If you need to include external CSS or JavaScript files (e.g., from a CDN), you can directly link to them without using Liquid:

<link rel="stylesheet" href="https://example.com/custom.css">
<script src="https://example.com/script.js"></script>

Dawn Theme: (Json based template), Current version of Dawn Theme Last Version 15.3.0 ,updated Mar 3, 2025


Shopify 2.0 Features: (Json Based Templates)
================================================
JSON-based templates give you more flexibility. 
We can add or remove sections on any page — not just the homepage.

Dynamic Sections on All Pages
Drag-and-drop in Theme Editor
Non-technical merchant friendly
Faster Development
Reusability
Version-safe & Upgrade-friendly


1. Sections on Every Page
=========================
Before: Only the homepage could have customizable sections.
Now: Any page (home,product, collection, about, etc.) can have drag-and-drop sections.

Here are the key features of Shopify 2.0:

Sections Everywhere (Add/move/remove section on all pages):

Customizable Layouts: You can add, move, and remove sections on all pages, not just the homepage. This allows for greater customization of the entire site.
Dynamic Content: Create custom templates for specific products, collections, and pages, enabling unique layouts and designs.

2. Theme Architecture and JSON Templates
========================================
JSON-based Themes: The new architecture uses JSON templates, allowing for dynamic sections on each page.

Reusable Blocks: Create sections and blocks that can be reused across different parts of the site, improving design consistency.

3. Metafields: Using metafield we can add custom fields to products.
====================================================================
Enhanced Metadata: Shopify 2.0 allows you to define and manage metafields directly from the Shopify admin, without needing third-party apps.

{{ product.metafields.fieldname }}

{{ collection.metafields.fieldname }}

Custom Data: You can add custom fields to products, collections, and other entities, enabling more detailed information and advanced customization.

4. Theme App Extensions:

App Integration: Apps can now integrate directly with themes, allowing them to create custom blocks and sections. 
This makes it easier to install and update apps without modifying theme code.

Isolation of App Code: App-related code is isolated, reducing conflicts with theme updates and other apps.

5. Developer Tools and Workflow:

Shopify CLI: The command-line interface for Shopify has been enhanced, making it easier for developers to build and test themes.

Theme Check: This tool helps identify potential issues in theme code, improving theme quality and consistency.

6. Storefront Content Management

More Content Control: Merchants have greater control over the layout and content of their storefront, without requiring as much 
custom development.

Drag-and-Drop Editing: The updated theme editor allows for intuitive drag-and-drop customization, simplifying the design process.

7. Performance Improvements

Optimized for Speed: Shopify 2.0 themes are designed for better performance, with optimizations for fast loading times and better SEO.

Improved Accessibility: Enhanced accessibility features ensure themes meet industry standards for users with disabilities.

These features collectively offer merchants and developers a more flexible, customizable, and scalable platform, enabling a broader range of design options and more seamless integrations with apps and custom data.



Dawn theme (Free to Use - Json based template):  Current version of Dawn Theme Last Version 15.3.0 ,updated Mar 3, 2025
----------------------------------------------

Feature of Dawn Theme:  Dawn is developed by Shopify. Free to use .  Current version of Dawn Theme Version 15.3.0 ,updated Oct 3, 2024
----------------------

Dawn is developed by Shopify and is designed to be a showcase for the platform's latest features, especially those introduced with Online Store 2.0.

Free to Use: Dawn is a free theme available to all Shopify users. 
It provides a great starting point for those who are new to Shopify or don't want to invest in a paid theme.

Easy to manage & customize.
Product search, filtering, and recommendations: 

Quick buy: Add products to their cart without leaving their current page, streamlining the purchasing process and reducing friction.

Product search, filtering, and recommendations: Built-in product discovery features allow customers to browse our catalog easily and find what they’re looking for.

Start selling right away with Dawn's minimal setup steps that allow for a quick launch.

Responsibe design. Cater to our customer's preferred devices by making sure our store displays well on tablets and smartphones as well as desktop computers.

Powerful visual storytelling and large media options give our customers a look and feel for our brand and products.


Debutify Theme: (Lidquid based theme), Current Version 8.3
--------------------------------------------------------------------
The Shopify Debutify theme is primarily Liquid-based theme. It comes with 14 day free trial.

14-Day Free Trial. 


Shopify Dawn vs. Debut themes => Dawn theme load faster then debutify theme.
==============================================================================

The Dawn Shopify theme outperforms Debut in several key areas:

Speed: Dawn was refined for optimal performance, with a 35% faster load speed than Debut.

Mobile experience: To achieve an intuitive, mobile-first theme, Shopify designed Dawn for mobile screens first, then adapted it for desktops.

Content sections: Dawn accommodates content sections for all page types, resulting in more room for customization.

Flexibility: Brands can easily customize pages on Dawn using moveable sections and blocks for products, images, videos, and more—without the need for coding.

Compatibility: In addition to its superb performance across desktop to mobile devices, Dawn also works on all internet browsers.


**********Presets: 
=========================================================


JSON Template vs Liquid Template in Shopify : ****
----------------------------------------------------------
----------------------------------------------------------

Json : Used to define structure of shopify page.
They allow you to define the structure of our store's pages in a way that's more flexible and modular.

Liquid: Used to dynamically generate HTML, CSS, and JavaScript content.
Liquid is Shopify's templating language used to dynamically generate HTML, CSS, and JavaScript content.


1. In Json template Drag-and-drop Editing is available, but in liquid template it is not possible.


1. In Json Template, we have option to incude all home page section in customizer, but in old Liquid template we can not include home page section.

1. Using Json template we can insert dynamic data source to the fields.

1. For Json Template, created section data is unique means if we include same section twice on Json template we can update the different content on the same 2 sections.


Theme Version for liquid Online Store 1.0  
Theme version for Json Online Store 2.0+

But for Liquid template section data is defined globally so it will be same if we include section file twice.

Greatly improves flexibility with drag-and-drop sections in the Shopify theme editor.

Json template example:
=========================
// product.json

{
  "sections": {
    "main": {
      "type": "product-template"
    }
  },
  "order": ["main"]
}



Include Section in JSON Template : ****
--------------------------------------

{

    "sections" : {

        "main" : {
            "type" : "first-section"   // include section liquid file 
        },

        "second" : {
            "type" : "second-section"  // include section liquid file 
        }

       },

     "order" : ["main","second"]   // to arrance the section order

}



Example of blog schema :
---------------------------

{% schema %}

{
  "name": "blog",
  "settings": [],

  "blocks": [
    {
      "type": "blog",
      "name": "Blog Post",

      "settings": [
        {
          "type": "text",
          "id": "title",
          "label": "Title" // title
        },

        {
          "type": "textarea",
          "id": "content",
          "label": "Content" // description
        },

        {
          "type": "image_picker",
          "id": "image",
          "label": "Image" // image
        }

      ]

    }

  ]
}

{% endschema %}




====================================================================================================================================================

Liquid is a template language created by Shopify. 

Liquid is an open-source template language. It can be used to add dynamic content to webpages, 
and to create a wide variety of custom web templates.


Shopify was founded in 2006 by Tobias Lütke and Scott Lake ****. Shopify 2.0


Shopify Theme Structure:
=========================

1. Layout: theme.liquid is the layout file.
--------------------------------------------
Theme.liquid is the layout file where we can put common js,css file in header or footer.
For example, layouts are a good place to include any content we might want in the <head> element, as well as headers and footers.

Layouts are the base of the theme, through which all templates are rendered.
Layouts are Liquid files that allow you to include content, that should be repeated on multiple page types, in a single location. 

For example, layouts are a good place to include any content you might want in our <head> element, as well as headers and footers.
You can edit the default theme.liquid layout, or you can create multiple custom layout files to suit our needs.

2.Templates:
-------------
In Shopify, a template refers to a pre-designed layout or structure for an online store, often referred to as a theme. 
It provides the foundational look and feel of a store and controls how the content, such as products, images, and text, is displayed to customers.

3. Sections  :    {% section section_name %}
----------------------------------------------
Sections that our website pages are built off. We will also further explain these in more detail later in this blog.
Pages are built off using different sections.

Every shopify website we see is made up of sections.


In Shopify, Sections are customizable components that allow store owners to build flexible, dynamic pages.

They are used to structure the layout and content of a store's theme, enabling users to create unique and varied designs for different pages (like the homepage, product pages, or collection pages) without needing to touch the underlying code.





It’s the same in Shopify. Here's the example structure of a website homepage in sections:

Example:
----------
Announcement bar
Header/Menu
A slideshow
Featured collection section (product snippet from a chosen collection)
Featured collections section (multiple collections)
Image with product slider
Featured collection slider
Featured collections
Reviews section
Another Image banner section (with text & buttons)
Newsletter
Footer


4. Snippets  {% render 'snippet' %}
--------------------------------------
A Shopify snippet is a small reusable piece of code in our Shopify store's theme. 
It allows you to add HTML, CSS, JavaScript, or Liquid code that we can include in different parts of our theme.


Shopify Snippets are re-useable bits of code - which can also take on parameters. Snippets may only use the .liquid extension. 

{% render %} is generally more performant and better optimized for handling snippets in modern Shopify themes.

You can add these to any .liquid file & other snippets too. 
Then when you make a change to a snippet it changes it for every instance of it. 

The key distinction is size — snippets are designed for the smallest pieces of code that you often reuse on our store, while sections are better for more complicated content that involves various elements. Also, sections may use the .json or .liquid file extensions. Snippets may only use the .liquid extension. 

Common used of snippets are:
-----------------------------
Anywhere where you might repeat code

For product card

Storing an Arrow Icon SVG code

Can we include snippet inside another snippet in shopify ??  {% render 'snippet' %} or {% assign content_of_snippet = 'snippet_content' %}
---------------------------------------------------------------

#1. One way is by using {% render 'snippet' %} instead of {% include 'snippet' %}. With {% render 'snippet' %}, you can include a snippet inside another snippet, but it will render the snippet as if it's a separate page, which might not always be desired.


{% render 'snippet' %}


#2. Another approach is to use the {% assign %} tag to capture the content of one snippet and then include that content in another snippet. For example:


{% assign content_of_snippet = 'snippet_content' %}

Then you can use {{ content_of_snippet }} wherever you want to include the content of the first snippet.


3. Config:  theme realed settings.
--------------
Config files define settings in the Theme settings area of the theme editor, as well as store their values.

This contains just 2 files. 

setting_data.json: Theme Setting : 
==================================
These are the global settings applied to our theme,these settings can include things like colors, fonts, layout options, and more.


A "setting_data.json" and a "settings_schema.json" file. When you go to the Shopify customizer (press the green “Customize” button on our theme), you will see on the panel to the left a little pain brush icon. When clicking onto this you’ll see a ton of settings called the “Theme settings”. These are the global settings applied to our theme.

****settings_schema.json == Theme color, logo height, section height , font size, font color, button color etc.
===========================
Each input setting you see there e.g. the selector to choose our Font and the swatch to choose our background color are called Schemas. Long story, short those are made by the settings_schema.json file. Now every time you save or update that value, the new value you inputted gets stored inside the setting_data.json.


****setting_data.json : All theme based settings are included in this file.
=======================

Every time you save or update that value , the new value you inputted gets stored inside the setting_data.json.

The settings_data.json file contains the setting values for a theme based on the settings included in settings_schema.json.

For example, you can use the following theme setting to allow a merchant to choose a color for the page background:

example:
===========
{
  "current": {
    "settings": {
      "color_scheme": "dark",
      "font_style": "serif",
      "header_layout": "classic",
      "logo_position": "left",
      "button_style": "rounded"
    },
    "theme": {
      "name": "Debut",
      "version": "3.0.0"
    }
  },
  "defaults": {
    "settings": {
      "color_scheme": "light",
      "font_style": "sans-serif",
      "header_layout": "modern",
      "logo_position": "center",
      "button_style": "flat"
    }
  }
}



settings_schema.json := Theme color, logo height, section height , font size, font color, button color etc.
----------------------------

{
    "name": "Colors",
    "settings": [
        {
        "type": "color",
        "id": "color_page_bg",
        "label": "Page background",
        "default": "#FFFFFF"
        }
    ]
}



4. Assets: images,css,js,font files
===================================

In Asset we can store various files, such as images, CSS stylesheets, JavaScript files, font files and other resources that are essential for our 
store’s design and functionality.

To call the “image.jpg” in our theme, we write this code:

{{ 'image.jpg' | asset_img_url }}

{{ 'style.css' | asset_url }}



5. Locales:  allow us to translate storefront content to multiple languages.
------------
Locale files are JSON files that allow us to translate storefront content to multiple languages.

Locale files are JSON files that contain a set of translations for text strings used throughout the theme and theme editor.

In addition to giving merchants a single place to easily edit words and phrases that are repeated throughout the theme, locale files allow you translate storefront content, and theme editor settings, to multiple langages for international merchants and customers.


What is a Shopify block? ===> section are made of with blocks(piece of content)
============================
Blocks are pieces of content that can be added, hidden and re-ordered inside of a section. 

Shopify, a block generally refers to a modular content element that you can add to a page, theme, or section of our Shopify store. Blocks allow you to create flexible, customizable designs and layouts without requiring custom coding knowledge. 

You can have a maximum of 50 blocks inside each section. Each block can have it’s own individual block settings.

We can access the settings inside the block by using {{ block.setting.id }}


Why use robots.txt file ?
=========================
Restric website to show in search engine.

The robots.txt file is a simple text file placed on a website to communicate with web crawlers (bots), 
like those used by search engines. 

Its primary function is to control and restrict the access that these crawlers have to certain parts of our website.


User-agent: *
Disallow: /private-folder/
Allow: /public-folder/
User-agent: Specifies which crawler the rules apply to (e.g., Googlebot, Bingbot, or * for all bots).

Disallow: Blocks access to the specified path.

Allow: Grants access, used mainly when overriding a broader disallow rule.



Write Code for fetch collection & product inside collection: ****
------------------------------------------------------

{% for collection in collections %}

  <h2>{{ collection.title }}</h2>
  <ul>
    {% for product in collection.products %}

      <li>{{ product.title }} - {{ product.price | money }}</li>

    {% endfor %}
  </ul>

{% endfor %}

Write Code for fetch products directly without using collection : *****
-------------------------------------------------------------

{% for product in all_products %}

  <h2>{{ product.title }}</h2>
  <p>{{ product.description }}</p>
  <p>Price: {{ product.price | money }}</p>
  <!-- You can include more product information here -->

{% endfor %}


What are the different types of Shopify plans and what features do they provide?
----------------------------------------------------------------------------------
Basic Plan : Price $29 per month, 2 staff account, 10 inventory locations
-------------

Shopify for small team : Price $79 per month,  5 staff account , 10 inventory locations
------------------------

Advanced Shopify: This plan costs $299 per month, 15 staff account ,10 inventory locations
--------------------

Shopify plus : $2000 usd, 100 staff account.  200 inventory locations, Up to 10x on select APIs
------------------

Shopify offers several different pricing plans, each with their own set of features and pricing. 

Basic Shopify: This plan costs $29 per month and includes all the basic features required to start an online store, such as unlimited products, storage, and bandwidth, a free SSL certificate, and 24/7 support.

Shopify: This plan costs $79 per month and includes all the features of Basic Shopify, plus gift cards, professional reports, and abandoned cart recovery.

Advanced Shopify: This plan costs $299 per month and includes all the features of Shopify, plus advanced report builder, third-party calculated shipping rates, and advanced report builder.


Shopify Plus: This plan is for large businesses and enterprise-level clients and includes all the features of Advanced Shopify, plus white-glove account management, and dedicated support.

When their online sales reach about $80,000 per month. ******

***GraphQL Storefront API (Facebook build GraphQL):
-------------------------------------------------
The Storefront API is available only in GraphQL. There's no REST API for storefronts.

GraphQL is a query language. It provides a query in the form of a string that is sent to a server. 


The Shopify Storefront API is a GraphQL-based API that allows you to build custom storefronts on any platform (web, mobile, etc.), totally separate from Shopify’s Liquid-based front end.


A query language for our API.

Facebook build GraphQL on 2012, 

The server interprets the query and then returns the result in the form of JSON format to the client.

Advantage of GraphQL: ****
------------------------
GraphQL solves this problem by fetching only the exact and specific data in a single request.

*** GraphQL is way faster than other communication APIs because it facilitates us to request query by choosing only the specific fields you want to query.

**** The main advantage of GraphQl over REST is that REST responses contain too much data or sometimes not enough data, which creates the need for another request. GraphQL solves this problem by fetching only the exact and specific data in a single request.

GraphQL vs REST API?
-------------------------------
GraphQL vs REST API - Difference Between API Design.

GraphQL is a query language, architecture style, and set of tools to create and manipulate APIs. 
REST is good for simple data sources where resources are well defined. 

GraphQL is good for large, complex, and interrelated data sources. 
REST has multiple endpoints in the form of URLs to define resources.


Shopify Storefront API ( The Storefront API is available only in GraphQL. There's no REST API for storefronts)
---------------------------------------------------------------------------------------------------------------
Read products and collections
Create customers and update customer accounts
Query international prices for products and orders
Interact with a cart during a customer's session
Initiate a checkout


Dawn Theme: (Json based template), Current version of Dawn Theme Last Version 15.2.0 ,updated Mar 3, 2025
----------------------------------------------------------------------------------------------------------
Dawn theme is best optimized, fast, easy to customize.

Dawn is Shopify's reference theme, which is built for performance, flexibility, and ease of use. 
It uses Online Store 2.0 features, including JSON templates, which support app blocks and sections on all pages.


Here is an example of a Liquid file that displays the product title and price on a Shopify page:


<div class="product">
  <h2>{{ product.title }}</h2>
  <p>Price: {{ product.price | money }}</p>
</div>


How to fetch info from section ?
---------------------------------
{{section.settings.id}}


Assing Variable Shopify:
-------------------------

{% assign favorite_food = "pizza" %}
{% assign age = 35 %}


How to get shopify theme id?
-----------------------------
Inspect the home page. Search for “theme_store_id”

Shopify Plus : recommended for revenue per month is at least $75,000 per month.
----------------

Shopify Plus Plan price  $2000 USD per month

Monthly sales: Shopify Plus is generally recommended for businesses that generate at least $75,000 in monthly revenue


Shopify Plus is an enterprise-level solution offering additional features such as:
----------------------------------------------------------------------------------

Advanced customization options
Custom checkout
Unlimited Staff Account
Dedicated support team
Increased API call limits
Exclusive apps and integrations


Customizable checkout :

The checkout.liquid file provides a customizable checkout that gives you more control over the branding of our store.

Checkout.liquid has been deprecated for the Information, Shipping, and Payment pages and will be removed on August 13, 2024. 
Shopify Plus merchants can now use checkout extensibility to customize these pages instead. If you customize the Information, Shipping, or Payment pages in our checkout, then upgrade to checkout extensibility before August 13, 2024.

API resources :

Shopify Plus supports additional API calls that let you integrate with custom apps. You can request increased API rate limits by contacting support. The following API resources can be used by Shopify Plus merchants only:

REST
GiftCard
Multipass
User
GraphQL

Locations :

With Shopify Plus, you can add up to 200 locations so you can track inventory and fulfill orders at various locations.


What are some key features of Shopify and Shopify Plus?
---------------------------------------------------------
A3: Key features of Shopify include:

Easy-to-use interface
Customizable themes
App Store with numerous integrations
Secure and reliable hosting
Multiple sales channels
SSL certificate
24/7 customer support



Sections
-------------
Shopify does not support including sections within sections directly. 
--------------------------------------------------------------------

Sections are Liquid files that allow us to create reusable modules of content that can be customized by merchants. 
They can also include blocks which allow merchants to add, remove, and reorder content within a section.

For example, you can create an Image with text section that displays an image and text side-by-side with options for merchants to choose the image, set the text, and select the display order.


Section schema
-----------------
Sections support the {% schema %}  tag. This tag allows you to define various attributes of a section, such as the section name, any section blocks, and settings to allow for theme editor customization options.

Example of blog schema :
---------------------------

{% schema %}
{
  "name": "blog",
  "settings": [],
  "blocks": [
    {
      "type": "blog",
      "name": "Blog Post",
      "settings": [
        {
          "type": "text",
          "id": "title",
          "label": "Title"
        },
        {
          "type": "textarea",
          "id": "content",
          "label": "Content"
        },
        {
          "type": "image_picker",
          "id": "image",
          "label": "Image"
        }
      ]
    }
  ]
}
{% endschema %}


Example of section schema:
--------------------------

{% schema %}
{
  "name": "Slideshow",
  "tag": "section",
  "class": "slideshow",
  "limit": 1,
  "settings": [
    {
      "type": "text",
      "id": "title",
      "label": "Slideshow"
    }
  ],
  "max_blocks": 5,
  "blocks": [
     {
       "name": "Slide",
       "type": "slide",
       "settings": [
         {
           "type": "image_picker",
           "id": "image",
           "label": "Image"
         }
       ]
     }
  ],
  "presets": [
    {
      "name": "Slideshow",
      "settings": {
        "title": "Slideshow"
      },
      "blocks": [
        {
          "type": "slide"
        },
        {
          "type": "slide"
        }
      ]
    }
  ],
  "locales": {
    "en": {
      "title": "Slideshow"
    },
    "fr": {
      "title": "Diaporama"
    }
  },
  "enabled_on": {
    "templates": ["*"],
    "groups": ["footer"]
  }
}
{% endschema %}






Banner Image and Title Schema & show it in liquid file ?
----------------------------------------------------------

Liquid file code :
-------------------
{% comment %}
  banner-image.liquid
  Liquid code to display banner image and title
{% endcomment %}

<div class="banner">
  {% if section.settings.banner_image %}
    <img src="{{ section.settings.banner_image | img_url: 'master' }}" alt="Banner Image">
  {% endif %}

  {% if section.settings.banner_title %}
    <h2>{{ section.settings.banner_title }}</h2>
  {% endif %}
</div>


Create a section for banner schema: 
-----------------------------------
We write schema in section & write schema in schema tag {% schema %}  {% endschema %}



{% comment %}
  banner-image.liquid
  Schema for a banner image and title
{% endcomment %}



{% schema %}
{
  "name": "Banner Image",
  "settings": [
    {
      "type": "image_picker",
      "id": "banner_image",
      "label": "Banner Image"
    },
    {
      "type": "text",
      "id": "banner_title",
      "label": "Banner Title"
    }
  ],
  "presets": [
    {
      "name": "Banner",
      "category": "Custom Content"
    }
  ]
}
{% endschema %}






Difference between blocks & sections:
--------------------------------------
Blocks are customizable modules that make up the sections in our page templates. 
You can use blocks to add text, images, links, buttons, and more.



How many sections can you have on Shopify?
==========================================
You can have up to 25 sections per template, 

and each section can contain up to 50 blocks. 


index.json :
-------------
index.json file will save/store all the data in JSON format. Like heading text, sub heading, banner image, title, product info data, Blog info. Any section which 
we create and add the data, that data is stored in index.json file.****

Some applications or custom solutions might use the index.json file as a means of storing structured data in JSON format. 
This data could be anything from configuration settings to product information, depending on the specific requirements of the application.


setting_data.json : All theme based settings are included in this file.
--------------------
The settings_data.json file contains the setting values for a theme based on the settings included in settings_schema.json.

For example, you can use the following theme setting to allow a merchant to choose a color for the page background:

config/settings_schema.json := Theme color, logo size, section hight , font size, font color, button color etc.
----------------------------

{
    "name": "Colors",
    "settings": [
        {
        "type": "color",
        "id": "color_page_bg",
        "label": "Page background",
        "default": "#FFFFFF"
        }
    ]
}

Settings_schema.json :
-----------------------
It contains all schema related settings, like logo settings (min,max height), image picker setting, bloock setting, cards setting,header setting.

The settings_schema.json file controls the organization and content of the Theme settings area of the theme editor. 
All setting selections in the theme editor are saved in settings_data.json.



Schema : We design section using schema.
----------
Using schema we desing sections which include names, blocks, and settings of the section.

Schema tags allow an individual to define various attributes of a section which include names, blocks, and settings of the section.

A Schema is a Shopify liquid tag that contains JSON inside

Every section file needs a schema with a name and presets to allow it to be added in the customiser

Themes are edited by the user changing settings (inputs) in the customiser

Input settings are the different types of inputs (settings) you can have. There are 28 of them

There are 3 types of settings: theme, section and block level

For theme settings, data is stored in the settings_data.json file

For sections and blocks, data from inputs are stored in the .json template file where the section is used

These are the different attributes you can have inside of a schema:

name:
This is where you set the name of a section. This can be different from the name of the file. This name is what store owners will see the section named as in the editor

tag:
This determines what HTML tag the section should be wrapped around. By default, it is a element. If you would like you can to have a section or header or footer tag.

class:
This allows you to add a custom class into the tag which wraps this section

limit:
Limit determines how many times this section can be used on a specific template. e.g. it can only be used 2 times on the homepage or collection page

settings:
This is where input settings go

blocks:
You can create multiple types of blocks, each with it's own individual limits and settings

max_blocks:
This puts a max ceiling on the number of total blocks that can be used in a section. For example, you can have 3 different types of blocks for a section. Let’s say you only want there to be 4 blocks maximum, this is where you would set that.



Template: Template use to design the layout/design of every page. 
----------
Templates control what's rendered on each type of page in a theme. 


JSON vs. LiquidAnchor link to section titled "JSON vs. Liquid"
If you want to use sections in a template, then you should use a JSON template.

JSON templates provide more flexibility for merchants to add, remove, and reorder sections, including app sections.
Additionally, they minimize the amount of data in settings_data.json. Instead, data is stored directly in the template, which improves the performance of the theme editor.



Template Types:
----------------

There are two different file types you can use for a theme template: JSON and Liquid.

JSON  
-----  
JSON templates are data files with the .json file extension. These templates let you easily populate our template with content from sections. 
Sections can be added, removed, or rearranged by merchants using the theme editor.

If you're using a JSON template, then any HTML or Liquid code needs to be included in a section that's referenced by the template.


Liquid 
-------
Liquid templates are Liquid markup files, with the .liquid file extension. 
You can add Liquid and HTML directly to Liquid templates.

Liquid is a template language that allows us to display data in a template.

Liquid is the template language used in Shopify. It's used to output dynamic content, variables, and control structures in templates. Shopify's themes use Liquid for dynamic content rendering.


***in shopify hide  the product which is not in stock. how we can do that ? Using  {% if product.available %}
============================================================================
1. Create a collection with available stock product and show only this collection.

2. Check the “Track quantity” Option:

Ensure that the “Track quantity” option is enabled for our products. This allows Shopify to monitor stock levels.

{% for product in collection.products %}
  {% if product.available %}
    <!-- our existing code to display the product -->
    <div class="product">
      <h2>{{ product.title }}</h2>
      <!-- More product details here -->
    </div>
  {% endif %}
{% endfor %}



{% for product in collection.products %}
{% if product.available %}

{{product.title}}
{{product.price | money}}

{% endif %}

{% endfor %}



Note:
------
You can have a maximum of 1000 JSON templates in our theme, across all template types. For example, if you have 20 JSON product templates, 10 JSON page templates, and 5 JSON collection templates, then you can add up to 965 additional templates to the theme.

Article Template:
------------------
The article template renders the article page, which contains the full content of the article, as well as an optional comments section for customers. This template is used for items like individual posts in a blog.

"content_for_header" : Load all the required scripts into shopify into the <head> tag.
---------------------------
It dynamically loads all scripts required by Shopify into the document head. These scripts are required for features like reCAPTCHA, Shopify apps, and more.
The content_for_header object is required in theme.liquid. It must be placed inside the HTML <head> tag. 

You shouldn't try to modify or parse the content_for_header object. If content_for_header changes, then the behavior of our Liquid will change.

"content_for_layout" : returns the content of sections to be rendered on the home page.
-------------------------
The content_for_layout object dynamically outputs the content for each template. You need to add a reference to this object between the <body> and </body> HTML tags.


Different between Snippet & Sections:
--------------------------------------
Snippets are reusable code snippets that are included directly within template files.

{% include 'snippet_name' %} 

Sections are customizable "blocks of content" that provide a visual editing experience for merchants via the Shopify Theme Editor. 

{% section 'hero-banner' %}

Both snippets and sections play important roles in organizing and customizing Shopify themes efficiently.

**** You can have up to 25 sections per template, and each section can contain up to 50 blocks.

**** We can  not include section inside another section.




Variable is shopify:
-----------------------

Variables in Liquid are placeholders that can hold different types of data, such as text, numbers, arrays, or objects. These variables can be defined and manipulated within Liquid code to dynamically generate content.

Here's how variables work in Shopify's Liquid:

Assigning Variables:
--------------------

You can assign a value to a variable using the {% assign %} tag. 

For example:

{% assign product_title = product.title %}

{% assign my_array = "apple, banana, orange" | split: ", " %}



Accessing Variables:
--------------------

Once a variable is assigned, you can access its value using double curly braces {{ }}. 

For example:
------------
{{ product_title }}


Scope of Variables:
-------------------

Variables in Liquid have a specific scope, meaning they are only accessible within the block of code where they are defined or within narrower scopes like loops or conditionals.

Built-in Variables:
-------------------

Shopify provides various built-in variables that you can use to access information about the current context. 

For example, 
product provides information about the current product being displayed, 
collection provides information about the current collection, 
and customer provides information about the logged-in customer.



Filters and Modifiers:
-----------------------
Liquid allows you to apply filters and modifiers to variables to manipulate their output.
 For example, you can use the | symbol to apply a filter. 

For instance, {{ product.price | money }} would format the product's price as currency.


Date Filters:

date: Formats dates. For example: {{ article.published_at | date: "%Y-%m-%d" }}

Math Filters:

plus: Adds a number to another number.
minus: Subtracts a number from another number.
times: Multiplies a number by another number.
divided_by: Divides a number by another number.

Text Filters:

capitalize: Capitalizes the first character of a string.
downcase: Converts a string to lowercase.
upcase: Converts a string to uppercase.

String Filters:

append: Appends a string to another string.
prepend: Prepends a string to another string.
remove: Removes occurrences of a substring from a string.
replace: Replaces occurrences of a substring with another substring.
truncate: Truncates a string to a specified length.


Array Filters:

join: Joins the elements of an array into a single string.
sort: Sorts the elements of an array.
map: Applies a filter to each item in an array.
first: Returns the first item in an array.
last: Returns the last item in an array.

Miscellaneous Filters:

size: Returns the size of an array or the length of a string.
default: Sets a default value if a variable is undefined or empty.
escape: Escapes HTML entities.
strip_html: Removes HTML tags from a string.
json: Converts a variable to JSON format.
Money Filters:

money: Formats a number as a currency.


Conditional Logic and Loops:
-----------------------------

Variables are commonly used within conditional statements (if, else, elsif, etc.) and loops (for, limit, offset, etc.) to control the flow of logic or to iterate over collections of data.



What are the different types of Shopify reports and how can they be used?
============================================================================

Shopify offers several types of reports to help merchants track and analyze their store's performance. These include:

Sales reports:
--------------
 These reports provide information on sales, revenue, and average order value. They can help you identify trends in our sales data and make informed decisions about our pricing and promotions.

Financial reports: 
------------------
These reports provide an overview of our store's financial performance, including profit and loss statements, balance sheets, and cash flow statements. They can help you understand the financial health of our business and make strategic decisions about our investments and expenses.

Marketing reports: 
------------------
These reports provide insights into our marketing campaigns, such as email and social media marketing. They can help you evaluate the effectiveness of our campaigns and make adjustments to optimize our results.

Customer reports: 
-----------------
These reports provide information on our customers, such as their demographics, purchase history, and lifetime value. They can help you understand our customers better and tailor our marketing and sales strategies to their needs.





Shopify Api :
----------------------

POST /{locale}/cart/add.js
----------------------------

Use the POST /{locale}/cart/add.js endpoint to add one or multiple variants to the cart.

let formData = {
 'items': [{
  'id': 36110175633573,
  'quantity': 2
  }]
};

fetch(window.Shopify.routes.root + 'cart/add.js', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify(formData)
})
.then(response => {
  return response.json();
})
.catch((error) => {
  console.error('Error:', error);
});



GET /{locale}/cart.js
------------------------
Use the GET /{locale}/cart.js endpoint to get the cart as JSON.




POST /{locale}/cart/update.js
-----------------------------

Use the POST /{locale}/cart/update.js endpoint to update the cart's line item quantities, note, or attributes. You can submit a serialized cart form, or submit separate updates to a cart's line items, note, or attributes.


let updates = {
  794864053: 2,
  794864233: 3
};

fetch(window.Shopify.routes.root + 'cart/update.js', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({ updates })
})
.then(response => {
  return response.json();
})
.catch((error) => {
  console.error('Error:', error);
});



POST /{locale}/cart/change.js
------------------------------
The POST data requires either an id or line property to identify the line item to be changed.



POST /{locale}/cart/clear.js
-----------------------------

Use the POST /{locale}/cart/clear.js endpoint to set all quantities of all line items in the cart to zero.



What are the differences between public and private apps in Shopify?
----------------------------------------------------------------------------
 Public apps and private apps serve different purposes in Shopify:

Public Apps:
------------
Intended for multiple merchants
Listed on the Shopify App Store
Require OAuth 2.0 for authentication
Can be used as a revenue source for developers
Must comply with Shopify's App Store requirements


Private Apps:
--------------
Built for a specific merchant's store
Not listed on the Shopify App Store
Use basic HTTP authentication
Do not need to comply with App Store requirements
