## [4.0.30] - 15-Nov-2026 01:08 AM
- Maintenance update and stability enhancements.

## [4.0.29] - 15-Nov-2026 12:36 AM
- Maintenance update and stability enhancements.

## [4.0.28] - 15-Nov-2026 12:29 AM
- Maintenance update and stability enhancements.

## [4.0.27] - 14-Nov-2026 11:55 PM
- Maintenance update and stability enhancements.

## [4.0.26] - 14-Nov-2026 11:21 PM
- Maintenance update and stability enhancements.

## [4.0.25] - 14-Nov-2026 10:39 PM
- Maintenance update and stability enhancements.

## [4.0.24] - 14-Nov-2026 06:33 PM
- Maintenance update and stability enhancements.

## [4.0.23] - 14-Nov-2026 06:14 PM
- Maintenance update and stability enhancements.

## [4.0.22] - 14-Nov-2026 05:20 PM
- Maintenance update and stability enhancements.

## [4.0.21] - 14-Nov-2026 05:19 PM
- Maintenance update and stability enhancements.

## [4.0.20] - 14-Nov-2026 03:36 PM
- User History Select-User Prompt & Auto-Load: User Activity History now opens cleanly on "-- Select User --" instead of loading mixed "ALL" records automatically; KPI metrics reset to "-" and a clean onboarding prompt appears until a user account is chosen, then systems and timeline load immediately upon selection.
- User History Executive UI & Zero-Clip Grids: Redesigned header, KPI cards with circular vector glyphs, filter bar, and Systems Logged Into / Activity Timeline grids in a crisp Slate-Teal palette with tuned column widths and horizontal-scroll fallback so dates, modules, actions, PCs, and IP addresses never clip across 1.0x and 1.25x DPI scaling.
- Employee Monitor Telemetry Refresh: Harmonized header, KPI cards, and action toolbar with User History; calibrated all 10 telemetry columns (Station / PC, IP Address, MAC Address, Active / Last User, Internet, VNC Host, Ver, Last Seen) to eliminate "..." truncation at 1.0x and 1.25x scaling, and aligned User History shortcut scope when no station is selected.
- Employee & Staff Master Overhaul: Replaced oversized cartoon navigation tiles with a compact 156px navigation rail featuring rounded vector-badged pills; upgraded section and summary containers to responsive rounded cards (fitting 1260px+ windows cleanly without right-border clipping or FixedSingle chrome); compacted signature upload; fixed "&" mnemonic underline glitches across User Management and My User Profile; and unified all 6 administration grids with unclipped headers ("Assigned Users", etc.) and responsive layout support.

## [4.0.19] - 14-Nov-2026 03:25 PM
- User History Select-User Prompt & Auto-Load: User Activity History now opens cleanly on "-- Select User --" instead of loading mixed "ALL" records automatically; KPI metrics reset to "-" and a clean onboarding prompt appears until a user account is chosen, then systems and timeline load immediately upon selection.
- User History Executive UI & Zero-Clip Grids: Redesigned header, KPI cards with circular vector glyphs, filter bar, and Systems Logged Into / Activity Timeline grids in a crisp Slate-Teal palette with tuned column widths and horizontal-scroll fallback so dates, modules, actions, PCs, and IP addresses never clip across 1.0x and 1.25x DPI scaling.
- Employee Monitor Telemetry Refresh: Harmonized header, KPI cards, and action toolbar with User History; calibrated all 10 telemetry columns (Station / PC, IP Address, MAC Address, Active / Last User, Internet, VNC Host, Ver, Last Seen) to eliminate "..." truncation at 1.0x and 1.25x scaling, and aligned User History shortcut scope when no station is selected.
- Employee & Staff Master Overhaul: Replaced oversized cartoon navigation tiles with a compact 156px navigation rail featuring rounded vector-badged pills; upgraded section and summary containers to clean rounded cards without harsh FixedSingle borders; compacted signature upload; fixed "&" mnemonic underline glitches across User Management and My User Profile; and unified all 6 administration grids with unclipped headers ("Assigned Users", etc.) and responsive layout support.

