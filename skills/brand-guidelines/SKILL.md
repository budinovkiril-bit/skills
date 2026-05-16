---
name: brand-guidelines
description: Applies a project's brand colors and typography to any artifact that may benefit from consistent branding. Use it when brand colors, style guidelines, visual formatting, or company design standards need to be applied to any project.
license: Complete terms in LICENSE.txt
---

# Brand Guidelines Skill

## Overview

This skill applies any project's brand colors and typography to artifacts such as presentations, documents, and other visual assets. It is not tied to any specific company or organization — it works with whatever brand colors and fonts are provided for the current project.

**Keywords**: branding, corporate identity, visual identity, post-processing, styling, brand colors, typography, visual formatting, visual design, custom brand, project branding

## How It Works

When using this skill, provide the brand configuration for your project. The skill will apply the specified colors and fonts to the target artifact, ensuring consistent visual identity across all outputs.

## Brand Configuration

To use this skill, supply the following brand details for your project:

### Colors

Define the colors used in your brand. Common roles include:

- **Primary**: Main brand color for key elements (e.g., headings, buttons, highlights)
- - **Secondary**: Supporting color for accents and secondary elements
  - - **Background**: Default background color
    - - **Text**: Primary text color
      - - **Accent(s)**: Additional accent colors for shapes, dividers, or decorative elements
       
        - Example format:
        - ```
          primary: #RRGGBB
          secondary: #RRGGBB
          background: #RRGGBB
          text: #RRGGBB
          accent1: #RRGGBB
          accent2: #RRGGBB
          ```

          ### Typography

          Define the fonts used in your brand. Common roles include:

          - **Heading Font**: Font for titles and large headings (24pt and above)
          - - **Body Font**: Font for regular body text and smaller content
           
            - Example format:
            - ```
              heading_font: FontName (fallback: Arial)
              body_font: FontName (fallback: Georgia)
              ```

              > **Note**: Fonts should be pre-installed in your environment for best results. If custom fonts are unavailable, the skill will fall back to system defaults (Arial for headings, Georgia for body text).
              >
              > ## Features
              >
              > ### Smart Color Application
              > - Applies the project's primary color to headings and key structural elements
              > - - Uses secondary and accent colors for shapes, dividers, and decorative elements
              >   - - Selects text color intelligently based on background brightness for readability
              >     - - Maintains visual consistency across all elements of the artifact
              >      
              >       - ### Font Application
              >       - - Applies the specified heading font to all headings (24pt and larger)
              >         - - Applies the specified body font to all body text
              >           - - Falls back gracefully to Arial (headings) and Georgia (body) if custom fonts are not available
              >             - - Preserves text hierarchy and formatting throughout
              >              
              >               - ### Shape and Accent Colors
              >               - - Non-text shapes use the defined accent colors
              >                 - - Cycles through available accent colors for visual variety
              >                   - - Maintains visual interest while staying on-brand
              >                    
              >                     - ## Technical Details
              >                    
              >                     - ### Font Management
              >                     - - Uses system-installed fonts when available
              >                       - - Provides automatic fallback to Arial (headings) and Georgia (body)
              > - No font installation required — works with existing system fonts
              > - - For best results, pre-install the project's brand fonts in your environment
              >  
              >   - ### Color Application
              >   - - Uses RGB color values for precise brand matching
              >     - - Applied via `python-pptx`'s `RGBColor` class (for presentations)
              >       - - Maintains color fidelity across different systems and output formats
