## User Story: Create a New Customer Order

**As** a user who manages customer orders,

**I want to** create a new customer order,

**So that I can** specify the customer, expected delivery date, destination, warehouse, and order details,

### Acceptance Criteria

#### Scenario 1: Starting the order creation process

- **Given** I am logged into the order management system,
- **When** I navigate to the "Create New Order" page,
- **Then** I should see options to select a customer, set the expected delivery date, choose a destination and select a warehouse from a dropdown list.

#### Scenario 2: Selecting a customer

- **Given** I am on the "Create New Order" page,
- **When** I select a customer from the customer dropdown,
- **Then** the selected customer should be associated with this order.

#### Scenario 3: Setting the expected delivery date

- **Given** I am on the "Create New Order" page,
- **When** I choose an expected delivery date,
- **Then** the selected date should be set as the expected delivery date for this order.

#### Scenario 4: Selecting a destination

- **Given** I am on the "Create New Order" page,
- **When** I choose a destination from the dropdown list,
- **Then** the selected destination should be associated with this order.

#### Scenario 5: Selecting a warehouse

- **Given** I am on the "Create New Order" page,
- **When** I select a warehouse from the dropdown list,
- **Then** the selected warehouse should be associated with this order.

#### Scenario 6: Adding order lines

- **Given** I am on the "Create New Order" page,
- **When** I select a style from the style dropdown,
- **And** I add order lines with quantity, size, and color,
- **Then** the order lines should be added to this order.

#### Scenario 7: Selecting size and color from dropdowns

- **Given** I am adding an order line,
- **When** I select a size and color from the dropdowns,
- **Then** the selected size and color should be associated with the order line.

#### Scenario 8: Adding multiple order lines

- **Given** I am on the "Create New Order" page,
- **When** I add multiple order lines with different styles, quantities, sizes, and colors,
- **Then** all the order lines should be added to this order.

#### Scenario 9: Saving the order

- **Given** I am on the "Create New Order" page,
- **When** I have added all the necessary details and order lines,
- **And** I click the "Save Order" button,
- **Then** the order should be saved with a status of 50 (approval pending).

### Definition of Done (DOD)

- The user can successfully create a new customer order with all required details.
- The order is associated with the selected customer, expected delivery date, destination, warehouse, and order lines.
- The order lines include style, quantity, size, and color information.
- The order is saved with a status of 50 (approval pending).
- Once the order is successfully saved, an event must be published to the Kafka `cosmos.customerorder.create.1` topic.
  - The event payload should include information about the created customer order (CO).
