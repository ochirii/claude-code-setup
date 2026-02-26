# PowerPoint Content Generation

**Claude Skill: Create, edit, and modify PowerPoint presentations**

This skill provides comprehensive PowerPoint generation capabilities using python-pptx and custom scripts.

## Core Functions

### 1. Text Content Modification

**Extract, analyze, and replace text content while preserving formatting**

```python
# Extract text inventory from presentation
python .claude/skills/pptx/scripts/inventory.py input.pptx inventory.json

# Apply text replacements
python .claude/skills/pptx/scripts/replace.py input.pptx replacements.json output.pptx
```

**Use Cases:**
- Generate presentation variations (e.g., different audiences, languages)
- Automate content updates across multiple decks
- Ensure consistent terminology and formatting
- Batch modify presentations with template data

### 2. Slide Reordering and Duplication

**Rearrange, duplicate, or subset slides**

```python
# Reorder slides (0-indexed)
python .claude/skills/pptx/scripts/rearrange.py template.pptx output.pptx 0,5,5,3,1
# Creates output.pptx with slides in order: 0, 5 (twice), 3, 1
```

**Use Cases:**
- Create audience-specific versions of a master deck
- Build presentations from a slide library
- Generate multiple deck variants from one source

### 3. Thumbnail Generation

**Create visual slide overviews as grid layouts**

```python
# Generate thumbnail grid
python .claude/skills/pptx/scripts/thumbnail.py presentation.pptx

# With custom columns and placeholder outlines
python .claude/skills/pptx/scripts/thumbnail.py deck.pptx grid --cols 4 --outline-placeholders
```

**Use Cases:**
- Generate slide previews for review
- Create presentation overview documents
- Visualize deck structure and flow
- Identify text placeholders for editing

### 4. HTML to PowerPoint Conversion

**Convert precisely-positioned HTML slides to PowerPoint**

```javascript
const pptx = new pptxgen();
pptx.layout = 'LAYOUT_16x9';

const { slide, placeholders } = await html2pptx('slide.html', pptx);
slide.addChart(pptx.charts.LINE, data, placeholders[0]);

await pptx.writeFile('output.pptx');
```

**Use Cases:**
- Generate slides from web content or data visualizations
- Create presentations programmatically with precise positioning
- Convert design mockups to PowerPoint format
- Automate chart and data integration

## Technical Approach

### Text Processing Pipeline
1. **Extraction**: `inventory.py` extracts all text with position, formatting, and structure data
2. **Analysis**: Detects text overflow, shape overlap, and formatting issues  
3. **Modification**: `replace.py` applies changes while preserving paragraph properties (bullets, alignment, spacing, fonts)
4. **Validation**: Ensures no overflow worsens and formatting stays consistent

### Key Capabilities
- Preserves all paragraph formatting (bullets, alignment, spacing)
- Handles nested GroupShapes with absolute positioning
- Detects and prevents text overflow issues
- Maintains font properties (size, weight, color, style)
- Supports inline formatting (bold, italic, underline within text)

## Documentation

See detailed guides for each component:
- [`html2pptx.md`](html2pptx.md) - HTML to PowerPoint conversion
- [`ooxml.md`](ooxml.md) - Direct PPTX XML manipulation reference

## Installation

```bash
pip install python-pptx Pillow

# For HTML conversion (requires Node.js)
npm install pptxgenjs playwright sharp

# For thumbnail generation (requires LibreOffice and poppler-utils)
brew install libreoffice poppler  # macOS
```
