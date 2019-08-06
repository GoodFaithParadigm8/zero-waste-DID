# Metal Types

+ Aluminium
+ Brass and Bronze
+ Cast Iron
+ Copper
+ Steel
+ Tin 

### Example JSON-LD

```javascript
<script type="application/ld+json">{
    "@context": "https://schema.org",
    "@type": "Packaging", // could be type Recycable ? Material
    "material": "Aluminum",
    "size": "12 oz", // optional
    "dryWeight": "4 oz", // optional
    "image": { // perhaps in the future include image for AI 
        "@type": "imageObject",
        "url": "http://example.com/images/image.png",
        "height": "640",
        "width": "800"
    },
    "publisher": {
        "@type": "Organization",
        "name": "Publisher name",
        "logo": {
            "@type": "imageObject",
            "url": "http://example.com/images/logo.jpg"
        }
    }
}</script>
```