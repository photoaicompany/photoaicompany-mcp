# photoaicompany MCP Server

<img src="assets/logo.png" alt="photoaicompany" width="256">

**Design tools, photo editing and brand kits for agents and developers — a free online design app as an MCP server.**

- **Live MCP endpoint:** `https://mcp.photoai.company/mcp` (Streamable HTTP, stateless)
- **Official MCP Registry:** `com.photoai.company/photoaicompany` (domain-authenticated, pending DNS proof at publish time)
- **Website:** https://photoai.company/ · **Support:** support@photoai.company
- **Privacy:** https://photoai.company/privacy/ · **Terms:** https://photoai.company/terms/

Note: unlike a read-only catalog server, this server **mutates designs** — it creates, edits, reorders and deletes designs, pages, layers and elements, and can revoke read-only keys. Clients should confirm destructive actions with the user before calling them.

## Tools (43)

| Tool | Title | What it does |
|---|---|---|
| `create_design` | Create Design | Create a new editable design document from a size preset (Instagram post/story, YouTube thumbnail, Facebook post, X post, presentation slide, A4, US Letter) or custom width/height in pixels. |
| `get_design` | Get Design | Fetch a design's metadata: canvas size, background, element count, and a summary of every element on the canvas. |
| `list_designs` | List Designs | List the user's designs, newest first, with pagination. |
| `duplicate_design` | Duplicate Design | Duplicate an existing design into a new, fully editable copy (deep copy of all elements). |
| `resize_design` | Resize Design | Resize a design's canvas to another preset or custom size. |
| `add_text` | Add Text | Add a text element to the canvas with font, size, color, alignment, and bold/italic styling. |
| `list_fonts` | List Fonts | List the fonts available in the photoaicompany editor, grouped by category (serif, sans, display, script, mono). |
| `apply_text_style` | Apply Text Style | Apply a text style preset (heading, subheading, body, caption, quote) to a text element — sets size, weight, alignment, and line height in one step. |
| `suggest_font_pairing` | Suggest Font Pairing | Suggest a heading + body font pairing for a mood or purpose (e. |
| `search_stock_media` | Search Stock Media | Search Pexels for stock photos and videos by keyword. |
| `add_image` | Add Image | Add an image element to the canvas from a public image URL or an uploaded asset ID. |
| `upload_asset` | Upload Asset | Upload a user asset (image or video) into the asset library. |
| `list_assets` | List Assets | List uploaded assets in the asset library, optionally filtered by kind. |
| `remove_background` | Remove Background | Remove the background from an image. |
| `add_shape` | Add Shape | Add a shape element: rectangle, circle, triangle, line, star, or polygon, with fill and stroke styling. |
| `list_layers` | List Layers | List all layers/elements on the canvas in z-order (bottom to top). |
| `reorder_layer` | Reorder Layer | Move a layer forward, backward, to the front, or to the back of the z-order stack. |
| `list_pages` | List Pages | List the pages of a design. |
| `add_page` | Add Page | Add a blank page (same size) after the last page, or at a position, and make it the active page. |
| `set_active_page` | Set Active Page | Choose which page the element tools (add_text, add_shape, update_element and the rest) act on. |
| `duplicate_page` | Duplicate Page | Copy a page (with new element IDs) and place the copy right after it. |
| `merge_designs` | Merge Designs | Append all pages of one or more source designs to a target design (deep copies with new IDs). |
| `import_design` | Import Design | Create a new design from JSON: a name, a canvas size (preset or width/height) and pages of elements (text, shape, image, qr), in the same shape get_design and list_layers report. |
| `create_read_key` | Create Read-Only Key | Create a read-only access key for a design. |
| `revoke_read_keys` | Revoke Read-Only Keys | Revoke every read-only key for a design. |
| `reorder_page` | Reorder Page | Move a page to a new 1-based position. |
| `delete_page` | Delete Page | Delete a page and its elements. |
| `update_element` | Update Element | Change properties of an existing element (position, size, rotation, opacity, flip, text, font, color, fill, stroke, corner radius, image crop). |
| `delete_element` | Delete Element | Remove an element from the design. |
| `undo_last_change` | Undo Last Change | Revert the design to the state before its most recent change. |
| `align_elements` | Align Elements | Align or evenly distribute selected elements: left, center, right, top, middle, bottom of their combined bounding box, or distribute horizontally/vertically (even spacing needs 3+ elements). |
| `group_elements` | Group Elements | Group selected elements into one group, or ungroup an existing group back into individual elements. |
| `apply_color_palette` | Apply Color Palette | Apply a color palette to a design: cycles the palette across text colors and shape fills. |
| `suggest_color_palette` | Suggest Color Palette | Suggest a color palette for a mood or purpose. |
| `apply_photo_filter` | Apply Photo Filter | Apply a photo filter preset (vivid, warm, cool, mono, faded, noir, or none) to an image element. |
| `adjust_image` | Adjust Image | Adjust brightness, contrast, saturation, and warmth on an image element. |
| `create_brand_kit` | Create Brand Kit | Create a brand kit with a name, brand colors, brand fonts, and logo asset IDs. |
| `get_brand_kit` | Get Brand Kit | Fetch a brand kit's contents: colors, fonts, and logo assets. |
| `apply_brand_kit` | Apply Brand Kit | Apply a brand kit to a design: brand colors cycle across text and shape fills, brand fonts apply to text elements. |
| `list_templates` | List Templates | Browse the photoaicompany starter template catalog, optionally filtered by category (social, marketing, document, presentation). |
| `apply_template` | Apply Template | Start a new, fully editable design from a template. |
| `export_design` | Export Design | Export a design as PNG, JPG, PDF, or SVG. |
| `generate_design` | Generate Design | Generate real design artwork from a text prompt with FLUX. |

## Connect

### Claude Code
```bash
claude mcp add --transport http photoaicompany https://mcp.photoai.company/mcp
```

### Claude Desktop / Cursor / Windsurf (`mcp.json`)
```json
{
  "mcpServers": {
    "photoaicompany": {
      "url": "https://mcp.photoai.company/mcp"
    }
  }
}
```

### VS Code (`mcp.json`)
```json
{
  "servers": {
    "photoaicompany": {
      "type": "http",
      "url": "https://mcp.photoai.company/mcp"
    }
  }
}
```

No environment variables or API keys are required for the public endpoint; design state is per-session unless the server is configured otherwise.

## Registry metadata
`server.json` in this repo is the file intended for the Official MCP Registry as `com.photoai.company/photoaicompany` v0.1.0 (domain-authenticated via DNS proof at photoai.company).

## License
MIT — see [LICENSE](LICENSE). This repository contains listing, documentation and install configuration for the hosted photoaicompany MCP server; the server itself is operated at mcp.photoai.company.