## [4.0.18] - 14-Nov-2026 02:51 PM
- Fixed VNC Disconnect -> Reconnect Hang: Hardened StarVncServer, StarVNC.exe, and VncRfbClient TCP socket teardown (SO_LINGER, Immediate Shutdown, fast IPv4 connect without DNS stall, tighter handshake timeouts, AbortConnect cancellation, and generation-guarded VncViewerForm reconnect + HandleCreated auto-connect) so reconnecting after Disconnect is instant and reliable.
- Compact Responsive VNC Toolbar: Rebalanced VncViewerForm toolbar button widths, spacing, and vertical alignment so PCs picker, Host/Port, Connect, View Only, Fit, Sync, Keys, PNG, and Disconnect fit cleanly without right-edge clipping on standard and compact tabs.
- Renamed "Team Chat" to "Chat": Unified naming across the bottom-right launcher pill ("Chat"), Employee Monitor shortcut button ("Chat"), and popup header/window title ("Chat").
- Fixed Chat Popup Anchoring & Window Layering: Anchored the popup directly above the bottom-right "Chat" button inside WorkingArea across 1.0x/1.25x/1.4x DPI scaling and window resizes; switched to MainForm-owned non-TopMost popup so it never hides off the side or slips behind MainForm while external OS apps can rise above it normally.
- Standardized Executive UI Redesign for Chat: Upgraded the "Chat" button and InternalChatPopupForm with Slate-to-Teal gradient header, vector Chat emblem, circular glass controls, segmented [Messages | Users] toggle, clipped horizontal quick-staff pills with < / > navigation, clean message bubbles, circular avatar directory, and Alert / Urgent red broadcast controls.

## [4.0.17] - 14-Nov-2026 01:24 PM
- Fixed Server Crash on Tab Close (Employee Monitor): Prevented System.InvalidOperationException ("No row can be added to a DataGridView control that does not have columns") by stopping and disposing _refreshTimer cleanly inside Dispose(bool) when MainForm.CloseTab closes an open tab without calling Close(), and guarded RefreshNodesNow/BindGrid against disposed controls (also hardened KeyGenForm auto-refresh timer).
- Automatic PostgreSQL Database Schema Migration on Startup & Update: Added DatabaseMigrationService integrated into DbHelper, AuthService, and UpdateService so any new tables, missing columns, indexes, and policies (including db_schema_version tracking, internal_chat_read_state, internal_chat_messages.sender_ip, audit_logs telemetry columns, and licensed_client_nodes VNC/Internet columns) upgrade automatically on Server & Client without manual SQL scripts.
- Integrated VNC Capture, Diagnostics & Station Picker Fix: Resolved "Windows Desktop / UAC Secure Screen" false positives in StarVncServer and standalone StarVNC.exe with 3-tier Win32 GDI capture (CopyFromScreen CaptureBlt -> SourceCopy -> GetDC/CreateDC("DISPLAY") + BitBlt), real OpenInputDesktop desktop detection, Per-Monitor DPI awareness, identical-frame deduplication, deduplicated viewer target titles, and a new "PCs" dropdown switcher in VncViewerForm.
- Floating Team Chat & Bottom-Right Widget Redesign: Moved the Team Chat pill inside pnlWorkArea clear of both the bottom-right live clock and open tab footers with crisp vector icon + red unread badge; shrunk popup width cleanly to 400x540 anchored at bottom-right (skipping center-screen repositioning), changed to unowned non-always-on-top window with Minimize (-) toggle, preserved red Emergency Alerts, and redesigned compact [Messages | Users] tabs with horizontal quick-switch staff chips and searchable directory.
- Executive UI Modernization & Alignment Polish: Upgraded EmployeeMonitorForm, UserHistoryForm, VncViewerForm, and InternalChatPopupForm with gradient headers, rounded KPI cards, dynamic DisplayRectangle clipped tab controls (eliminating DataGridView header clipping across 1.0x/1.25x/1.4x DPI), custom rounded status/action pills, and cue-banner hints.

