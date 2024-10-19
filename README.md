# CMS_midterm
# midtermcms-Gursimran-kaur
# Nanna's Pantry Shopify Store

## Theme Information
- **Theme Style**: Dawn
- **Custom Styles**: Custom CSS file for animations and additional styling.

## Site Features
- **GDPR Banner**: 
  - Implemented a GDPR banner that can be dismissed for at least the duration of the session with an acceptance button.
  - Code :
    ```html
    <div id="gdpr-banner" style="position: fixed; bottom: 0; width: 100%; background-color: #222; color: white; text-align: center; padding: 10px;">
      <p>This website uses cookies to ensure you get the best experience on our website. <a href="/pages/privacy-policy" style="color: #ffcc00;">Learn more</a></p>
      <button id="gdpr-accept" style="background-color: #ffcc00; border: none; padding: 10px;">Accept</button>
    </div>

    <script>
      document.getElementById('gdpr-accept').onclick = function() {
        document.getElementById('gdpr-banner').style.display = 'none';
        localStorage.setItem('gdprAccepted', 'true');
      }

      window.onload = function() {
        if (localStorage.getItem('gdprAccepted') === 'true') {
          document.getElementById('gdpr-banner').style.display = 'none';
        }
      }
    </script>
    ```

## Header
- **Logo**: Included.
- **Main Menu**: 
  - Baked Goods
  - Raw & Roasted Nuts
  - Tea & Spices
  - Contact Form

## Homepage Features
- **Image Slider**: Done (added screenshot).
- **Featured Product**: Blueberry Muffin (added screenshot).
- **All Collections Section**: Added title "Browse Our Collections".
- **Newsletter Signup Section**: Added email bar with "Stay Updated" heading.

## Product Features
- **All Product Images**: Same aspect ratio.
- **Sharing Links**: Enabled for individual products.

## Footer
- **Quick Links Menu**: 
  - Search
  - Contact
  - Return Policy
  - Privacy Policy (GDPR)
- **Follow Us Menu**: 
  - Twitter
  - Facebook
  - Pinterest
  - Instagram
- **Store Location Map**: 
  - Code used:
    ```html
    <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2881.3867545278827!2d-79.41537722532745!3d43.76482994520603!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x882b47257e142195%3A0x998c398862d57488!2sCDI%20College%20-%20North%20York!5e0!3m2!1sen!2sca!4v1729291305390!5m2!1sen!2sca" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
    ```

## Animation
- **Footer Animation**: Added slide-in-from-left animation to footer sections using custom CSS.
- **Custom CSS Code**:
    ```css
    @keyframes slide-in-from-left {
      0% {
        transform: translateX(-100%);
        opacity: 0;
      }
      100% {
        transform: translateX(0);
        opacity: 1;
      }
    }

    .animate-slide-in {
      animation: slide-in-from-left 0.5s ease forwards;
    }
    ```

## Featured Product Layout Changes
- **Featured Product Title**: Moved below the product's image in the homepage featured product layout (`featured-product.liquid`).
- **Code Changes**:
    ```html
    <!-- Product Image -->
    <div class="product__image">
      <img
        src="{{ product.featured_image | img_url: 'medium' }}"
        alt="{{ product.title | escape }}"
        width="300"
        height="300"
      >
    </div>

    <!-- Product Title (Moved below the image) -->
    <h2 class="product__title {{ block.settings.heading_size }}" {{ block.shopify_attributes }}>
      {%- unless placeholder -%}
        {{ product.title | escape }}
      {%- else -%}
        {{ 'onboarding.product_title' | t }}
      {%- endunless -%}
    </h2>
    ```

## Cart Layout Changes
- **Cart Layout Changes**: Adjusted layout to move the "Quantity" column before the "Price" column and the "Update Cart" button before the "Continue Shopping" button.
- **Code Changes**: (Add the specific code snippets if needed).

## Enhance Your Site Functionality
### Installed Apps

1. **Yotpo**
   - **Description:** Yotpo is an app that helps you collect and display customer reviews, ratings, and user-generated content. It enhances your store's credibility and boosts sales.
   

