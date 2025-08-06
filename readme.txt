# Character Assets API - Complete Guide

A comprehensive collection of Indian dress character customization assets for apps and games.

## 📋 Overview

This asset library contains **245 high-quality PNG images** organized into character parts for creating customizable avatars. All assets feature Indian clothing styles and are designed for portrait-oriented applications.

## 🎯 Technical Specifications

- **Image Format**: PNG with transparency
- **Resolution**: 1080x1920 (Portrait orientation)
- **Background**: Transparent
- **Layer Alignment**: Pre-positioned for proper layering
- **Character Positioning**: Boy and girl characters stand at different locations, but clothing items align correctly on their respective layers

## 📁 Asset Structure

```
Repository: https://github.com/xchirxg/db
├── background/          # 4 background scenes
├── boy/                 # 113 male character assets
└── girl/                # 128 female character assets
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

## 🗂️ Asset Categories Explained

### **Backgrounds** (4 items)
- Environmental scenes for character placement
- Use as base layer behind all character elements

### **Skin** (Boy: 5, Girl: 6)
- **Contains**: Base body shape + skin color
- **Purpose**: Foundation layer for all clothing
- **Usage**: Always required as the character base
- **Layer Position**: Above background, below all clothing

### **Hair System**
- **Backhair**: Hair strands that go behind the character
  - **Layer Position**: Behind skin layer
  - **Required**: Use before applying skin layer
- **Fronthair**: Hair strands that appear in front
  - **Layer Position**: Top layer (above all other elements)

### **Clothing - Individual Pieces**

#### **Bottom** (18 items each)
- **Contains**: Pants, skirts, shorts, traditional Indian lower garments
- **Excludes**: Shoes (separate category)
- **Compatibility**: Use with individual top and shoes

#### **Top** (Boy: 23, Girl: 34)
- **Contains**: Shirts, jackets, traditional Indian upper garments (kurtas, tops, etc.)
- **Compatibility**: Use with individual bottom and shoes

#### **Shoes** (Boy: 4, Girl: 10)
- **Contains**: Footwear of various styles
- **Compatibility**: Use with individual top and bottom pieces

### **Clothing - Complete Sets**

#### **Full** (Boy: 16, Girl: 28)
- **Contains**: Pre-matched complete outfits (top + bottom + shoes combined)
- **Important**: When using full outfits, DO NOT use individual top, bottom, or shoes
- **Advantage**: Perfectly coordinated looks with guaranteed style matching

### **Facial Features**
- **Eyeball** (Boy: 11, Girl: 10): Eye color and style variations
- **Eyebrow** (5 each): Eyebrow shape and thickness options
- **Mouth** (4 each): Expression and lip style variations

### **Accessories**
- **Thing1** (Boy: 3, Girl: 5): Additional accessories, jewelry, props, or special items

## 🎨 Layer Rendering Order (Bottom to Top)

Follow this exact order for proper character rendering:

```
1. Background (base scene)
2. Backhair (hair behind character)
3. Skin (body + skin tone)
4. Bottom (lower clothing) OR skip if using Full
5. Shoes (footwear) OR skip if using Full  
6. Top (upper clothing) OR skip if using Full
7. Full (complete outfit) OR skip if using individual pieces
8. Thing1 (accessories)
9. Eyeball (eyes)
10. Eyebrow (eyebrows)
11. Mouth (facial expression)
12. Fronthair (hair in front)
```

## 📡 API Access

### JSON Configuration URL
```
https://raw.githubusercontent.com/xchirxg/db/main/character-assets.json
```

### Direct Image Access Pattern
```
https://raw.githubusercontent.com/xchirxg/db/main/{category}/{filename}
```

Examples:
- `https://raw.githubusercontent.com/xchirxg/db/main/girl/top/(15).png`
- `https://raw.githubusercontent.com/xchirxg/db/main/boy/skin/(3).png`
- `https://raw.githubusercontent.com/xchirxg/db/main/background/(2).png`

## ⚡ Quick Implementation Guide

### Basic Character Creation Steps:
1. Fetch the JSON configuration file
2. Select desired character gender (boy/girl)
3. Choose skin tone from skin category
4. Decide between individual pieces OR complete outfit:
   - **Individual**: Select top + bottom + shoes separately
   - **Complete**: Select one item from "full" category (skip top/bottom/shoes)
5. Add facial features (eyeball, eyebrow, mouth)
6. Add hair (backhair first, fronthair last)
7. Optionally add background and accessories
8. Layer images in the specified order

### Outfit Combination Rules:
- **Option A**: skin + top + bottom + shoes + (optional accessories)
- **Option B**: skin + full + (optional accessories)
- **Never mix**: Don't use full outfits with individual top/bottom/shoes

## 🎭 Character Positioning Notes
- Boy and girl characters have different standing positions in the frame
- All clothing items are pre-positioned to align correctly with their respective character base
- No manual positioning adjustments needed when following proper layering order

## 📊 Asset Counts Summary
- **Total Assets**: 245 images
- **Backgrounds**: 4
- **Boy Assets**: 113
- **Girl Assets**: 128
- **Categories**: 12 different types

## 🔄 Version Information
- **Current Version**: 1.0.0
- **Last Updated**: 2024
- **Compatibility**: All modern web browsers and mobile applications
- **File Format Support**: PNG with alpha transparency

## 💡 Best Practices
- Always use the recommended layer order for proper visual results
- Cache the JSON configuration to reduce API calls
- Implement random selection for variety in character generation
- Consider preloading commonly used assets for better performance
- Use the "full" category for quick, guaranteed matching outfits
- Use individual pieces when more customization control is needed

## 🚫 Common Mistakes to Avoid
- Don't skip the skin layer (always required)
- Don't put backhair in front of skin
- Don't mix full outfits with individual clothing pieces
- Don't forget to layer fronthair on top
- Don't use bottom/top/shoes when using full outfits

## 📞 Repository Information
- **Username**: xchirxg
- **Repository**: db
- **Access**: Public (no authentication required)
- **CDN**: GitHub Raw Content Delivery
