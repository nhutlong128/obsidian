-  Type: #literature #react-bootstrap 
    Date written: [[2021-05-20, Thu]]  
    Source:  https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html
    Status: #done  
    Keywords:  #applicationdevelopment #webapp #css #react #react-bootstrap
	
### Notes

##### Layout
- Container
	- Containers provide a means to center and horizontally pad your site’s contents
	- ![[Pasted image 20210520171436.png]]
	- Fluid Container
		- You can use `<Container fluid />` for width: 100% across all viewport and device sizes.
		- ![[Pasted image 20210520171503.png]]
		- You can set breakpoints for the `fluid` prop. Setting it to a breakpoint (`sm, md, lg, xl`) will set the `Container` as fluid until the specified breakpoint.
			- ![[Pasted image 20210520171524.png]]


- Auto-layout columns
	- When no column widths are specified the `Col` component will render equal width columns
		- ![[Pasted image 20210520171614.png]]
	- ### Setting one column width
		- ![[Pasted image 20210520171800.png]]
	- ### Variable width content
		- ![[Pasted image 20210520171901.png]]

- ## Responsive grids
	- The `Col` lets you specify column widths across 5 breakpoint sizes (xs, sm, md, lg, and xl). For every breakpoint, you can specify the amount of columns to span, or set the prop to `<Col lg={true} />` for auto layout widths.
		- ![[Pasted image 20210520172752.png]]
	- You can use the `order` property to control the **visual order** of your content.
		- ![[Pasted image 20210520172848.png]]
		- ![[Pasted image 20210520172856.png]]
	- Setting column widths in Row
		- ![[Pasted image 20210520173047.png]]

- Media Objects
	- The media object helps build complex and repetitive components (e.g. blog comments, tweets, the like and more) where some media is positioned alongside content that doesn’t wrap around said media.
	- ![[Pasted image 20210520174607.png]]
	- Media List
		-  On your `ul` or `ol` , add the .list-unstyled to remove any browser default list styles, use `<Media as="li">` to render as a list item. As always, use spacing utilities wherever needed to fine tune.
		-  ![[Pasted image 20210520174709.png]]

##### Components
- ### Alerts
	- Provide contextual feedback messages for typical user actions with the handful of available and flexible alert messages.
	- ![[Pasted image 20210520174837.png]]
	- ![[Pasted image 20210520174845.png]]
	- Alert Link
		- For links, use the `<Alert.Link>` component to provide matching colored links within any alert.
		- ![[Pasted image 20210520175305.png]]
	- Alert Heading
		- Alerts can contain whatever content you like. Headers, paragraphs, dividers, go crazy.
		- ![[Pasted image 20210520175413.png]]
	- Dismissing
		- Add the `dismissible` prop to add a functioning dismiss button to the Alert.
		- ![[Pasted image 20210520175441.png]]
	- Button
		- You can also control the visual state directly which is great if you want to build more complicated alerts.
		- ![[Pasted image 20210520175700.png]]

- ### Accordion
	- Accordions use Card components to provide styling of the Accordion components. Use AccordionToggle to provide a button that switches between each AccordionCollapse component.
	- ![[Pasted image 20210520180058.png]]

- ### Breadcrumbs
	- Indicate the current page’s location within a navigational hierarchy that automatically adds separators via CSS. Add `active` prop to active `Breadcrumb.Item` . Do not set both `active` and `href` attributes. `active` overrides `href` and `span` element is rendered instead of `a` .
	- ![[Pasted image 20210520180254.png]]

- ### Buttons
	- Custom button styles for actions in forms, dialogs, and more with support for multiple sizes, states, and more.
	- ![[Pasted image 20210520180517.png]]
	- ## Button tags
		- Normally `<Button>` components will render a HTML `<button>` element. However you can render whatever you'd like, adding a `href` prop will automatically render an `<a />` element. You can use the `as` prop to render whatever your heart desires. React Bootstrap will take care of the proper ARIA roles for you.
		- ![[Pasted image 20210520180600.png]]

	- ## Sizes
		- ![[Pasted image 20210520180624.png]]
		- Create block level buttons—those that span the full width of a parent—by adding `block`
			- ![[Pasted image 20210520180652.png]]

	- ## Button loading state
		- ![[Pasted image 20210520180719.png]]

- ### Button groups
	- Group a series of buttons together on a single line with the button group.
		- ![[Pasted image 20210520180923.png]]
	- Button toolbar
		- Combine sets of `<ButtonGroup>`s into a `<ButtonToolbar>` for more complex components.
		- ![[Pasted image 20210520180951.png]]
	- Nesting
		- You can place other button types within the `<ButtonGroup>` like `<DropdownButton>`s
		- ![[Pasted image 20210520181049.png]]
- ### Cards
	- Bootstrap’s cards provide a flexible and extensible content container with multiple variants and options.
	- ![[Pasted image 20210520181135.png]]

	- ### Card Groups
		- ![[Pasted image 20210520181358.png]]
		- ![[Pasted image 20210520181408.png]]
	- ### Card Deck
		- ![[Pasted image 20210520181453.png]]
		- ![[Pasted image 20210520181502.png]]
	- ### Card Columns
		- ![[Pasted image 20210520181836.png]]
		- ![[Pasted image 20210520181843.png]]
- ### Carousel
	- A slideshow component for cycling through elements—images or slides of text—like a carousel.
	- ![[Pasted image 20210520181940.png]]
- ### Dropdowns
	- Toggle contextual overlays for displaying lists of links and more with the Bootstrap dropdown plugin
	- Single button dropdowns
		- ![[Pasted image 20210520182125.png]]
	- Dropdown items
		- ![[Pasted image 20210520182205.png]]
	- Menu alignment
		- ![[Pasted image 20210520182224.png]]
	- Menu dividers
		- ![[Pasted image 20210520182249.png]]
- ### 
