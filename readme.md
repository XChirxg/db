# Character Assets API - Complete Guide

A comprehensive collection of Indian dress character customization assets for apps and games with intelligent thumbnail cropping system.

## 📋 Overview

This asset library contains 245+ high-quality PNG images organized into character parts for creating customizable avatars. All assets feature Indian clothing styles and are designed for portrait-oriented applications with support for both individual character creation and couple positioning.

## 🎯 Technical Specifications

- **Image Format**: PNG with transparency
- **Resolution**: 1080x1920 (Portrait orientation)
- **Background**: Transparent
- **Layer Alignment**: Pre-positioned for proper layering
- **Character Positioning**: Boy and girl characters can be placed together as they're pre-separated in the images to appear as if standing together
- **Thumbnail System**: Intelligent cropping system for compact preview images

## 📁 Asset Structure

**Repository**: https://github.com/xchirxg/db

```
├── background/          # 4 background scenes
├── boy/                 # 113+ male character assets
└── girl/                # 128+ female character assets
    ├── backhair/        # Hair behind the character
    ├── bottom/          # Lower body clothing
    ├── face/
    │   ├── eyeball/     # Eye variations
    │   ├── eyebrow/     # Eyebrow styles
    │   └── mouth/       # Mouth expressions
    ├── fronthair/       # Hair in front of character
    ├── full/            # Complete outfit sets
    ├── shoes/           # Footwear
    ├── skin/            # Base body + skin tone
    ├── thing1/          # Accessories & extras
    └── top/             # Upper body clothing
```

## 🖼️ Thumbnail Cropping System

### Overview
The thumbnail system uses intelligent cropping to create compact preview images (120x120px) from the original 1080x1920px assets. This allows for efficient selection interfaces while maintaining image quality.

### Crop Configurations

#### Boy Character Assets

| Category | Crop Area (x, y, width, height) | Focus Area |
|----------|--------------------------------|------------|
| **Backhair** | `255, 520, 352, 358` | Hair region behind head |
| **Bottom** | `277, 1056, 292, 466` | Lower body clothing |
| **Fronthair** | `275, 570, 332, 294` | Hair region in front |
| **Full** | `251, 818, 326, 706` | Complete outfit view |
| **Shoes** | `309, 1309, 244, 216` | Footwear area |
| **Skin** | `373, 659, 114, 110` | Face/skin tone |
| **Top** | `281, 842, 292, 442` | Upper body clothing |

#### Girl Character Assets

| Category | Crop Area (x, y, width, height) | Focus Area |
|----------|--------------------------------|------------|
| **Backhair** | `467, 594, 454, 674` | Hair region behind head |
| **Bottom** | `493, 1068, 374, 448` | Lower body clothing |
| **Full** | `499, 931, 388, 592` | Complete outfit view |
| **Top** | `513, 925, 338, 456` | Upper body clothing |

### Implementation

```javascript
// Example: Boy backhair thumbnail cropping
const backhairCropConfig = {
    x: 255,
    y: 520,
    width: 352,
    height: 358
};

function cropBackhair(canvas, ctx, image) {
    const config = backhairCropConfig;
    
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    ctx.drawImage(
        image,
        config.x, config.y, config.width, config.height,
        0, 0, canvas.width, canvas.height
    );
}
```

### CSS for Thumbnails

```css
.thumbnail {
    width: 120px;
    height: 120px;
    object-fit: cover;
    border-radius: 8px;
    border: 2px solid #ddd;
    transition: all 0.3s ease;
    cursor: pointer;
}

.thumbnail:hover {
    border-color: #667eea;
    transform: scale(1.05);
}

.thumbnail.selected {
    border-color: #667eea;
    box-shadow: 0 0 10px rgba(102, 126, 234, 0.5);
}
```

## 🗂️ Asset Categories Explained

### Backgrounds (4 items)
- Environmental scenes for character placement
- Use as base layer behind all character elements

