---
name: naive-ui
description: Use when working with naive-ui components, or troubleshooting naive-ui usage issues.
license: MIT
metadata:
  author: Sepush
  version: "2026.5.13"
---

# Naive UI Practices

Usage guide for Naive UI and Vue 3 applications. Full coverage of all naive-ui components, prioritized by impact to guide automated refactoring, component creation, and troubleshooting.

## When to Apply

Reference these guidelines when:
- Writing new Vue 3 components using Naive UI
- Implementing forms and data validation
- Handling large datasets with virtual scrolling (DataTable, Tree, Select)
- Customizing application themes and dark mode
- Troubleshooting Naive UI usage issues and styling conflicts

## Rule Categories by Priority

| Priority | Category | Impact | Prefix |
|----------|----------|--------|--------|
| 1 | Core Configuration | CRITICAL | `core-` |
| 2 | Form & Data Input | CRITICAL | `component-` |
| 3 | Complex Data Display | HIGH | `component-` |
| 4 | Feedback & Overlay | HIGH | `component-` |
| 5 | Layout & Navigation | MEDIUM | `component-` |
| 6 | Basic Data Display | MEDIUM | `component-` |
| 7 | Advanced Customization | LOW-MEDIUM | `core-` |
| 8 | Ecosystem & Troubleshooting | LOW | `core-` |

## Quick Reference

### 1. Core Configuration (CRITICAL)

- `core-setup` - Auto-import setup, global config, providers
- `core-theme` - Theme overrides, dark mode, CSS variables, useThemeVars
- `core-import-on-demand` - Import on demand and tree shaking
- `core-nuxtjs` - Nuxt.js integration best practices
- `core-ssr` - Server-Side Rendering guidelines
- `core-style-conflict` - Potential style conflict resolution

### 2. Form & Data Input (CRITICAL)

- `component-form-validation` - Validation rules, dynamic forms, array fields
- `component-form` - Layout, validation, dynamic fields, nested forms
- `component-input` - Formatted input, precision, validation triggers
- `component-select` - Filterable, multiple, tags, async search, custom render
- `component-datepicker` - Date ranges, shortcuts, formatting, timezone
- `component-upload` - Custom request, file handling, drag drop
- `component-auto-complete` - Search/autocomplete with suggestions
- `component-cascader` - Multi-level hierarchical selection
- `component-dynamic-input` - Add/remove list items dynamically
- `component-dynamic-tags` - Editable tag list
- `component-input-otp` - One-time password input (since 2.41.1)
- `component-mention` - @mention with suggestion panel
- `component-time-picker` - Time selection panel
- `component-transfer` - Dual-list item transfer
- `component-tree-select` - Tree-structured dropdown selection

### 3. Complex Data Display (HIGH)

- `component-datatable` - Virtual scroll, remote data, sorting, filtering, fixed columns
- `component-tree` - Async loading, checkable, controlled state, large dataset handling
- `component-virtual-list` - Virtual scrolling patterns
- `component-table` - Simple styled HTML table (use DataTable for complex needs)
- `component-heatmap` - GitHub-style activity calendar heatmap (since 2.43.0)
- `component-infinite-scroll` - Scroll-triggered data loading (since 2.38.2)
- `component-highlight` - Search result text highlighting (since 2.40.0)
- `component-qr-code` - QR code generator (since 2.36.0)
- `component-thing` - Rich list item layout (avatar, title, description, actions)

### 4. Feedback & Overlay (HIGH)

- `component-modal` - Form modals, draggable, focus management, async close
- `component-feedback` - Programmatic API, global methods (Message, Notification, Dialog)
- `component-feedback-alert` - Alert, Skeleton, Spin, LoadingBar, Popconfirm
- `component-drawer` - Slide-in side panel
- `component-popover` - Anchored pop-up panel (style it yourself)
- `component-tooltip` - Simple hover text hint
- `component-popselect` - Select options in a popover
- `component-marquee` - Horizontally scrolling content (since 2.40.2)

### 5. Layout & Navigation (MEDIUM)

- `component-layout` - Layout, Grid, Flex, Space, Card, Divider
- `component-menu` - Menu, Dropdown, Breadcrumb, Tabs
- `component-navigation-steps` - Steps, Timeline, Pagination, Anchor, BackTop
- `component-split` - Resizable split-pane layout (since 2.36.0)
- `component-affix` - Sticky positioning on scroll
- `component-collapse-transition` - Animated height show/hide
- `component-scrollbar` - Custom-styled scrollbar container

### 6. Basic Data Display & General (MEDIUM)

- `component-data-display` - Image, List, Descriptions, Calendar, Time, Countdown, Code, Log, Equation, Number Animation
- `component-display` - Badge, Tag, Avatar, Progress, Statistic, Result, Empty
- `component-button` - Button variants, loading, icons
- `component-selection` - Radio, Checkbox, Switch, Slider, Rate, ColorPicker
- `component-carousel` - Slideshow/image carousel
- `component-collapse` - Accordion-style collapsible panels
- `component-ellipsis` - Text truncation with tooltip
- `component-gradient-text` - Gradient-colored text
- `component-icon` - Icon rendering with xicons
- `component-page-header` - Page header with back button and actions
- `component-typography` - Styled text components (h1-h6, p, text, list, blockquote)
- `component-watermark` - Text/image watermark overlay
- `component-float-button` - Floating action button (since 2.38.0)

### 7. Advanced Customization (LOW-MEDIUM)

- `core-customize-theme` - Customizing theme extensively
- `core-fonts` - Configuring fonts
- `core-i18n` - Internationalization
- `core-controlled-uncontrolled` - Controlled manner & uncontrolled manner

### 8. Global Utilities & Troubleshooting (LOW)

- `core-troubleshooting` - Common issues and quick fixes
- `core-installation` - Installation guidelines
- `core-jsx` - JSX & TSX usage
- `core-umd` - Using UMD build
- `core-usage-sfc` - Usage in SFC
- `core-vite-ssge` - Vite SSG/SSE integration
- `core-vitepress` - Vitepress integration
- `core-experimental-features` - Experimental features
- `core-discrete` - createDiscreteApi — use Message/Dialog/etc. outside setup
- `core-config-provider` - n-config-provider: global theme, locale, component defaults
- `component-element` - n-element: expose theme CSS vars on DOM
- `component-global-style` - n-global-style: sync theme to document.body

## How to Use

Read individual rule files for detailed explanations and code examples:

```
references/core-setup.md
references/component-datatable.md
```

Each rule file contains:
- Specific implementation details
- Code examples for Vue 3 setup script
- Warning notes and prerequisites
- Relevant TypeScript interfaces

## Full Compiled Document

For the complete guide with all rules expanded: `AGENTS.md`
