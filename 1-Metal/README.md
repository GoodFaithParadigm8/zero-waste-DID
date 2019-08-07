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
        "description": "aluminum"
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