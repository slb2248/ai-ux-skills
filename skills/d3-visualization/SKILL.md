---
name: d3-visualization
description: Create interactive data visualizations with D3.js
---

# D3.js Data Visualization

Create beautiful, interactive data visualizations using D3.js.

## When to Use
- Building dashboards with charts
- Creating infographics
- Network/relationship diagrams
- Geographic visualizations
- Animated data transitions

## Core Principles

### 1. Data-First Design
- Understand the data structure before designing
- Let the data inform the visualization type
- Consider data updates and transitions

### 2. Visual Encoding
- **Position**: Most accurate (x/y axes)
- **Length**: Bar charts, comparisons
- **Angle**: Pie charts (use sparingly)
- **Area**: Bubble charts
- **Color**: Categories, gradients for values

### 3. Accessibility
- Don't rely solely on color
- Add labels and tooltips
- Ensure keyboard navigation
- Provide text alternatives

## Chart Selection Guide

| Data Type | Recommended Chart |
|-----------|------------------|
| Comparison | Bar, Column |
| Trend over time | Line, Area |
| Part-to-whole | Stacked bar, Treemap |
| Distribution | Histogram, Box plot |
| Relationship | Scatter, Network |
| Geographic | Map, Choropleth |

## Implementation Pattern

```javascript
// Standard D3 pattern
const svg = d3.select("#chart")
  .append("svg")
  .attr("viewBox", [0, 0, width, height]);

// Scales
const x = d3.scaleLinear()
  .domain(d3.extent(data, d => d.value))
  .range([0, width]);

// Data binding
svg.selectAll("rect")
  .data(data)
  .join("rect")
  .attr("x", d => x(d.value))
  .attr("height", d => y(d.category));
```

## Design Guidelines

### Color Palettes
- Use colorbrewer2.org for accessible palettes
- Limit to 5-7 colors for categories
- Use sequential palettes for continuous data

### Typography
- 12-14px for labels
- 16-18px for titles
- Use tabular figures for numbers
- Ensure contrast ratio ≥ 4.5:1

### Interactions
- Hover states for details
- Click to filter/focus
- Smooth transitions (300-500ms)
- Provide undo/reset options

### Responsive Design
- Use viewBox for scaling
- Adjust tick counts at breakpoints
- Consider mobile-specific layouts
- Touch-friendly targets (44px min)

## Common Patterns

### Tooltips
```javascript
element.on("mouseenter", (event, d) => {
  tooltip
    .style("opacity", 1)
    .html(`Value: ${d.value}`)
    .style("left", event.pageX + "px")
    .style("top", event.pageY + "px");
});
```

### Transitions
```javascript
bars.transition()
  .duration(400)
  .attr("height", d => y(d.value));
```

### Responsive
```javascript
const resize = () => {
  const width = container.clientWidth;
  svg.attr("width", width);
  x.range([0, width - margin.left - margin.right]);
  // Update elements
};
window.addEventListener("resize", resize);
```
