You are a senior Frontend Engineer and UI/UX specialist with strong expertise in Next.js, React, TypeScript, responsive design, data visualization, and modern dashboard layouts.

Your task is to review the existing Next.js frontend codebase and make the entire application fully responsive without changing the existing business logic, API integrations, data flow, or core functionality.

The application includes:

* A collapsible sidebar
* Header and navigation components
* Dashboard pages
* Data tables
* Charts and graphs
* Diagrams and visualizations
* Cards and statistic widgets
* Forms, filters, search fields, and action buttons
* Modal dialogs, dropdowns, and tooltips

## Main Requirements

### 1. Preserve Existing Functionality

* Do not modify backend APIs, API calls, business logic, authentication logic, state management, or data models.
* Do not remove or break any existing functionality.
* Keep the current component structure where possible.
* Avoid unnecessary refactoring.
* Do not replace existing libraries unless there is a clear technical reason.
* Preserve the current design language, colors, typography, spacing, and visual identity.

### 2. Responsive Layout

Make the application work correctly on the following screen sizes:

* Mobile: 320px–767px
* Tablet: 768px–1023px
* Desktop: 1024px–1439px
* Large Desktop: 1440px and above

The layout must adapt smoothly between breakpoints and should not rely only on a few hard-coded device sizes.

Use responsive CSS techniques such as:

* CSS Grid
* Flexbox
* Responsive spacing
* Fluid widths
* `min-width`, `max-width`, and `clamp()`
* Appropriate media queries
* Responsive utility classes if the project uses Tailwind CSS

Avoid fixed widths and fixed heights unless they are required.

### 3. Sidebar Behavior

Review and improve the sidebar behavior for different screen sizes:

#### Desktop

* Keep the sidebar visible by default.
* Preserve the existing collapse and expand functionality.
* Ensure the main content automatically adjusts when the sidebar is expanded or collapsed.
* Prevent the sidebar from overlapping the main content.

#### Tablet

* Use a compact or collapsed sidebar when appropriate.
* Ensure navigation remains easy to access.
* Avoid reducing the main content area excessively.

#### Mobile

* Hide the sidebar by default.
* Display a menu button in the header.
* Open the sidebar as an off-canvas drawer.
* Add a backdrop/overlay behind the sidebar.
* Allow the sidebar to be closed using:

  * The close button
  * The backdrop
  * The Escape key
* Prevent unwanted page scrolling while the mobile sidebar is open.
* Ensure keyboard accessibility and proper focus behavior.

### 4. Data Tables

Make all tables responsive without losing important information.

Requirements:

* Prevent horizontal layout overflow from breaking the page.
* Use horizontal scrolling when a table cannot fit on small screens.
* Add a visible and usable horizontal scroll container.
* Keep table headers aligned with their corresponding columns.
* Preserve sorting, filtering, pagination, row actions, and selection behavior.
* Avoid shrinking columns so much that the content becomes unreadable.
* Keep important columns visible when possible.
* Consider hiding only non-essential columns on smaller screens if the existing design supports it.
* Ensure action buttons remain accessible on mobile devices.
* Make table controls responsive and allow search, filters, pagination, and action buttons to wrap correctly.

Do not convert tables into cards unless the current UX clearly benefits from it and the table functionality can be preserved.

### 5. Charts and Graphs

Make all charts responsive.

Requirements:

* Charts must resize correctly when the viewport or parent container changes.
* Use responsive chart containers.
* Avoid hard-coded chart widths.
* Ensure charts do not overflow their parent containers.
* Preserve chart data, labels, legends, tooltips, interactions, and existing configurations.
* Adjust chart height appropriately for mobile screens.
* Prevent labels and legends from overlapping.
* Move or wrap legends when necessary.
* Ensure tooltips remain visible within the viewport.
* Use `ResizeObserver` or the chart library's responsive capabilities when appropriate.

### 6. Diagrams and Visualizations

Review all diagrams, flowcharts, architecture diagrams, and visual components.

Requirements:

* Prevent diagrams from being clipped or overflowing the page.
* Preserve the readability of nodes, labels, edges, and connections.
* Allow horizontal and/or vertical scrolling when a diagram cannot be meaningfully scaled down.
* Support zooming and panning if the current diagram library supports these features.
* Do not scale complex diagrams down until text becomes unreadable.
* Ensure diagrams resize correctly when the sidebar changes state.
* Recalculate diagram dimensions after layout changes if required.

### 7. Dashboard Cards and Widgets