### Skin (Boy: 5+, Girl: 6+)
- **Contains**: Base body shape + skin color
- **Purpose**: Foundation layer for all clothing
- **Usage**: Always required as the character base
- **Layer Position**: Above background, below all clothing

### Hair System
- **Backhair**: Hair strands that go behind the character
  - Layer Position: Behind skin layer
  - Required: Use before applying skin layer
- **Fronthair**: Hair strands that appear in front
  - Layer Position: Top layer (above all other elements)

### Clothing - Individual Pieces
- **Bottom** (18+ items each): Pants, skirts, shorts, traditional Indian lower garments
- **Top** (Boy: 23+, Girl: 34+): Shirts, jackets, traditional Indian upper garments
- **Shoes** (Boy: 4+, Girl: 10+): Footwear of various styles

### Clothing - Complete Sets
- **Full** (Boy: 16+, Girl: 28+): Pre-matched complete outfits
- **Important**: When using full outfits, DO NOT use individual top, bottom, or shoes
- **Advantage**: Perfectly coordinated looks with guaranteed style matching

### Facial Features
- **Eyeball** (Boy: 11+, Girl: 10+): Eye color and style variations
- **Eyebrow** (5+ each): Eyebrow shape and thickness options
- **Mouth** (4+ each): Expression and lip style variations

### Accessories
- **Thing1** (Boy: 3+, Girl: 5+): Additional accessories, jewelry, props, or special items

## 🎨 Layer Rendering Order (Bottom to Top)

Follow this exact order for proper character rendering:

```
1. Background (base scene)
2. Backhair (hair behind character)
3. Skin (body + skin tone)
4. Shoes (footwear) OR skip if using Full  
5. Bottom (lower clothing) OR skip if using Full
6. Top (upper clothing) OR skip if using Full
7. Full (complete outfit) OR skip if using individual pieces (include shoes, bottom and top)
8. Eyeball (eyes)
9. Eyebrow (eyebrows)
10. Mouth (facial expression)
11. Fronthair (hair in front)
12. Thing1 (accessories)
```

## 👫 Couple Positioning

- **Boy and girl characters are pre-positioned** to appear as if standing together
- **No manual positioning required** when using both characters
- **Characters are already separated** in their respective images
- **Perfect for couple/relationship apps** and multi-character scenarios

## 📡 API Access

### JSON Configuration URL
```
https://raw.githubusercontent.com/xchirxg/db/main/character-assets.json
```

### Direct Image Access Pattern
```
https://raw.githubusercontent.com/xchirxg/db/main/{category}/{filename}
```

### Examples
```
https://raw.githubusercontent.com/xchirxg/db/main/girl/top/15.png
https://raw.githubusercontent.com/xchirxg/db/main/boy/skin/3.png
https://raw.githubusercontent.com/xchirxg/db/main/background/2.png
```

## ⚡ Implementation Guide

### Basic Character Creation Steps

1. **Fetch the JSON configuration file**
2. **Select desired character gender** (boy/girl) or both for couples
3. **Choose skin tone** from skin category
4. **Decide between individual pieces OR complete outfit**:
   - Individual: Select top + bottom + shoes separately
   - Complete: Select one item from "full" category (skip top/bottom/shoes)
5. **Add facial features** (eyeball, eyebrow, mouth)
6. **Add hair** (backhair first, fronthair last)
7. **Optionally add background and accessories**
8. **Layer images in the specified order**

### Outfit Combination Rules

- **Option A**: `skin + top + bottom + shoes + (optional accessories)`
- **Option B**: `skin + full + (optional accessories)`
- **Never mix**: Don't use full outfits with individual top/bottom/shoes

### Thumbnail vs Full Image Usage

- **For Selection UI**: Use cropped thumbnails with the provided crop configurations
- **For Character Rendering**: Use original full-size images (1080x1920px)
- **Performance**: Cache cropped thumbnails for faster loading
- **Quality**: Original images maintain full detail for final character display

## 📊 Asset Counts Summary

- **Total Assets**: 245+ images (continuously growing)
- **Backgrounds**: 4
- **Boy Assets**: 113+
- **Girl Assets**: 128+
- **Categories**: 12 different types
- **Future Growth**: Regular additions planned

