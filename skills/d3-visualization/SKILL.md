---
name: data-visualization
description: Design effective data visualizations: charts, graphs, dashboards, and infographics.
---

# Data Visualization

Create clear, accessible, and impactful data visualizations. This skill covers principles for designing charts, graphs, dashboards, and infographics that make data easy to understand and act on.

**What is Data Visualization?**
Data visualization is the practice of representing information visually—turning numbers, statistics, and data into charts, graphs, maps, and other visual formats that help people understand patterns, trends, and insights.

## When to Use Data Visualization

Create data visualizations when you need to:
- **Build dashboards** with charts and graphs
- **Create infographics** that tell a data story
- **Design analytics interfaces** for tracking metrics
- **Show relationships** between data points (network diagrams, correlation charts)
- **Display geographic data** (maps, choropleths)
- **Present trends over time** (line charts, area charts)
- **Compare values** (bar charts, column charts)
- **Show distributions** (histograms, box plots)

## Core Principles

### 1. Data-First Design
- Understand the data structure before designing
- Let the data inform the visualization type
- Consider data updates and transitions
- Ask: What story does this data tell?

### 2. Visual Encoding
Choose the right visual encoding for your data type:
- **Position**: Most accurate (x/y axes) - best for precise comparisons
- **Length**: Bar charts, comparisons - easy to compare
- **Angle**: Pie charts (use sparingly) - harder to compare accurately
- **Area**: Bubble charts - good for showing two dimensions
- **Color**: Categories, gradients for values - use for grouping or highlighting
- **Shape**: Different shapes for different categories

### 3. Accessibility
Make visualizations accessible to everyone:
- Don't rely solely on color to convey meaning
- Add labels and tooltips with data values
- Ensure keyboard navigation for interactive charts
- Provide text alternatives (tables, descriptions)
- Use sufficient color contrast (4.5:1 minimum)

## Chart Selection Guide

| What You Want to Show | Recommended Chart Type |
|----------------------|----------------------|
| **Comparison** | Bar chart, Column chart |
| **Trend over time** | Line chart, Area chart |
| **Part-to-whole** | Stacked bar, Pie chart, Treemap |
| **Distribution** | Histogram, Box plot, Violin plot |
| **Relationship** | Scatter plot, Bubble chart, Network diagram |
| **Geographic** | Map, Choropleth, Heat map |
| **Ranking** | Ordered bar chart, Lollipop chart |
| **Flow** | Sankey diagram, Flow chart |

## Choosing the Right Chart Type

**Start with your question**: What do you want to communicate?

- **"How much?"** → Bar chart, column chart
- **"Over time?"** → Line chart, area chart
- **"Parts of a whole?"** → Pie chart, stacked bar, treemap
- **"How are things related?"** → Scatter plot, bubble chart
- **"Where?"** → Map, choropleth
- **"How is data distributed?"** → Histogram, box plot

**Common Tools:**
- **D3.js**: Powerful JavaScript library for custom visualizations
- **Chart.js, Recharts, Victory**: Easier-to-use charting libraries
- **Tableau, Power BI**: Business intelligence tools
- **Figma, Illustrator**: For custom-designed infographics

## Implementation Pattern (D3.js Example)

```javascript
// Standard D3 pattern for custom visualizations
const svg = d3.select("#chart")
  .append("svg")
  .attr("viewBox", [0, 0, width, height]);

// Scales map data values to visual space
const x = d3.scaleLinear()
  .domain(d3.extent(data, d => d.value))
  .range([0, width]);

// Data binding: join data to DOM elements
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
- Use sequential palettes for continuous data (light to dark)
- Use diverging palettes for data with meaningful midpoint
- Use qualitative palettes for distinct categories
- Ensure colorblind-friendly palettes (avoid red/green combinations)

### Typography
- **Labels**: 12-14px for readability
- **Titles**: 16-18px to establish hierarchy
- Use tabular figures (monospaced numbers) for alignment
- Ensure contrast ratio ≥ 4.5:1 for accessibility
- Use sans-serif fonts for labels (e.g., Arial, Helvetica)

### Interactions
- **Hover states**: Show details on hover (tooltips, highlights)
- **Click to filter**: Allow users to drill down into data
- **Smooth transitions**: 300-500ms for data updates
- **Provide undo/reset**: Let users explore and return
- **Loading states**: Show progress for data fetching

### Responsive Design
- Use `viewBox` for SVG scaling
- Adjust tick counts at different breakpoints
- Consider mobile-specific layouts (stacked vs. side-by-side)
- Touch-friendly targets (44px minimum)
- Test on different screen sizes

## Data Visualization Best Practices

**Show the data clearly:**
- Remove unnecessary decoration (chart junk)
- Use consistent scales and axes
- Label axes and data points clearly
- Provide context (what does this mean?)
- Start axes at zero when appropriate (unless misleading)

**Make it accessible:**
- Use sufficient color contrast
- Don't rely on color alone to convey meaning
- Add text labels and descriptions
- Provide alternative text for charts
- Ensure keyboard navigation for interactive elements

**Help users explore:**
- Add interactive tooltips with details
- Allow filtering and drilling down
- Show related data on hover
- Provide clear legends and keys
- Enable data export when relevant

## Common Patterns

### Tooltips
Show additional information on hover:
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
Animate data updates smoothly:
```javascript
bars.transition()
  .duration(400)
  .attr("height", d => y(d.value));
```

### Responsive Charts
Make charts adapt to container size:
```javascript
const resize = () => {
  const width = container.clientWidth;
  svg.attr("width", width);
  x.range([0, width - margin.left - margin.right]);
  // Update elements
};
window.addEventListener("resize", resize);
```

## Design Checklist

Before finalizing your visualization:
- [ ] Chart type matches the question you're answering
- [ ] Axes are clearly labeled with units
- [ ] Colors are accessible (colorblind-friendly)
- [ ] Data is easy to read (not cluttered)
- [ ] Tooltips or labels show exact values
- [ ] Legend is clear and positioned appropriately
- [ ] Responsive on mobile devices
- [ ] Keyboard navigation works (for interactive charts)
- [ ] Context is provided (what does this mean?)
- [ ] Source of data is cited

## Common Mistakes to Avoid

**Don't:**
- Use pie charts for more than 5-6 categories
- Distort proportions with non-zero axes (when inappropriate)
- Use 3D effects (they distort perception)
- Overload charts with too much information
- Use low contrast colors
- Rely on color alone for critical information
- Forget to label axes or provide context

**Do:**
- Choose the simplest chart that answers the question
- Start axes at zero when comparing absolute values
- Use clear, descriptive titles
- Provide data tables for accessibility
- Test with actual users
- Iterate based on feedback
