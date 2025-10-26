# Principled Baker

> A powerful Blender add-on for baking PBR textures with just a few clicks

[![Blender](https://img.shields.io/badge/Blender-4.5.3-orange.svg)](https://www.blender.org/)
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

## 📋 Table of Contents

- [About](#about)
- [Version Compatibility](#version-compatibility)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Bake Modes](#bake-modes)
- [Limitations & Known Issues](#limitations--known-issues)
- [Community](#community)
- [License](#license)

## 🎨 About

Principled Baker is a Blender add-on that simplifies the process of baking PBR (Physically Based Rendering) textures. It automatically detects what needs to be baked from your Principled BSDF shader and allows you to bake almost all shader inputs to image textures with minimal effort.

## ⚙️ Version Compatibility

**✅ Tested with Blender 4.5.3**

> **Note:** This add-on has been tested and confirmed to work with Blender 4.5.3. Other versions have not been tested and may not work as expected.

For older Blender versions:
- [Principled Baker for Blender 2.79](https://github.com/danielenger/Principled-Baker_for_2-79)

## ✨ Features

### Automatic Detection & Baking
- 🔍 **Smart Detection** - Automatically detects what needs to be baked based on connected shader inputs
- 🎯 **Manual Selection** - Choose specific texture channels to bake
- 🖼️ **Comprehensive Baking** - Bake almost all Principled BSDF inputs including:
  - Color, Metallic, Roughness
  - Alpha, Emission, Ambient Occlusion
  - Diffuse, Glossiness (inverted Roughness)
  - Bump (as heightmap), Vertex Color, Material ID

### Workflow Features
- 🎨 **Auto Material Creation** - Automatically creates new materials with baked image texture nodes
- 📐 **Auto UV Unwrap** - Smart UV Project and Lightmap Pack options
- ✨ **Auto Smooth Control** - Manage auto smooth settings (object/on/off)

## 📥 Installation

1. Download the latest release or clone this repository
2. Open Blender 4.5.3
3. Navigate to `Edit` > `Preferences` > `Add-ons`
4. Click `Install` and select the downloaded add-on folder or ZIP file
5. Enable "Principled Baker" in the add-ons list
6. The add-on will appear in the Shader Editor Toolbar

## 🚀 Usage

1. Open the **Shader Editor** in Blender
2. Select the object(s) you want to bake
3. Configure your bake settings in the Principled Baker panel
4. Choose your desired bake mode (see below)
5. Click **Bake** to generate your textures

## 🎯 Bake Modes

Principled Baker offers three flexible baking modes:

### Combined Mode
Bake a single selected object or multiple objects with shared UV maps. Works like Blender's default bake behavior.

### Single/Batch Mode
Bake each selected object separately, perfect for processing multiple objects with unique textures.

### Selected to Active
Bake from selected objects to the active object, useful for transferring details between models.

## ⚠️ Limitations & Known Issues

### Important Warnings
- ⚠️ **Be careful with the Overwrite option!** It will permanently replace existing files
- 🔄 **Cycles Only** - Baking works in Cycles render engine only (Baking "in" Eevee may crash Blender)

### Technical Limitations
- **Displacement** - Only works with Displacement nodes; Vector Displacement is not supported
- **Transparent Colors** - Color inputs from transparent nodes (Transparent, Translucent, Glass) are ignored by default to prevent false colors. Disable "Exclude Transparent Colors" to include them
- **Normal/Bump Maps** - If both Normal Map and Bump Map are baked, the Bump node won't be linked in the new material
- **Complex Shaders** - Results from complex mixed shader node trees may not always be useful
- **Material ID** - Using Material Name for Material ID colors may produce duplicate colors

### Known Issues
- ⚙️ Subsurface Radius results may not be useful
- 🔀 Tangent results might not be useful
- 📦 Batch baking with shared materials can produce incomplete image textures

## 💬 Community

Join the discussion on Blender Artists:
- [Principled Baker Thread](https://blenderartists.org/t/addon-principled-baker/1102187)

## 📄 License

This project is licensed under the GNU General Public License v3.0 - see the code headers for details.

**Copyright (C) 2018-2024 Daniel Engler**

---

<div align="center">
Made with ❤️ for the Blender community
</div>
