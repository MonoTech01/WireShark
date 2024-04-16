# Customizing Your Profile

## Key Goals:

    Faster Analysis: See information quickly and efficiently
    Emphasize Key Data: Highlight what matters most

## Profile Setup:

    Name: Choose a clear, descriptive name (instead of just "Default")
    View:
        Time Display: Use "delta time" (time since the first packet) for quick comparisons

## Adding Columns:

    Go to: Edit → Preferences → Appearance → Column
    Click: "+" button to add a new column

## Display Packet Content as Column:

    Find Content: Locate the specific data within a packet
    Right-Click: Select "Apply as a column"

## Filtering and Coloring for SYN Packets

    Why Color SYN?: Helps identify botnets and track packet transmission
    Find SYN:
        Locate a SYN packet
        Look at the filter and copy it (usually "tcp.flags.syn==1")
    Add Filter:
        Paste the filter into the search bar
        Click "+" to save as a quick-access filter
        Optional: Edit the name for nested organization (e.g., "TCP // Syn")
    Coloring Rules:
        Go to: View → Coloring Rules

## Screen Layout:

    Customize: Edit → Preferences → Layout
