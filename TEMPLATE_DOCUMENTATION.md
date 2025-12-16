# MedyGenes Report Template Documentation

## Table of Contents
1. [Overview](#overview)
2. [File Structure](#file-structure)
3. [Page Structure](#page-structure)
4. [Color Scheme & Branding](#color-scheme--branding)
5. [Layout Structure](#layout-structure)
6. [Section Breakdown](#section-breakdown)
7. [Components & Styling](#components--styling)
8. [Data Organization](#data-organization)
9. [Interactive Elements](#interactive-elements)
10. [Print/PDF Considerations](#printpdf-considerations)
11. [Customization Guide](#customization-guide)
12. [Known Issues & Bug Fixes](#known-issues--bug-fixes)

---

## Overview

This is a comprehensive HTML template for generating patient pharmacogenetic reports in PDF format. The template is designed to display genetic analysis results, drug recommendations, and clinical guidance in a professional, medical report format optimized for A4 printing.

**Key Features:**
- **Multi-page A4 layout** (4 pages: Patient Info, Drug Genetics, Drug Details, Genotype Details)
- **Print-optimized styling** with proper page breaks
- **Interactive tooltips** and navigation links
- **Color-coded drug status indicators** (green/orange/red pills)
- **ChEMBL-style drug icons** (5 icons per drug)
- **Responsive table layouts** with genetic findings
- **Professional medical branding** with MedyGenes logo
- **Source attribution** with CPIC and FDA logos

---

## File Structure

```
reports/
├── index.html              # Main template file (1393 lines)
├── assets/
│   └── medygenes_logosvg.svg  # Company logo (blue: #00B2FF, green: #0CCA4A)
└── TEMPLATE_DOCUMENTATION.md  # This documentation file
```

---

## Page Structure

The report is organized into **4 separate A4 pages**:

### Page 1: Patient Information & Prescription
- **Header**: MedyGenes logo + contact info
- **Patient Section**: All patient details (name, age, sex, physician, report ID, patient ID, conditions, health insurance, patient details)
- **Prescription & Recommendation Section**: Color-coded pills with links to drug-specific findings
- **Page Number**: "Page 1" (bottom right)

### Page 2: Drug-Specific Genetic Findings
- **Header**: MedyGenes logo + contact info
- **Drug-Specific Genetic Findings Section**: Multiple drug cards, each containing:
  - Drug name (color-coded: orange for dose-change, green for normal, red for bad)
  - Check Interaction/Check Dose/Alternative Drug tags with tooltips
  - Genetic findings table
  - Clinical Summary
  - Drug mechanism & implication
  - Sources (CPIC, FDA) in pill format
- **Page Number**: "Page 2" (bottom right)

### Page 3: Drug Details
- **Header**: MedyGenes logo + contact info
- **Drug Details Section**: Comprehensive information for each drug:
  - Drug name with ChEMBL-style icons (5 icons)
  - Dosage, How It Works, Genetic Considerations, Watch For
  - Color-coded info cards (important/warning/success)
- **Page Number**: "Page 3" (bottom right)

### Page 4: Genotype Details
- **Header**: MedyGenes logo + contact info
- **Genotype Details Table**: Complete genotype information with:
  - Gene, Allele, Description, Level of Evidence, Clinical Type
  - Alleles stacked vertically under same gene
- **Footer**: Confidential notice + copyright
- **Page Number**: "Page 4" (bottom right)

**Page Styling:**
- Each page: `210mm x 297mm` (A4 size)
- Green accent bar at top (3px height)
- Page numbers in bottom right corner
- Proper page breaks for printing

---

## Color Scheme & Branding

### Primary Colors
- **Main Text**: `#123C4E` (Dark blue-gray)
- **Main Blue**: `#00B2FF` (Bright cyan-blue)
- **Main Green**: `#0CCA4A` (Bright green)
- **Muted Text**: `#4c4c4c` (Gray)
- **Background**: `#f7f7f7` (Light gray)
- **Panel Background**: `#ffffff` (White)
- **Border**: `#dedede` (Light gray)

### Status Colors

**Prescription Pills:**
- **Normal Metabolizer (Green)**: 
  - Background: `#f2fff9`
  - Text: `#187a4d`
  - Border: `#c7f1dc`

- **Dose Change Recommendation (Orange)**:
  - Background: `#fff8e6`
  - Text: `#a06100`
  - Border: `#f5d8a1`

- **Bad/Not Recommended (Red)**:
  - Background: `#fff4f4`
  - Text: `#9e1b1b`
  - Border: `#f5b5b5`

**Drug Name Colors (in Drug-Specific Genetic Findings):**
- **Atorvastatin**: Orange (`#a06100`) - matches dose-change pill
- **Metformin**: Green (`#187a4d`) - matches normal pill
- **Lisinopril**: Green (`#187a4d`) - matches normal pill
- **Clopidogrel**: Red (`#9e1b1b`) - matches bad pill

**Strength Badge Colors:**
- **Strong**: Red background (`#fff4f4`), red text (`#9e1b1b`)
- **Moderate**: Green background (`#f2fff9`), green text (`#187a4d`)
- **Optional**: Gray background (`#f8f8f8`), gray text (`#666`)
- **No Info**: White dash (`-`)

**Drug Info Cards (Drug Details Page):**
- **Important**: Orange background (`#fff8e6`), orange border (`#f5d8a1`)
- **Warning**: Red background (`#fff4f4`), red border (`#f5b5b5`)
- **Success**: Green background (`#f2fff9`), green border (`#c7f1dc`)
- **Default**: White background (`#ffffff`), gray border (`#e8e8e8`)

### Typography
- **Font Family**: `"Helvetica Neue", Helvetica, Arial, sans-serif`
- **Font Sizes**: 
  - Drug titles (Drug Details): 20px
  - Section headers: 15px
  - Body text: 14px
  - Small text: 12-13px
  - Labels: 11-12px
  - Page numbers: 11px

---

## Layout Structure

### Page Container
- **Class**: `.page`
- **Size**: `210mm x 297mm` (A4)
- **Padding**: 36px top, 44px sides, 48px bottom
- **Background**: White with subtle shadow
- **Border**: 1px solid border
- **Page Break**: `page-break-after: always` (except last page)
- **Accent Bar**: 3px green gradient at top

### Header Section
- **Class**: `.topbar`
- **Layout**: Flexbox with space-between
- **Border**: 2px solid accent color (green) at bottom
- **Components**:
  1. Brand section (logo + subtitle)
  2. Contact information (right-aligned)

### Brand Section
- **Logo**: SVG image from `assets/medygenes_logosvg.svg`
- **Logo Height**: 40px
- **Logo Colors**: Blue (`#00B2FF`), Green (`#0CCA4A`)
- **Subtitle**: "Genomic Compatibility Report" (below logo, 12px)
- **Layout**: Vertical stack (flex-direction: column)

### Contact Information
- **Website**: medigenes.co.il
- **Phone**: +1 (555) 321-9876
- **Email**: support@medygenes.com
- **Address**: Yigal Alon 94, Tel Aviv
- **Alignment**: Right-aligned
- **Font Size**: 13px

---

## Section Breakdown

### 1. Patient Section (Page 1)
**Position**: First section after header

**Structure**:
- **Title**: "Patient"
- **Layout**: 3-column grid (`.meta-grid`)
- **Fields**:
  - Name
  - Age
  - Sex
  - Physician
  - Report ID
  - Collected Date
  - Patient ID
  - Conditions
  - Health Insurance (Maccabi)
  - Patient Details (plain text chips: Vegan, Lactose, Non-Smoke, Allergy, Monitor)

**Styling**:
- Each field has a label (uppercase, muted color, 12px)
- Patient Details chips are plain text (14px, no colors/borders)
- Consistent font family: Helvetica/Arial

---

### 2. Prescription & Recommendation Section (Page 1)
**Position**: Second section on Page 1

**Structure**:
- **Title**: "Prescription & Recommendation"
- **Pill List**: Horizontal flex container with pills
- **Notes**: Explanatory text below pills

**Pill Format**:
- **Underlined links** (no icons)
- **Format**: `<strong>Brand Name</strong> — Generic Name Dosage`
- **Links**: Each pill links to corresponding drug-specific finding section (`#finding-[drugname]`)

**Pill Status Classes**:
- `.pill.normal` - Green (normal metabolizer)
- `.pill.dose-change` - Orange (dose adjustment needed)
- `.pill.bad` - Red (not recommended)

**Example Pills**:
- Lipitor — Atorvastatin 20mg (orange - dose change) → `#finding-atorvastatin`
- Glucophage — Metformin 500mg (green - normal) → `#finding-metformin`
- Zestril — Lisinopril 10mg (green - normal) → `#finding-lisinopril`
- Plavix — Clopidogrel 75mg (red - not recommended) → `#finding-clopidogrel`

---

### 3. Drug-Specific Genetic Findings Section (Page 2)
**Position**: Main section on Page 2

**Structure**: Multiple drug cards (`.drug-card`), each with border

**Each Drug Card Contains**:

#### A. Drug Header (`.drug-head`)
- **Drug Title**: Clickable link to drug details section
  - Format: `Brand Name — Generic Name Dosage`
  - Color-coded based on pill status (orange/green/red)
- **Drug Head Items** (`.drug-head-items`): Three tags with tooltips
  1. **Check Interaction**: Shows drug-drug interactions
  2. **Check Dose**: Indicates if dose is too high or appropriate
  3. **Alternative Drug**: Suggests alternatives based on genetics

**Tag Tooltips**:
- Hover to reveal detailed information
- Positioned above tag with arrow pointer
- Black background with white text
- Max-width: 280px, wraps text
- Smooth fade-in animation

#### B. Genetic Findings Table
**Columns**:
1. **Gene**: Gene name (e.g., SLCO1B1, CYP2C19, ABCB1)
2. **Genotype**: Two alleles separated by `/` (clickable links)
   - Format: `*5 / *5` or `C / A` or `*2 / *2`
   - Each allele links to genotype details section
3. **Phenotype**: Phenotype description
4. **Description**: Detailed explanation
5. **Clinical Recommendation**: Action items for clinicians
6. **Strength**: Badge showing strength level
   - Options: Moderate, Strong, Optional, or `-` (dash)

**Table Styling**:
- Dark header (`#0f0f0f` background, white text)
- Alternating row colors (odd rows: `#fafafa`)
- Borders between rows
- Clickable genotype links (underlined, green color)
- Warning rows: Red background with warning icon for "Not recommended"

#### C. Clinical Summary
- **Position**: After table, before Drug mechanism
- **Format**: Same styling as Drug mechanism/implication
- **Label**: `<strong>Clinical Summary:</strong>`
- **Content**: Brief summary of genetic considerations

#### D. Drug Mechanism & Implication
- **Drug mechanism**: How the drug works
- **Drug implication**: Link to detailed drug information

#### E. Sources (Pill Format - Clickable)
- **Position**: Inside detail-notes div, at the end
- **Format**: Pill-shaped container with circular logos (clickable link)
- **Functionality**: Clicking sources opens ChEMBL compound page in new tab
- **Icons**: 
  - CPIC: Favicon from `https://cpicpgx.org/favicon.ico`
  - FDA: Favicon from `https://www.fda.gov/favicon.ico`
- **Styling**: 
  - Pill shape (`border-radius: 999px`)
  - Gray background (`#f5f5f5`)
  - Circular icons (`border-radius: 50%`)
  - Text: "Sources: CPIC, FDA"
  - Hover effect: Background darkens to `#e8e8e8`
- **ChEMBL Links**:
  - Atorvastatin: `https://www.ebi.ac.uk/chembl/explore/compound/CHEMBL1487`
  - Clopidogrel: `https://www.ebi.ac.uk/chembl/explore/compound/CHEMBL1771`
  - Metformin: `https://www.ebi.ac.uk/chembl/explore/compound/CHEMBL1431`
  - Lisinopril: `https://www.ebi.ac.uk/chembl/explore/compound/CHEMBL1237`

---

### 4. Drug Details Section (Page 3)
**Position**: Main section on Page 3

**Structure**: Multiple drug detail cards (no outer border on section)

**Each Drug Detail Card Contains**:

#### A. Drug Header
- **Drug Name**: Brand name (Generic name)
  - Font size: 20px
  - Border-bottom separator
  - Icons positioned below divider

#### B. ChEMBL-Style Icons (5 icons)
**Icons** (32px x 32px, positioned below drug name):
1. **Natural Product** (leaf icon) - Inactive (gray)
2. **Chemical Probe** (flask icon) - Inactive (gray)
3. **Rule Of Five** (stylized "5" in circle) - Active (green)
4. **Approved Drug** (checkmark) - Active (green)
5. **Synthetic** (molecule structure) - Active (green)

**Icon States**:
- **Active**: Green background (`#0CCA4A`), white icon
- **Inactive**: Gray background (`#f5f5f5`), gray icon (30% opacity)

#### C. Drug Information Grid (2 columns)
**Four Info Cards**:
1. **Dosage**: Standard dosage information
2. **How It Works**: Mechanism explanation
3. **Genetic Considerations**: Personalized genetic summary
   - Color-coded: Important (orange), Warning (red), Success (green)
4. **Watch For**: Side effects list (bullet points)

**Card Styling**:
- White background with subtle shadow
- Hover effect (lift + shadow increase)
- Left border indicator (colored based on type)
- Colored left border indicator bar

---

### 5. Genotype Details Section (Page 4)
**Position**: Main section on Page 4

**Structure**: Comprehensive table

**Table Columns**:
1. **Gene**: Gene name (with rowspan for multiple alleles)
2. **Allele**: Individual allele variant (clickable link)
3. **Description**: Clinical significance
4. **Level of Evidence**: 1A, 1B, 2A, 2B, 3, 4
5. **Clinical Type**: Toxicity, Efficacy, Metabolizer, etc.

**Table Format**:
- Each gene spans multiple rows (rowspan)
- Alleles stacked vertically under same gene
- Example: SLCO1B1 gene with two `*5` alleles (each in separate row)

**Footer**:
- Confidential notice
- Copyright: MedyGenes © 2025

---

## Components & Styling

### Tables
**General Styling**:
- Full width
- Border collapse
- Font size: 14px
- Header: Dark background (`#0f0f0f`), white text
- Alternating row backgrounds (`#fafafa` for odd rows)
- Padding: 12px vertical, 10px horizontal

**Special Table Features**:
- Rowspan for gene names in genotype table
- Clickable links in genotype columns (underlined)
- Badge components in Strength column
- Warning rows with red background and icon

### Badges
**Types**:
- **Strength badges**: Strong (red), Moderate (green), Optional (gray)
- **Impact badges** (legacy): High (red), Moderate (green), Low (blue)

**Styling**:
- Inline-block display
- Padding: 4px 10px
- Border-radius: 10px
- Font-weight: 600
- Font-size: 12px
- Letter-spacing: 0.3px

### Pills/Tags

**Prescription Pills**:
- Border-radius: 999px (fully rounded)
- Padding: 8px 12px
- Font-size: 13px
- Color-coded by status
- Underlined text
- Links to drug-specific findings

**Sources Pill**:
- Border-radius: 999px (pill shape)
- Padding: 8px 12px
- Background: `#f5f5f5`
- Border: 1px solid `#e0e0e0`
- Circular icons inside

**Drug Head Tags**:
- Border-radius: 8px
- Padding: 4px 10px
- Background: `#f5f5f5`
- Hover effect: Background change, border color change, slight lift
- Tooltip on hover

### Links
**Styling**:
- Color: Accent green (`#0CCA4A`)
- Text-decoration: Underline (always visible)
- Font-weight: 700
- Hover: Maintains underline

**Link Types**:
- Drug names → Drug details section (`#drug-[drugname]`)
- Genotypes → Genotype details section (`#geno-[gene]-[variant]`)
- Prescription pills → Drug-specific findings (`#finding-[drugname]`)
- Internal navigation anchors

### Sections
**General Section Styling**:
- Border: 1px solid border (except Drug Details section - no border)
- Border-radius: 14px
- Background: White with subtle gradient
- Padding: 18px top/left/right, 14px bottom
- Margin-bottom: 24px

**Section Headers**:
- Font-size: 15px
- Uppercase
- Letter-spacing: 0.2px
- Muted color
- Margin-bottom: 10px

**Drug Cards** (Drug-Specific Genetic Findings):
- Border: 1px solid border
- Border-radius: 12px
- Padding: 20px
- Background: White
- Box-shadow: Subtle shadow
- Margin-bottom: 16px

**Drug Cards** (Drug Details):
- Border-top: 3px solid accent green
- Border-radius: 12px
- Padding: 24px top, 20px sides/bottom
- Background: White
- Box-shadow: Subtle shadow
- Margin-bottom: 24px

---

## Data Organization

### Patient Data
Stored in `.meta-grid` (3-column grid):
- **Personal info**: Name, Age, Sex
- **Medical info**: Conditions, Patient Details (Vegan, Lactose, etc.)
- **Administrative**: Report ID, Patient ID, Collected Date
- **Provider info**: Physician, Health Insurance

### Drug Data Structure
Each drug has:
1. **Basic Info**: Name, dosage, brand name
2. **Status Indicators**: Normal/Dose-change/Bad (color-coded)
3. **Genetic Variants**: Array of gene/genotype/phenotype combinations
4. **Clinical Summary**: Brief genetic considerations
5. **Recommendations**: Clinical actions
6. **Mechanism**: How it works
7. **Implication**: Link to detailed information
8. **Sources**: CPIC, FDA (with logos)
9. **ChEMBL Icons**: 5 icons showing drug properties

### Genotype Data Structure
Each genotype entry:
- **Gene**: Gene name
- **Allele 1**: First allele variant
- **Allele 2**: Second allele variant
- **Description**: Clinical significance
- **Level of Evidence**: 1A, 1B, 2A, 2B, 3, 4
- **Clinical Type**: Toxicity, Efficacy, Metabolizer, etc.

---

## Interactive Elements

### Tooltips
**Implementation**: CSS `::after` pseudo-element with `data-tooltip` attribute

**Features**:
- Appears on hover
- Positioned above element
- Black background, white text
- Arrow pointer (CSS triangle)
- Smooth fade-in animation
- Text wrapping for long content

**Usage**:
```html
<div class="drug-head-item" data-tooltip="Tooltip text here">
  Content
</div>
```

### Anchor Links
**Navigation Pattern**:
- Drug names link to `#drug-[drugname]` sections
- Genotypes link to `#geno-[gene]-[variant]` sections
- Prescription pills link to `#finding-[drugname]` sections
- Smooth scroll behavior (browser default)

**Link Format**:
```html
<a class="detail-link" href="#drug-atorvastatin">Atorvastatin</a>
<a class="detail-link" href="#geno-slco1b1-5">*5</a>
<a href="#finding-atorvastatin" class="pill">Lipitor — Atorvastatin 20mg</a>
```

### Hover Effects
**Drug Head Tags**:
- Background color change
- Border color change to accent
- Transform: translateY(-1px) (slight lift)
- Transition: 0.2s ease

**Drug Info Cards**:
- Transform: translateY(-2px) (lift)
- Box-shadow increase
- Transition: 0.2s ease

**Links**:
- Maintain underline on hover
- Color remains accent green

---

## Print/PDF Considerations

### Print Media Query
```css
@media print {
  body { 
    background: #fff; 
    padding: 0; 
  }
  .sheet, .page { 
    box-shadow: none; 
    border: 1px solid #e0e0e0; 
    width: 210mm;
    height: 297mm;
    margin: 0;
    page-break-after: always;
  }
  .page:last-child {
    page-break-after: auto;
  }
  .section { 
    break-inside: avoid; 
  }
}
```

### Page Break Rules
- **@page**: A4 size, 0 margin
- **Page containers**: `page-break-after: always` (except last page)
- **Sections**: `break-inside: avoid` to prevent splitting

### Print Optimizations
- Removes background colors/shadows
- Ensures sections don't break across pages
- White background for printing
- No padding on body
- Maintains borders for page separation

### PDF Generation
**Recommended Tools**:
- Browser Print → Save as PDF
- Puppeteer/Playwright for automated generation
- wkhtmltopdf
- Chrome Headless

**Settings**:
- Paper size: A4
- Margins: Default or minimal
- Scale: 100%
- Background graphics: Enabled

---

## Customization Guide

### Changing Colors
**Primary Colors** (in `:root`):
```css
--text: #123C4E;        /* Main text color */
--accent: #0CCA4A;      /* Main green */
--muted: #4c4c4c;       /* Muted text */
--bg: #f7f7f7;          /* Background */
--panel: #ffffff;       /* Panel background */
--border: #dedede;      /* Borders */
```

**Status Colors**:
- Modify `.pill.normal`, `.pill.dose-change`, `.pill.bad` classes
- Update badge colors in `.badge.strength-*` classes
- Update drug name colors in `#finding-[drug] .drug-title a` selectors

### Adding New Drugs
1. Add pill to Prescription section with link to `#finding-[drugname]`
2. Copy a drug card structure in Drug-Specific Genetic Findings
3. Add ID: `id="finding-[drugname]"` to drug-card
4. Update drug name and dosage
5. Add genetic findings rows to table
6. Update Clinical Summary
7. Add drug details card in Drug Details section
8. Add appropriate status class to pill (normal/dose-change/bad)
9. Update ChEMBL icons (5 icons) with appropriate active/inactive states

### Adding New Genes/Genotypes
1. Add row to drug's genetic findings table
2. Create genotype detail entry in Genotype Details table
3. Add link anchor ID (`#geno-[gene]-[variant]`)
4. Ensure alleles are stacked vertically under same gene

### Modifying Layout
**Page Size**:
- Change `.page` width/height (currently 210mm x 297mm)
- Adjust padding/margins

**Grid Layouts**:
- Modify `.meta-grid` columns (currently 3)
- Adjust `.drug-grid` spacing
- Modify `.drug-info-grid` columns (currently 2)

**Typography**:
- Update font-family in `body`
- Adjust font sizes in respective classes

### Logo Replacement
1. Replace `assets/medygenes_logosvg.svg`
2. Update logo colors in SVG (blue: `#00B2FF`, green: `#0CCA4A`)
3. Adjust `.brand .mark` height if needed (currently 40px)

### Updating Source Icons
1. Replace favicon URLs in source-icon img tags
2. Update icon sizes in `.source-icon` class (currently 20px)
3. Modify pill styling in `.source-row` class

---

## Known Issues & Bug Fixes

### Fixed Issues
✅ **Page Structure**: All 4 pages properly separated with page breaks
✅ **Source Icons**: Using actual CPIC and FDA favicons
✅ **Drug Icons**: ChEMBL-style icons implemented (5 icons per drug)
✅ **Color Consistency**: Drug names match pill colors
✅ **Link Navigation**: All internal links working correctly
✅ **Print Layout**: Proper A4 page breaks configured
✅ **Section Borders**: Drug Details section has no outer border
✅ **Sources Placement**: Sources inside pill container with circular logos
✅ **Clinical Summary**: Positioned after table, before Drug mechanism
✅ **Font Consistency**: All patient details use same font styling

### Potential Considerations
- **Favicon Loading**: Source icons use `onerror` handler to hide if favicons fail to load
- **External Links**: Prescription pills link to ChEMBL website (external)
- **Page Breaks**: Test print output to ensure proper page separation
- **Icon States**: ChEMBL icons currently show same states for all drugs (may need customization per drug)

### Browser Compatibility
- **Tested**: Modern browsers (Chrome, Firefox, Safari, Edge)
- **Print**: Optimized for Chrome/Chromium-based browsers
- **SVG**: Logo uses inline SVG (compatible with all modern browsers)

---

## Best Practices

### Data Entry
- Always use consistent formatting for drug names
- Keep genotype notation standardized (`*5 / *5` format)
- Ensure all links have corresponding anchor IDs
- Verify tooltip text is accurate and helpful
- Use consistent color coding (green=normal, orange=dose-change, red=bad)

### Styling
- Maintain color consistency across status indicators
- Use semantic HTML structure
- Keep CSS organized by component
- Test print/PDF output regularly
- Ensure proper page breaks

### Accessibility
- Ensure sufficient color contrast
- Use descriptive link text
- Maintain logical reading order
- Test with screen readers
- Alt text for images/icons

### Performance
- Minimize inline styles
- Use CSS classes for repeated styles
- Optimize SVG logo size
- Consider lazy loading for large reports
- External favicons may have loading delays

---

## Troubleshooting

### Common Issues

**Links Not Working**:
- Verify anchor IDs match href values
- Check for typos in IDs
- Ensure sections exist in HTML
- Test internal navigation

**Colors Not Displaying**:
- Check CSS variable definitions
- Verify color values are valid hex codes
- Clear browser cache
- Check for CSS specificity issues

**Print Layout Issues**:
- Check `@media print` styles
- Verify page break settings (`page-break-after`)
- Test with different browsers
- Ensure A4 size is correct (210mm x 297mm)

**Tooltips Not Showing**:
- Verify `data-tooltip` attribute exists
- Check CSS `::after` pseudo-element
- Ensure z-index is high enough
- Test hover functionality

**Icons Not Loading**:
- Check favicon URLs are accessible
- Verify `onerror` handler is working
- Test with different network conditions
- Consider hosting icons locally if needed

**Page Breaks Not Working**:
- Verify `.page` class has `page-break-after: always`
- Check `@page` rule is set to A4
- Test print preview
- Ensure no conflicting CSS

---

## Version History

**Version 2.1** (Current)
- ✅ Clickable sources linking to ChEMBL compound pages
- ✅ Sources open in new tab (`target="_blank"`)
- ✅ Hover effects on source pills (background darkens)
- ✅ Each drug links to its specific ChEMBL compound page
- ✅ Updated documentation

**Version 2.0**
- ✅ Multi-page structure (4 pages)
- ✅ ChEMBL-style drug icons (5 icons)
- ✅ Sources in pill format with circular logos
- ✅ Clinical Summary section
- ✅ Enhanced Drug Details styling
- ✅ Page numbers
- ✅ Color-coded drug names
- ✅ Updated documentation

**Version 1.0**
- Initial template creation
- Basic sections implemented
- Print optimization included

---

## Support

For questions or issues:
- **Website**: medigenes.co.il
- **Email**: support@medygenes.com
- **Phone**: +1 (555) 321-9876
- **Address**: Yigal Alon 94, Tel Aviv

---

*Last Updated: December 2025*
