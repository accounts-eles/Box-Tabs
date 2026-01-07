🗂️ Box Tabs Template

A premium, interactive "tile-reveal" interface built with Tailwind CSS. This component features a unique grid of clickable info-tiles that act as tabs, triggering a dedicated content area below. It is ideal for feature highlights, service descriptions, or interactive learning modules.

🚀 Live Demo

Explore the Box Tabs Component Here

✨ Project Overview

The Box Tabs Template is designed to encourage exploration through a tactile, card-based interface. It uses distinct visual feedback loops—such as vertical translation on hover and deep color shifts on selection—to guide the user through different informational topics.

Key Features

Tactile Tile Navigation: Interactive cards (.info-tile) that utilize transform and box-shadow transitions to create a "lift" effect when hovered.

Smart Icon States: SVG icons within the tiles automatically shift from brand-dark to white when a tile is hovered or active, ensuring high visibility.

Centralized Reveal Area: A dedicated content box (.reveal-content) with a strong visual left-border anchor that updates dynamically based on the selected tile.

Fluid Grid Layout: A responsive flexbox container that shifts from a 4-column desktop grid to a single-column list on mobile devices.

Smooth Opacity Transitions: Content reveals utilize CSS opacity transitions to avoid jarring text swaps, creating a more polished user experience.

🛠️ Technical Implementation

Styling Engine: Tailwind CSS for foundational utilities combined with custom CSS variables (:root) for the specific brand identity.

Typography: Utilizes the Inter font family for a clean, sans-serif academic or corporate look.

Content Mapping: Uses a JavaScript contentMap object to store and retrieve data associated with each tile's data-topic attribute.

Visual Design Tokens:

Primary Dark (#1f2a52): Active state background and heavy left border for content.

Accent Cyan (#00bec7): Hover states and container borders.

Tertiary Light (#d2f0f0): Inactive tile backgrounds.

Slate Grey (#abb5bf): Secondary "placeholder" or instructional text.

📂 Structure and Usage

The component is entirely self-contained within a single HTML file, featuring a centralized interaction controller.

Main Container: A centered, bordered card that holds the header and navigation.

Tile Container: A flexbox grid holding the clickable data-topic triggers.

Reveal Content: A dynamic area with an initial-message state that transitions to full content upon user interaction.

infoTiles.addEventListener('click', (event) => {
  const clickedTile = event.target.closest('.info-tile');
  if (clickedTile) {
    // 1. Reset states across all tiles
    document.querySelectorAll('.info-tile').forEach(tile => tile.classList.remove('active'));
    clickedTile.classList.add('active');

    // 2. Fetch content from the data map and update the display
    const topic = clickedTile.dataset.topic;
    revealedInfo.textContent = contentMap[topic];
    revealedInfo.classList.remove('initial-message');
    revealedInfo.classList.add('visible');
  }
});


📄 License

MIT License - Developed as part of the accounts-eles UI component library.
