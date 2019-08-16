# Metal Types

+ Aluminium
+ Brass and Bronze
+ Cast Iron
+ Copper
+ Steel
+ Tin 

### Example JSON-LD for product packaging

```javascript
<script type="application/ld+json">
{
    "@context": "https://schema.org",
    "@type": "Product"
    "description": "packaging",
    "material": {
        "@type": "Product",
        "description": "metal",
        "name": "aluminium"
    }
    "category": {
        "@type": "Thing",
        "name": "can"
    },
    "weight": {
        "@type": "QuantitaveValue",
        "value": "4",
        "valueReference": "oz",
    },
    "image": { // perhaps in the future include image for AI 
        "@type": "imageObject",
        "url": "http://example.com/images/image.png",
        "height": "640",
        "width": "800"
    },
}
</script>
```

### Example JSON-LD for manafactured product 

```javascript
<script type="application/ld+json">
{
    "@context": "https://schema.org",
    "@type": "Product"
    "manafacture": "Acme door handles"
    "description": "Door handle hardware.",
    "material": {
        "@type": "Product",
        "description": "metal",
        "name": "brass"
    }
    "category": {
        "@type": "Thing",
        "name": "door handle" 
    },
    "weight": {
        "@type": "QuantitaveValue",
        "value": "12",
        "valueReference": "oz",
    },
    "image": { // perhaps in the future include image for AI 
        "@type": "imageObject",
        "url": "http://example.com/images/image.png",
        "height": "640",
        "width": "800"
    },
}
</script>
```

### Example JSON-LD for product packaging & manafactured product & shipping packaging

<script type="application/ld+json">
  "@context": "http://schema.org",
    "@type": "ItemList",
    "url": "http://toymanafacture.com?toy=39600",
    "numberOfItems": "1",
    "itemListElement": [
       "@type": "Product",
       "image": "http://toymanafacture.com/random.platicCar.jpeg",
       "url": "http://toymanafacture.com/",
       "name": "toyCar",
        "offers": {
           "@type": "Offer",
           "price": "1.99."
         },
        ],
         {
           "@type": "Product"
           "description": "packaging",
           "category": {
	      "@type": "Thing",
          "description": "paper"
	      "name": "cardboard"
                       ...
          },
</script>