## [4.0.16] - 14-Nov-2026 12:32 PM
- Employee Workstation & VNC Monitor (Privilege #414): Added Settings -> Employee Monitor dashboard displaying Online & Offline Server/Client PCs with Seat, Role, System Name, IP Address, MAC Address, Internet status, Active User/Role, VNC Status (:5900), manual IP:Port connect, Team Chat shortcut, and User History jump.
- Integrated Managed RFB 3.8 VNC Viewer & Host Engine (Privilege #415): Added embedded VncViewerForm tab and standalone tray StarVNC.exe agent (Server: HOST+VIEWER / Client: HOST agent) with DES challenge encryption, cluster-auto-derived auth key, external TightVNC fallback, Fit/1:1 scaling, View-Only toggle, special keys menu, and PNG snapshot export.
- Universal Installer VNC & Firewall Packaging: Updated StarSoft_Setup wizard & Payload.zip to bundle StarVNC\StarVNC.exe, generate StarVNC.ini per Server/Client role, open firewall port 5900, and register StarVNC in Windows Startup.
- Staff Activity & Multi-System Login History (Privilege #416): Added dedicated User History dashboard showing every PC a staff member logged into plus full chronological billing, settlement, purchase, user admin, policy, VNC session, and chat audit history with CSV export.
- Internal WhatsApp-Style Team Chat & Emergency Alerts (Policy POL_INTERNAL_CHAT): Added policy-controlled floating bottom-right Team Chat launcher & popup with Online/Offline user presence, Team Group broadcast, 1-on-1 messaging, unread badges, and real-time Emergency Alert broadcasts.
- Software Registration Auto-Resolution Overlap Fix: Replaced obfuscation-fragile reflection with compile-safe IResponsiveForm interface scaling and font-measured vertical positioning so badge, enterprise card, and manual links never overlap or clip at 1.25x/1.4x DPI.

## [4.0.15] - 14-Nov-2026 11:39 AM
- Check for Update UI Center Alignment & DPI Fix: Centered all update status panels, cards, version badge, and download link cleanly across all display resolutions and fixed `&` mnemonic rendering in `"Click here to download & install update now"`.
- Software Registration Modern Redesign: Upgraded UI to match Update Center's deep indigo gradient header, warm gold version badge, centered hardware pill badge, elevated license card, royal indigo CTA buttons, and vector halo icons under the unified "Software Registration" title.
- Billing Screen Header Shortcuts: Added quick-access icon+text "Recent Bills" & "Settlements" shortcut pills next to Dealer/Super Dealer on the Billing top bar (governed by Privilege #104), adapting cleanly for compact viewports.
- Ribbon Hover Alignment Fix: Prevented "POS Kiosk [Ctrl+Shift+K]" and other ribbon buttons from zooming or wrapping out of bounds on mouse hover at 1.0x and scaled DPIs.

## [4.0.14] - 14-Nov-2026 11:00 AM
- Added Policy-controlled Customer Address field (POL_SHOW_CUSTOMER_ADDRESS) across Billing and Kiosk screens
- Added Mobile number Enter-key auto-lookup in Billing to auto-fill Customer Name, Address & GSTIN and jump cursor straight to Item Search
- Enabled clean multi-line Customer Address persistence and printing on both A4/A5 Laser Invoices and POS Thermal Receipts (POL_PRINT_ADDRESS)
- Added dedicated Cust. Address tab in Bill Print Layout Studio with Customer Name+Address height adjustment and automatic cascading shift-down of all downstream bill sections

## [4.0.13] - 14-Nov-2026 10:31 AM
- Redesigned Bill Print Confirm Dialog into an ultra-compact 2-icon (A4 & POS) selector with full High-DPI and Display Resolution scaling support (zero clipping)
- Added mutually-exclusive Default Bill Print Policies (Default Bill Print: POS Thermal Roll & Default Bill Print: A4 / Normal Sheet) so whichever Policy is enabled automatically becomes default

## [4.0.12] - 14-Nov-2026 10:15 AM
- Fixed GitHub Cloud Auto-Updater fast-check & fallback binary download URL (Release_Build/StarSoft.exe + GitHub API fallback)
- Enforced Obfuscar assembly & string encryption on every Release executable and installer payload (removed debug PDB shipping)
- Redesigned Bill Print Selection dialog into a compact, sleek card-based prompt
- Restored Privilege #405 Settings > Policies & Configurations menu & shield icon for authorized admins without cross-page banner popups

## [4.0.11] - 13-Nov-2026 05:01 PM
- Maintenance update and stability enhancements.

## [4.0.10] - 11-Nov-2026 05:03 PM
- Maintenance update and stability enhancements.

## [4.0.9] - 11-Nov-2026 04:45 PM
- Maintenance update and stability enhancements.

## [4.0.8] - 11-Nov-2026 04:43 PM
- Maintenance update and stability enhancements.

## [4.0.7] - 11-Nov-2026 04:38 PM
- Maintenance update and stability enhancements.

## [4.0.6] - 11-Nov-2026 04:37 PM
- Maintenance update and stability enhancements.

## [4.0.5] - 11-Nov-2026 04:11 PM
- Maintenance update and stability enhancements.

## [4.0.4] - 11-Nov-2026 04:08 PM
- Maintenance update and stability enhancements.

## [4.0.3] - 11-Nov-2026 03:40 PM
- Maintenance update and stability enhancements.

## [4.0.2] - 11-Nov-2026 03:10 PM
- Maintenance update and stability enhancements.

## [4.0.1] - 11-Nov-2026 03:06 PM
- Maintenance update and stability enhancements.

## [4.0.0] - 11-Nov-2026 03:06 PM
- Maintenance update and stability enhancements.

## [3.0.99] - 11-Nov-2026 03:05 PM
- Maintenance update and stability enhancements.

## [3.0.98] - 11-Nov-2026 01:32 PM
- Maintenance update and stability enhancements.

## [3.0.97] - 11-Nov-2026 01:30 PM
- Maintenance update and stability enhancements.

## [3.0.96] - 11-Nov-2026 12:58 PM
- Maintenance update and stability enhancements.

## [3.0.95] - 11-Nov-2026 12:57 PM
- Maintenance update and stability enhancements.

## [3.0.94] - 11-Nov-2026 12:57 PM
- Maintenance update and stability enhancements.

## [3.0.93] - 11-Nov-2026 12:52 PM
- Maintenance update and stability enhancements.

## [3.0.92] - 11-Nov-2026 12:51 PM
- Maintenance update and stability enhancements.

## [3.0.91] - 11-Nov-2026 12:51 PM
- Maintenance update and stability enhancements.

## [3.0.90] - 11-Nov-2026 12:50 PM
- Maintenance update and stability enhancements.

## [3.0.89] - 11-Nov-2026 12:50 PM
- Maintenance update and stability enhancements.

## [3.0.88] - 11-Nov-2026 11:34 AM
- Maintenance update and stability enhancements.

## [3.0.87] - 11-Nov-2026 10:13 AM
- Maintenance update and stability enhancements.

## [3.0.86] - 11-Nov-2026 10:10 AM
- Maintenance update and stability enhancements.

## [3.0.85] - 11-Nov-2026 10:09 AM
- Maintenance update and stability enhancements.

## [3.0.84] - 11-Nov-2026 10:06 AM
- Maintenance update and stability enhancements.

## [3.0.83] - 11-Nov-2026 10:02 AM
- Maintenance update and stability enhancements.

## [3.0.82] - 11-Nov-2026 10:00 AM
- Maintenance update and stability enhancements.

## [3.0.80] - 10-Nov-2026 03:20 PM
- Maintenance update and stability enhancements.

## [3.0.79] - 10-Nov-2026 03:15 PM
- Maintenance update and stability enhancements.

## [3.0.78] - 10-Nov-2026 03:14 PM
- Maintenance update and stability enhancements.

## [3.0.77] - 10-Nov-2026 02:26 PM
- Maintenance update and stability enhancements.

## [3.0.76] - 10-Nov-2026 02:20 PM
- Maintenance update and stability enhancements.

## [3.0.75] - 10-Nov-2026 02:19 PM
- Maintenance update and stability enhancements.

## [3.0.74] - 10-Nov-2026 02:19 PM
- Maintenance update and stability enhancements.

## [3.0.73] - 10-Nov-2026 12:36 PM
- Maintenance update and stability enhancements.

## [3.0.72] - 10-Nov-2026 12:05 PM
- Maintenance update and stability enhancements.

## [3.0.71] - 10-Nov-2026 11:51 AM
- Maintenance update and stability enhancements.

## [3.0.70] - 10-Nov-2026 11:50 AM
- Multi-Screen DPI Resolution & POS Kiosk Shortcut Alignment.
- 21 Unique Ribbon Vector Icons Across All Tabs.
- Modern 2026 UI for Customer, Supplier & User Profiles.
- Compact 50/50 Half-Half Shift Close & Blind Settlement Layout.
- Redesigned Update Center, Software Identification & Policies Screens.
- Overhauled Printer Settings & Page Setup for A4/Thermal POS Bills.

## [3.0.69] - 09-Nov-2026 05:11 PM
- Maintenance update and stability enhancements.

## [3.0.68] - 09-Nov-2026 05:05 PM
- Maintenance update and stability enhancements.

## [3.0.67] - 09-Nov-2026 05:05 PM
- Maintenance update and stability enhancements.

## [3.0.66] - 09-Nov-2026 05:05 PM
- Maintenance update and stability enhancements.

## [3.0.65] - 09-Nov-2026 04:34 PM
- Maintenance update and stability enhancements.

## [3.0.64] - 09-Nov-2026 04:33 PM
- Maintenance update and stability enhancements.

## [3.0.63] - 09-Nov-2026 04:29 PM
- Maintenance update and stability enhancements.

## [3.0.62] - 09-Nov-2026 04:29 PM
- Maintenance update and stability enhancements.

## [3.0.61] - 09-Nov-2026 04:14 PM
- Maintenance update and stability enhancements.

## [3.0.60] - 09-Nov-2026 04:08 PM
- Maintenance update and stability enhancements.

## [3.0.59] - 09-Nov-2026 04:04 PM
- Maintenance update and stability enhancements.

## [3.0.58] - 09-Nov-2026 04:03 PM
- Maintenance update and stability enhancements.

## [3.0.57] - 09-Nov-2026 03:43 PM
- Maintenance update and stability enhancements.

## [3.0.56] - 09-Nov-2026 03:45 PM
- **Indian Financial Year Bill Number Series (`POL_FY_INVOICE_SERIES`)**:
  - Automatically calculates the financial year period (April 1 to March 31).
  - Invoice numbering follows the standard format: `{CompanyPrefix}-{FYYear}-{0001}` (e.g. `STAR-2026-0001`).
  - Automatically resets sequence back to `0001` on April 1st of every year (e.g. `STAR-2027-0001` on 01-Apr-2027).
  - Backdating an invoice automatically adopts the correct financial year and its sequence.
  - Fully governed by enterprise policy `POL_FY_INVOICE_SERIES`.
- **Instant Auto-Update (No Confirmation Popups)**:
  - Eliminated the `MessageBoxButtons.YesNo` prompt in `SoftwareUpdateForm` and `SoftwareCareForm`.
  - Clicking update now starts the download immediately with real-time button progress indicators and restarts automatically when complete.
- **Mandatory POS Kiosk Policy (`POL_ENFORCE_KIOSK_ONLY`)**:
  - Added enterprise policy `POL_ENFORCE_KIOSK_ONLY` to restrict cash counter operators exclusively to dedicated Fullscreen Kiosk Mode.
  - Blocks opening windowed billing tabs with an advisory notification guiding operators to launch POS Kiosk Mode (`Ctrl + Shift + K`).
- **Item Number & Item Code Fast Billing Search**:
  - Cashiers can now type the exact Item ID / Item Number (e.g. `1`, `6`) or Item Code (e.g. `ITM001`), and it will immediately match and add that item directly to the cart.
  - Upgraded catalog search algorithm to prioritize exact Item Code and Item ID matches at rank 0.
- **Swapped Customer Bar Controls (Mobile First)**:
  - Swapped Customer Name and Mobile Number in `BillingForm`: Mobile Number is now FIRST, Customer Name is SECOND.
  - Optimized tab order: typing a 10-digit mobile number immediately auto-populates existing customer details.
- **Unified 36px Kiosk Header Bar & 100% Visible Backdate DatePicker**:
  - Resized header height to a sleek 36px single bar, eliminating double header waste and aligning Bill Summary flush with the top.
  - Anchored Backdate `DateTimePicker` with 134px width and generous margin, ensuring the date and drop-down arrow are 100% visible.

## [3.0.54] - 09-Nov-2026 03:19 PM
- Maintenance update and stability enhancements.

## [3.0.53] - 09-Nov-2026 03:18 PM
- **Unified Sleek Kiosk Header Bar**: Resized header height from double-stacked 70px down to a single 38px unified header bar. Merged Kiosk badges (`🔒 POS KIOSK`, Cashier Info, `Release Kiosk: [Ctrl + Shift + K]`, and `📷 Screenshot`) seamlessly into the top bar, allowing GST Billing and Bill Summary to sit flush at the very top without wasted vertical space.
- **Fixed Backdate Billing Date Picker Visibility**: Moved the backdate `DateTimePicker` comfortably to the left with an expanded 134px width and 35px right margin, ensuring the full date format (`09-Nov-2026`) and its calendar drop-down button/arrow are 100% visible and never clipped or hidden.
- **Enhanced Kiosk Vertical Breathing Room**: Provided 32px of additional vertical room to the Cart DataGridView and Summary Checkout panel, ensuring checkout buttons remain well above screen boundaries on all monitor resolutions.

## [3.0.51] - 09-Nov-2026 02:59 PM
- **In-Button Silent LAN Auto-Update on Login Screen**: Implemented background update check and inline button progress on app startup before user login, preventing annoying duplicate logins upon client updates. Preserves typed username across self-update restart.

## [3.0.50] - 09-Nov-2026 02:58 PM
- Maintenance update and stability enhancements.

## [3.0.49] - 09-Nov-2026 02:41 PM
- Maintenance update and stability enhancements.

## [3.0.48] - 09-Nov-2026 02:41 PM
- Maintenance update and stability enhancements.

## [3.0.47] - 09-Nov-2026 01:56 PM
- Maintenance update and stability enhancements.

## [3.0.46] - 09-Nov-2026 01:55 PM
- Maintenance update and stability enhancements.

## [3.0.45] - 09-Nov-2026 01:53 PM
- Maintenance update and stability enhancements.

## [3.0.44] - 09-Nov-2026 01:52 PM
- Maintenance update and stability enhancements.

## [3.0.43] - 09-Nov-2026 01:51 PM
- Maintenance update and stability enhancements.

## [3.0.42] - 09-Nov-2026 01:47 PM
- Maintenance update and stability enhancements.

## [3.0.41] - 09-Nov-2026 01:46 PM
- Maintenance update and stability enhancements.

## [3.0.40] - 09-Nov-2026 01:40 PM
- Maintenance update and stability enhancements.

## [3.0.39] - 09-Nov-2026 01:13 PM
- Maintenance update and stability enhancements.

## [3.0.38] - 09-Nov-2026 01:00 PM
- Maintenance update and stability enhancements.

## [3.0.37] - 09-Nov-2026 12:55 PM
- Maintenance update and stability enhancements.

## [3.0.36] - 09-Nov-2026 12:55 PM
- **Quantity Entry Modal Fix in Kiosk Mode**: Added native `DialogResult.OK` command routing and `FormClosing` validation to `PromptItemQuantity`, ensuring `✔ Add to Cart [Enter]` reliably dismisses the dialog and adds item to cart.
- **DWM Flicker Elimination**: Enforced `TopMost = true` on `KioskBillingForm` in `DisplayResolutionService` and set dialogs to `TopMost = true` so fullscreen Kiosk mode never fights with Windows Taskbar on clicks.
- **Left-Aligned Date Picker & Customer Fields**: Shifted customer textboxes and Backdate Date picker leftward by ~95px with safety right-margin clamping, ensuring the calendar dropdown arrow `[v]` is 100% visible across 1024x768 to 4K resolutions.

## [3.0.35] - 09-Nov-2026 12:19 PM
- Maintenance update and stability enhancements.

## [3.0.34] - 09-Nov-2026 12:18 PM
- Maintenance update and stability enhancements.

## [3.0.33] - 09-Nov-2026 11:54 AM
- Maintenance update and stability enhancements.

## [3.0.32] - 09-Nov-2026 11:34 AM
- Maintenance update and stability enhancements.

## [3.0.31] - 09-Nov-2026 11:34 AM
- Maintenance update and stability enhancements.

## [3.0.30] - 09-Nov-2026 11:03 AM
- Maintenance update and stability enhancements.
## [3.0.16] - 09-Nov-2026 09:29 AM
- **Dealer & Super Dealer Special Pricing System**:
  - Added dedicated **Dealer Rate (₹)** (`dealer_price`) and **Super Dealer Rate (₹)** (`super_dealer_price`) to PostgreSQL `items` schema with automated migration.
  - Added input fields in **Item Master (`ProductMasterForm` / `ItemMasterForm`)** with dedicated table columns in the left inventory grid, supporting edit, save, and auto-sync.
- **Enterprise Policy `POL_DEALER_PRICING`**:
  - Added **Allow Dealer & Super Dealer Special Pricing** policy under *Discounts & Pricing* category.
  - Billing POS dynamically respects this policy: when disabled, dealer checkboxes are hidden from billing operators.
- **Billing POS Customer Tier Checkboxes (`BillingForm`)**:
  - Added mutually-exclusive **Dealer** and **Super Dealer** tick boxes next to Customer Name in the customer header bar.
  - Checking Dealer applies the product's Dealer Rate; checking Super Dealer applies Super Dealer Rate; unchecking restores retail Selling Price.
  - Dynamically recalculates all existing cart items and assigns the tier rate to newly scanned barcodes or searched items.
- **Independent Security Privilege Numbers #106 & #107**:
  - `PrivilegeCodes.DealerBilling = 106`: **[106] Dealer Pricing & Invoicing Permission**.
  - `PrivilegeCodes.SuperDealerBilling = 107`: **[107] Super Dealer Pricing & Invoicing Permission**.
  - Cashiers attempting to tick Dealer or Super Dealer without respective privileges receive an access denied notice.
- **Invoice Print Layout Engine Overlap Fix (`PrintService`)**:
  - Increased base HSN column width from 54px to 58px, completely resolving "HSN/SAC" clipping into "HSN/SA".
  - Enforced strict GDI+ `SetClip` boundary containment on the Item Description column, preventing long text from ever bleeding horizontally into adjacent columns.

## [3.0.15] - 07-Nov-2026 04:47 PM
- Added dedicated **Purchase** module on the top Ribbon Bar (`Home | Billing | Purchase | Masters | Reports | Settings`) and inside `Masters`.
- **Step 1 - Purchase Order (PO) Generator**: Select or quick-create a Supplier/Vendor, add existing or brand-new items with Brand, HSN/SAC, Unit, Qty, Purchase Rate, MRP, Selling Rate, and GST %, save POs, and convert any PO into a Purchase Invoice in 1 click.
- **Step 2 - Purchase Invoice Entry (GRN / Supplier Bill Entry)**: Load all items directly from any Pending PO or enter a direct Purchase Invoice, with live editable grid columns for Qty, Purchase Rate, MRP, Selling Price, Brand, and HSN/SAC.
- **Automatic Product Master (`items`) & Stock Synchronization**: Saving a Purchase Invoice automatically creates any new product in Product Master with auto-generated Item Code, Barcode, Brand, HSN, MRP, Purchase Rate, Selling Price, and initial Stock, and automatically increments `current_stock` and updates rates for existing products.
- **Step 3 - Purchase & PO Register**: Added KPI summary cards (Total POs, Total Purchase Invoices, Total Purchase Value, Supplier Balance Payable) and automatic Supplier Ledger (`party_ledger`) synchronization.

## [3.0.14] - 07-Nov-2026 03:58 PM
- Fixed all visual glitches, screen tearing, disappearing tabs, and layout jumping when opening multiple tabs or switching tabs.
- Created high-performance `ModernChromeTabControl` with native WinForms double-buffering (`UserPaint | AllPaintingInWmPaint | OptimizedDoubleBuffer`), eliminating 100% of background erase flashing (`WM_ERASEBKGND`), blank grey screen tears, and disappearing tab headers.
- Fixed layout jumping across tabs by establishing rock-solid identical tab drawing geometry (`drawRect`) for active, hovered, and inactive states, ensuring tab headers and close buttons never jump vertically on click or hover.
- Removed freezing of ancestor work area (`WM_SETREDRAW = 0`) during tab selection and switching, which previously caused `SysTabControl32` child window visibility and Z-order updates to stall and left ghost pixels from closed tabs on screen.
- Maintained background tab sizing synchronization during window resize / maximization, so background tabs are already 100% sized to the display rectangle before being brought to front, eliminating responsive layout jumps on tab switch.
- Increased default tab item width to 215px so long titles like "Policies & Configurations", "Users & Privileges", and "Brand / Co. Master" fit cleanly without truncation ellipsis.
- Removed heavy recursive `ThemeService.ApplyToControlTree` from the per-tab selection loop, preventing DataGridView column header layout hitching and button restyling delays during tab switches.

## [3.0.13] - 07-Nov-2026 03:55 PM
- Maintenance update and stability enhancements.

## [3.0.12] - 07-Nov-2026 03:51 PM
- Maintenance update and stability enhancements.

## [3.0.11] - 07-Nov-2026 01:38 PM
- Maintenance update and stability enhancements.

## [3.0.10] - 07-Nov-2026 12:58 PM
- Maintenance update and stability enhancements.

## [3.0.9] - 07-Nov-2026 12:17 PM
- Maintenance update and stability enhancements.

## [3.0.8] - 07-Nov-2026 11:47 AM
- Maintenance update and stability enhancements.

## [3.0.7] - 07-Nov-2026 11:20 AM
- Maintenance update and stability enhancements.

## [3.0.6] - 07-Nov-2026 11:04 AM
- Maintenance update and stability enhancements.

## [3.0.5] - 07-Nov-2026 11:03 AM
- Maintenance update and stability enhancements.

## [3.0.4] - 07-Nov-2026 10:40 AM
- Maintenance update and stability enhancements.

## [3.0.3] - 07-Nov-2026 10:39 AM
- Maintenance update and stability enhancements.

## [3.0.2] - 07-Nov-2026 10:38 AM
- Maintenance update and stability enhancements.

## [3.0.1] - 06-Nov-2026 05:22 PM
- Maintenance update and stability enhancements.

# Star Soft Enterprise ERP - Official Version Catalog & Changelog

All notable changes to the Star Soft Enterprise POS, Billing & ERP system are documented in this file.
Format based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

---

## [3.0.0] - 06-Nov-2026 05:15 PM
### Major Milestone Release - Architecture & Packaging Overhaul

#### Client & Server Independent Distribution Packages
- **100% Isolated Client Package (`StarSoft_Client_Package`)**:
  - Configured specifically for USB Pen Drive distribution or network file transfer to client workstations.
  - Strictly zero admin tools (no KeyGen, no StarMasterTool, no source code, no dev scripts).
  - Includes client billing binary (`StarSoft.exe`), local backup daemon (`StarBackup`), wallpapers/icons (`Resources`), and local invoice storage (`Backup_All`).
  - Added `Configure_Server_IP.bat`: 1-click interactive utility that asks for the Master Server IP address, tests LAN ping connectivity, and updates `config.ini` automatically.
  - Added `HOW_TO_CONFIGURE_CLIENT_DATABASE.txt`: Bilingual step-by-step connection guide (Tamil & English).
  - Added `Fresh_Database_Seed_Data.sql`: Complete standalone seed data script (Administrator user, standard GST tax slabs, measurement units, system settings, and default print layouts).

- **Master Server Deployment Package (`StarSoft_Server_Package`)**:
  - Full Master Server setup suite with `1_Setup_Server_Database_And_Firewall.bat`.
  - Automated PostgreSQL database creation (`star_soft_db`), automated SQL schema execution, and automated Windows Firewall configuration for Port 5432.
  - High-speed SMB LAN network share deployer (`2_Setup_LAN_Network_Share.bat`).
  - Isolated server administrator licensing tools (`Server_Admin_Tools\KeyGen.exe` & `StarMasterTool.exe`).

#### Smart Two-Tier Server Update Engine (Online-First with Local Fallback)
- **Host Binary Verification**:
  - When checking online updates via GitHub, the engine now verifies both the manifest version number AND performs an HTTP HEAD verification to ensure the executable binary actually exists and is accessible on the remote host before announcing an update.
- **Interactive Local Fallback**:
  - If the server is offline or no online update exists on the remote host, the system prompts the administrator: *"Would you like to check locally for an update package (.exe / .zip)?"*
  - Dedicated *"Browse Local Update Package..."* selector allowing instant inspection, version validation, and database publication of local offline packages.
- **Master Server Client Sync**:
  - Client workstations automatically verify against the Master Server PostgreSQL database (`app_version_binaries`) upon launch and login. Clients download the binary stream directly from the database and restart automatically.

#### Real-Time StarBackup Monitoring & Control
- Replaced the passive minimize-only close behavior in `StarBackup` with dedicated **`🗕 Tray`** (Minimize to System Tray) and **`✕ Exit`** (Stop Application) buttons.
- Added confirmation dialog on window close: prompts the user whether to minimize to background tray (keeping backups active) or exit completely (stopping backups).
- Added tray context menu option: `🛑 Stop & Exit StarBackup`.
- Real-time sub-second cache invalidation in `BackupMonitorService`: when StarBackup is terminated, the home screen notification card flips instantly from **GREEN** (`✓ Database Backup: Protected`) to **RED** (`⚠️ StarBackup Software Inactive`) without any delay.
- Automatic PostgreSQL synchronization: the Master Server writes its backup status to `system_settings`, allowing all client workstations across the LAN to reflect real-time backup health without needing StarBackup to run on client PCs.

#### Modern Executive GST Bill Print Layout
- Fully responsive centered preview canvas with Slate Blueprint backdrop (`#E2E8F0`) and paper drop shadow, eliminating white space voids when maximized.
- High-density dual header status badges: Filled primary accent badge (`TAX INVOICE (B2C)`) and white pill outline badge (`ORIGINAL FOR RECIPIENT`).
- Right-aligned metadata with bold accent-colored invoice number (`#HS-1104`) and payment mode (`CASH`).
- Item Description with combined Item Code and Serial Number tag formatting (`#ITM001 • S/N: ...`).
- Side-by-side Bank Remittance details box and Dynamic UPI QR Code (GPay / PhonePe / Paytm).

#### Security & Authentication
- Integrated `DbConnectionFailedDialog` (Tune HIS style): Clean diagnostic interface with checklist (Port 5432, Server IP, Firewall) and Master Admin Password gate preventing unauthorized database credential edits on client PCs.

---

## [2.0.100] - 06-Nov-2026 03:00 PM
### Client-Server LAN Synchronization & Automated Backup Daemon

#### Features & Improvements
- **StarBackup Engine v1.0**:
  - Autonomous multi-drive backup daemon with primary, secondary, and tertiary path redundancy.
  - Automated retention policies (pruning archives older than 60 days).
  - Background system tray service with customizable scheduled execution times.
- **PostgreSQL Version Binary Publishing**:
  - Created `app_version_binaries` table in PostgreSQL to distribute client binaries directly over the database connection without needing shared network folders.
- **Company System Policies Engine**:
  - Added policy restriction framework for version rollback, negative stock invoicing, and credit limits.

---

## [2.0.0] - 01-Nov-2026 10:00 AM
### Enterprise Multi-User Architecture & Advanced GST Suite

#### Features & Improvements
- **Role-Based Access Control (RBAC)**:
  - Role management (Administrator, Branch Manager, Billing Operator, Auditor).
  - PBKDF2 with SHA-256 password hashing with unique salt generation.
- **Indian GST Compliance**:
  - Automatic split of CGST, SGST, and IGST based on customer and store two-digit State Codes.
  - HSN / SAC code master integration and GST tax slab management (0%, 5%, 12%, 18%, 28%).
- **Theme & Appearance Engine**:
  - Desktop wallpaper themes (Mountain Dusk, Oceanic Deep Blue, Emerald Executive, Royal Midnight).
  - Notification alert card styling with customizable opacity and text contrast.
- **Hardware Integration**:
  - Barcode and QR code generation for products and bills.
  - Support for USB barcode scanners and 3-inch / 2-inch thermal POS receipt printers.

---

## [1.0.0] - 15-Oct-2026 09:00 AM
### Initial Production Release - Core POS & Retail Foundation

#### Features & Improvements
- High-speed retail billing interface with keyboard shortcuts.
- Product master catalog with barcode, cost price, and selling price.
- Basic customer ledger and party payment tracking.
- Cash register day-end reconciliation and basic sales reports.