## 🔄 Version Information

- **Current Version**: 2.0.0
- **Last Updated**: 2025
- **Compatibility**: All modern web browsers and mobile applications
- **File Format Support**: PNG with alpha transparency
- **Breaking Changes**: Updated file naming from (1).png to 1.png format

## 💡 Best Practices

### General Usage
- Always use the recommended layer order for proper visual results
- Cache the JSON configuration to reduce API calls
- Implement random selection for variety in character generation
- Consider preloading commonly used assets for better performance

### Outfit Selection
- Use the "full" category for quick, guaranteed matching outfits
- Use individual pieces when more customization control is needed

### Thumbnail Implementation
- Use cropped thumbnails for selection interfaces
- Apply hover effects for better user experience
- Implement selection states with visual feedback
- Cache cropped images to improve performance

### Couple/Multi-Character Scenarios
- Characters are pre-positioned for couple placement
- No additional positioning logic required
- Both characters can share the same background
- Layer order applies to each character independently

## 🚫 Common Mistakes to Avoid

- Don't skip the skin layer (always required)
- Don't put backhair in front of skin
- Don't mix full outfits with individual clothing pieces
- Don't forget to layer fronthair on top
- Don't use bottom/top/shoes when using full outfits
- Don't apply manual positioning for couple scenarios

## 📞 Repository Information

- **Username**: xchirxg
- **Repository**: db
- **Access**: Public (no authentication required)
- **CDN**: GitHub Raw Content Delivery
- **Updates**: Regular asset additions planned

## 🚀 Integration Examples

### JavaScript/React Thumbnail Implementation

```javascript
// Fetch the assets configuration
const response = await fetch('https://raw.githubusercontent.com/xchirxg/db/main/character-assets.json');
const assetsData = await response.json();

// Create thumbnail with cropping
function createThumbnail(imageUrl, category, gender) {
    const canvas = document.createElement('canvas');
    const ctx = canvas.getContext('2d');
    canvas.width = 120;
    canvas.height = 120;
    
    const img = new Image();
    img.onload = () => {
        const cropConfig = getCropConfig(category, gender);
        ctx.drawImage(
            img,
            cropConfig.x, cropConfig.y, cropConfig.width, cropConfig.height,
            0, 0, canvas.width, canvas.height
        );
    };
    img.src = imageUrl;
    
    return canvas;
}

// Get appropriate crop configuration
function getCropConfig(category, gender) {
    const cropConfigs = {
        boy: {
            backhair: { x: 255, y: 520, width: 352, height: 358 },
            bottom: { x: 277, y: 1056, width: 292, height: 466 },
            // ... other configurations
        },
        girl: {
            backhair: { x: 467, y: 594, width: 454, height: 674 },
            bottom: { x: 493, y: 1068, width: 374, height: 448 },
            // ... other configurations
        }
    };
    
    return cropConfigs[gender][category];
}
```

### Character Layer Composition

```javascript
// Layer the images for final character
const layers = [
    assetsData.backgrounds.items[0], // Background
    boyBackhair, // Boy's back hair
    girlBackhair, // Girl's back hair  
    boySkin, // Boy's skin
    girlSkin, // Girl's skin
    boyTop, // Boy's clothing
    girlTop, // Girl's clothing
    boyFronthair, // Boy's front hair
    girlFronthair // Girl's front hair
];

// Render all layers
layers.forEach(layer => {
    if (layer) {
        ctx.drawImage(layer, 0, 0);
    }
});
```

## 🔮 Future Roadmap

- **More Asset Categories**: Additional clothing styles and accessories
- **Seasonal Collections**: Holiday and seasonal-themed assets
- **Animation Support**: Sprite sheets for animated characters
- **Advanced Cropping**: Dynamic crop regions based on asset content
- **API Enhancements**: RESTful API with filtering and search capabilities

---

**Note**: This is a living document that will be updated as new assets and features are added to the collection. Check back regularly for updates and new categories.