* Use responsive CSS Grid or Flexbox layouts.
* Allow cards to automatically reflow based on available space.
* Use multiple columns on large screens.
* Reduce the number of columns on tablets.
* Display cards in a single column on small mobile screens when necessary.
* Ensure card content does not overflow.
* Make long titles, values, badges, and metadata wrap or truncate appropriately.
* Maintain consistent card heights only when it improves the visual layout.

### 8. Forms, Filters, and Actions

* Make forms usable on mobile devices.
* Stack form fields vertically when horizontal layouts become too narrow.
* Allow filter controls to wrap naturally.
* Ensure buttons remain easy to tap.
* Use appropriate minimum touch target sizes.
* Prevent buttons from being clipped or overflowing.
* Keep primary actions prominent.
* Use responsive button groups.
* Avoid placing too many actions in a single horizontal row on mobile.

### 9. Header and Navigation

* Make the header responsive.
* Prevent header items from overlapping.
* Ensure long page titles do not break the layout.
* Allow secondary actions to collapse, wrap, or move into a menu when necessary.
* Keep important actions accessible on all screen sizes.
* Ensure the mobile menu button is visible and usable.

### 10. Overflow and Layout Stability

Check the entire application for:

* Horizontal page overflow
* Content being clipped
* Elements overlapping
* Broken layouts at intermediate screen widths
* Fixed-width components
* Excessive use of absolute positioning
* Unresponsive containers
* Text overflow
* Long strings breaking layouts
* Charts or diagrams exceeding their containers
* Sidebar transitions causing layout jumps

Do not solve general overflow problems by applying `overflow-x: hidden` to the entire page. Fix the underlying layout issue instead.

### 11. Accessibility

Ensure responsive changes preserve or improve accessibility:

* Use semantic HTML where appropriate.
* Add accessible labels to icon-only buttons.
* Support keyboard navigation.
* Maintain visible focus states.
* Ensure sufficient color contrast.
* Use appropriate ARIA attributes for the sidebar drawer and navigation controls.
* Support the Escape key for dismissible mobile navigation and dialogs.
* Ensure responsive layouts remain usable with browser zoom.

### 12. Performance

* Avoid unnecessary re-renders.
* Avoid expensive resize event listeners.
* Use `ResizeObserver` where appropriate.
* Clean up event listeners and observers.
* Do not introduce unnecessary dependencies.
* Preserve or improve the existing application performance.

## Implementation Guidelines

1. First, inspect the existing project structure and identify:

   * The main layout
   * Sidebar components
   * Header components
   * Dashboard pages
   * Table components
   * Chart components
   * Diagram components
   * Shared layout and UI components
   * Existing responsive styles and breakpoints

2. Identify all components that currently have:

   * Fixed widths
   * Fixed heights
   * Hard-coded margins
   * Non-responsive grids
   * Layout overflow
   * Broken behavior on smaller screens

3. Implement responsive improvements incrementally.

4. Reuse existing components and styling conventions.

5. If the project uses Tailwind CSS:

   * Follow the existing Tailwind conventions.
   * Use responsive utility classes consistently.
   * Avoid mixing large amounts of custom CSS with Tailwind unless necessary.

6. If the project uses CSS Modules, styled-components, or another styling system:

   * Follow the existing architecture and conventions.
   * Do not introduce a new styling framework.

7. Do not use placeholder implementations. Apply the changes to the actual existing components.

## Testing Requirements

Test the application at least at these viewport widths:

* 320px
* 375px
* 390px
* 414px
* 768px
* 1024px
* 1280px
* 1440px
* 1920px

For each important page, verify:

* Sidebar behavior
* Header behavior
* Main content width
* Data table usability
* Chart responsiveness
* Diagram responsiveness
* Card layout
* Form layout
* Filter layout
* Button accessibility
* No unintended horizontal page scrolling
* No overlapping elements
* No clipped content

Also test resizing the browser dynamically from desktop width to mobile width and back.

## Expected Output

After implementing the changes, provide:

1. A summary of the responsive improvements.
2. A list of modified files.
3. A description of the sidebar behavior on desktop, tablet, and mobile.
4. A description of how tables behave on small screens.
5. A description of how charts and diagrams adapt to different screen sizes.
6. Any known limitations or remaining responsive issues.
7. Confirmation that existing functionality, APIs, business logic, and data flow were not changed.

Important: Do not only provide recommendations or a responsive design plan. Inspect the existing codebase and implement the responsive changes directly.
