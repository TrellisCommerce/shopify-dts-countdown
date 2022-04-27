Brought to you and maintained by [Trellis Commerce](https://trellis.co/) - A full-service eCommerce agency based in Boston, MA

# Dawn TailWindCSS Starter Component - Countdown

Extension of Shopify's Dawn theme countdown.
With this extension, you can:

- add a Countdown as a section in any page of the site

![On A Mission Skincare 2022-04-27 at 2 26 57 PM](https://user-images.githubusercontent.com/32713913/165585047-8a56f327-c535-4458-8ebf-7975f9616ec9.jpg)

- add a countdown block inside the PDP

![(null) 2022-04-27 at 2 24 48 PM](https://user-images.githubusercontent.com/32713913/165585127-ebfc4740-552b-4bdc-a677-b87c0e9b3ac0.jpg)


## How to Add to Your Theme

1. Add an `countdown-trellis.liquid` file to the `sections` directory and copy in the file's code from this repo.
2. Add an `countdown-trellis.liquid` file to the `snippets` directory and copy in the file's code from this repo.

- If you are not using the [dawn-tailwind-starter-base](https://github.com/TrellisCommerce/dawn-tailwind-starter-base) as your theme, you will need to add the following styles to your liquid file:

```
.twcss-absolute {
  position: absolute;
}

.twcss-relative {
  position: relative;
}

.twcss-left-1\/2 {
  left: 50%;
}

.twcss-bottom-\[-43px\] {
  bottom: -43px;
}

.twcss-mx-auto {
  margin-left: auto;
  margin-right: auto;
}

.twcss-mb-\[55px\] {
  margin-bottom: 55px;
}

.twcss-flex {
  display: flex;
}

.twcss-hidden {
  display: none;
}

.twcss-min-h-\[126px\] {
  min-height: 126px;
}

.twcss-w-screen {
  width: 100vw;
}

.twcss-min-w-\[126px\] {
  min-width: 126px;
}

.twcss-max-w-full {
  max-width: 100%;
}

.twcss-max-w-\[280px\] {
  max-width: 280px;
}

.twcss-max-w-screen-xlg {
  max-width: 1440px;
}

.-twcss-translate-x-1\/2 {
  --tw-translate-x: -50%;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}

.twcss-flex-col {
  flex-direction: column;
}

.twcss-flex-wrap {
  flex-wrap: wrap;
}

.twcss-items-center {
  align-items: center;
}

.twcss-justify-center {
  justify-content: center;
}

.twcss-border-\[3px\] {
  border-width: 3px;
}

.twcss-px-\[20px\] {
  padding-left: 20px;
  padding-right: 20px;
}

.twcss-px-\[18px\] {
  padding-left: 18px;
  padding-right: 18px;
}

.twcss-px-\[10px\] {
  padding-left: 10px;
  padding-right: 10px;
}

.twcss-py-\[5px\] {
  padding-top: 5px;
  padding-bottom: 5px;
}

.twcss-pb-\[40px\] {
  padding-bottom: 40px;
}

.twcss-pt-\[30px\] {
  padding-top: 30px;
}

.twcss-pt-\[25px\] {
  padding-top: 25px;
}

.twcss-pb-\[20px\] {
  padding-bottom: 20px;
}

.twcss-pt-\[10px\] {
  padding-top: 10px;
}

.twcss-pb-\[30px\] {
  padding-bottom: 30px;
}

.twcss-text-center {
  text-align: center;
}

.twcss-text-right {
  text-align: right;
}

.twcss-text-\[70px\] {
  font-size: 70px;
}

.twcss-text-\[65px\] {
  font-size: 65px;
}

.twcss-leading-none {
  line-height: 1;
}

.twcss-opacity-0 {
  opacity: 0;
}

@media (min-width: 320px) {
  .sm\:twcss-justify-between {
    justify-content: space-between;
  }
}

@media (min-width: 750px) {
  .md\:twcss-mb-0 {
    margin-bottom: 0px;
  }

  .md\:twcss-mr-\[39px\] {
    margin-right: 39px;
  }

  .md\:twcss-max-w-none {
    max-width: none;
  }

  .md\:twcss-justify-center {
    justify-content: center;
  }

  .md\:twcss-px-\[52px\] {
    padding-left: 52px;
    padding-right: 52px;
  }

  .md\:twcss-px-\[10\%\] {
    padding-left: 10%;
    padding-right: 10%;
  }

  .md\:twcss-pt-\[85px\] {
    padding-top: 85px;
  }

  .md\:twcss-text-\[75px\] {
    font-size: 75px;
  }
}
```

3. In sections > main-product.liquid, add this code as a new "block" in the schema

```
{
  "type": "countdown",
  "name": "Countdown",
  "limit": 1,
  "settings": [
    {
      "type": "select",
      "id": "countdown_style",
      "options": [
        {
          "value": "banner",
          "label": "Banner"
        },
        {
          "value": "text",
          "label": "Text"
        }
      ],
      "default": "banner",
      "label": "CountDown Style"
    },
    {
      "type": "color",
      "id": "bkg_color",
      "label": "Background Color",
      "default": "transparent"
    },
    {
      "type": "color",
      "id": "content_color",
      "label": "Content Color",
      "default": "#000000"
    },
    {
      "type": "text",
      "id": "title",
      "label": "Title",
      "default": "ON SALE for"
    },
    {
      "type": "checkbox",
      "id": "show_days",
      "label": "Show Days",
      "default": true
    },
    {
      "type": "checkbox",
      "id": "show_hours",
      "label": "Show Hours",
      "default": true
    },
    {
      "type": "checkbox",
      "id": "show_minutes",
      "label": "Show Minutes",
      "default": true
    },
    {
      "type": "checkbox",
      "id": "show_seconds",
      "label": "Show Seconds",
      "default": true
    }
  ]
}
```

4. In sections > main-product.liquid. Add this code at the end of the `case block.type`

```
  {% when 'countdown' %}
    {% liquid
      assign date = product.metafields.global.countdown
      if date
        render 'countdown-trellis', data: block.settings, date: date, type: 'block'
      endif
    %}
```

5. Add a new product's metafield called 'global.countdown' of type Date and Time. If the metafield has a value, then the countdown will be displayed on the PDP

![On A Mission Skincare _ Product metafield definitions _ Edit countdown _ Shopify 2022-04-27 at 2 43 42 PM](https://user-images.githubusercontent.com/32713913/165587600-0854f953-b134-412a-849b-480d62f56731.jpg)

