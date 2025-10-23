# Custom Changes to Kendall Theme

This is a customized version of the [jsonresume-theme-kendall](https://www.npmjs.com/package/jsonresume-theme-kendall) theme with the following fixes:

## Changes Made

### 1. Fixed Missing Company Names in Work Experience

**Issue**: The original Kendall theme template used `{{name}}` instead of `{{company}}` for displaying company names in work experience entries. This resulted in empty company name fields in the generated HTML.

**Fix**: Updated `resume.template` line 55 to use `{{company}}` instead of `{{name}}` to properly display company names according to the JSONResume schema.

**File**: `resume.template`
**Line**: 55
**Before**: `{{name}}`
**After**: `{{company}}`

## Maintenance

This custom theme is based on `jsonresume-theme-kendall@0.2.0`. If you need to update to a newer version of the base theme:

1. Install the latest version: `npm install jsonresume-theme-kendall@latest`
2. Copy the updated theme: `cp -r node_modules/jsonresume-theme-kendall/* theme-kendall-fixed/`
3. Re-apply the fix above
4. Remove unnecessary files: `rm -rf theme-kendall-fixed/node_modules`
5. Test the output: `yarn html`
