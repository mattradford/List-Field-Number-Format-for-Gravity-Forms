# List Field Number Format for Gravity Forms

[![License: GPL v2](https://img.shields.io/badge/License-GPL%20v2-blue.svg)](https://www.gnu.org/licenses/gpl-2.0)
[![WordPress](https://img.shields.io/badge/WordPress-5.0%2B-blue.svg)](https://wordpress.org/)
[![Gravity Forms](https://img.shields.io/badge/Gravity%20Forms-2.9%2B-orange.svg)](https://www.gravityforms.com/)

A Gravity Forms add-on plugin that transforms list field columns into powerful number fields with formatting, calculations, and validation.

## Features

- **Number Formatting**: Format list field columns as:
  - Decimal (dot separator: `1,234.56`)
  - Decimal (comma separator: `1.234,56`)
  - Currency with proper symbol placement

- **Column Calculations**: Automatically calculate values between columns using formulas with merge tags (e.g., `{1:2} + {1:3}`)

- **Range Validation**: Set minimum and maximum values for list field cells using formulas

- **Column Totals**: Automatically calculate and display totals for number columns

- **Rounding Options**: Control decimal places and rounding direction (up, down, or closest)

- **Entry Editor Support**: Works in both frontend forms and WordPress admin entry editor

## Installation

### Via WordPress Admin
1. Go to **Plugins → Add New → Upload Plugin**
2. Upload the plugin ZIP file
3. Activate the plugin

### Via SFTP
1. Upload the plugin folder to `/wp-content/plugins/`
2. Activate the plugin through the **Plugins** menu in WordPress

### Via Composer
```bash
composer config repositories.list-field-number-format vcs https://github.com/mattradford/List-Field-Number-Format-For-Gravity-Forms.git
composer require mattradford/list-field-number-format:dev-main
```

## Usage

1. **Create a form** with a List field in Gravity Forms
2. **Configure number formatting** in the plugin settings for each list column:
   - Select the number format type
   - Set rounding options
   - Add calculation formulas (optional)
   - Set range validation (optional)

### Formula Examples

| Example | Description |
|---------|-------------|
| `{1:2} + {1:3}` | Adds column 2 and column 3 from list field 1 |
| `{2:1} * 1.1` | Multiplies column 1 from list field 2 by 1.1 |
| `{1:5} - 10` | Subtracts 10 from column 5 in list field 1 |

### Field Merge Tags

- `{field_id:column_number}` - Reference a specific column in a list field
- `{field_id}` - Reference a standard field value

## Screenshots

*(Add screenshots of the plugin in action)*

## Frequently Asked Questions

### Does this work with the latest Gravity Forms?
Yes, the plugin is compatible with Gravity Forms 2.9 and later. It uses the modern `gform.utils.isNumber()` API with fallback to the deprecated `gformIsNumber()` for older versions.

### Can I use this with other Gravity Forms add-ons?
Yes, this plugin works alongside other Gravity Forms add-ons.

### Are calculations updated in real-time?
Yes, calculations update automatically as users enter values.

### Can I format numbers as currency?
Yes, select the "currency" format option and the plugin will use Gravity Forms' built-in currency formatting.

## Changelog

### 2.0.3 - 2026-08-16
- **Fixed**: Null reference error in `itsg_gf_list_number_format_newrow()` when field parent elements are not found
- **Fixed**: `getMatchGroups()` function now properly extracts regex matches from formula strings
- **Fixed**: Updated deprecated `gformIsNumber()` to use `gform.utils.isNumber()` with fallback support for GF 2.9+
- Version bump for bug fix release

### 2.0.2 - 2026-08-16
- **Fixed**: Added missing `getMatchGroups()` function that was causing "Uncaught ReferenceError: getMatchGroups is not defined"
- **Fixed**: Deprecated `gformIsNumber()` now uses `gform.utils.isNumber()` (GF 2.9+) with backward compatibility fallback
- Version bump for bug fix release

### 1.5.1 - 2025-12-13
- Previous version from original plugin

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This plugin is licensed under the GPL v2 or later.

## Credits

- Original plugin by [Adrian Gordon](http://www.itsupportguides.com/)
- Fork maintained by [Matt Radford](https://github.com/mattradford/)
- Fixes and improvements by [Mistral Vibe](https://mistral.ai/)
