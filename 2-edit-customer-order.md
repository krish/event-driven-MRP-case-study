## User Story: Edit Customer Order

**As** a user who manages customer orders,

**I want to** edit an existing customer order,

**So that I can** modify the order quantity, delivery date, destination, and warehouse,

### Acceptance Criteria

#### Scenario 1: Starting the order editing process

- **Given** I am logged into the order management system,
- **When** I navigate to the "Edit Order" page,
- **Then** I should be able to search for and select the customer order I want to edit.

#### Scenario 2: Modifying order quantity

- **Given** I am on the "Edit Order" page,
- **When** I change the order quantity for the selected order,
- **Then** the order quantity should be updated.

#### Scenario 3: Modifying delivery date

- **Given** I am on the "Edit Order" page,
- **When** I change the delivery date for the selected order,
- **Then** the delivery date should be updated.

#### Scenario 4: Modifying destination

- **Given** I am on the "Edit Order" page,
- **When** I change the destination for the selected order,
- **Then** the destination should be updated.

#### Scenario 5: Modifying warehouse

- **Given** I am on the "Edit Order" page,
- **When** I change the warehouse for the selected order,
- **Then** the warehouse should be updated.

#### Scenario 6: Saving the edited order

- **Given** I am on the "Edit Order" page,
- **When** I have made the desired changes to the order quantity, delivery date, destination, and warehouse,
- **And** I click the "Save Order" button,
- **Then** the edited order should be saved.

#### Scenario 7: Publishing an event after order edit

- **Given** I am on the "Edit Order" page,
- **And** I have successfully saved the edited order,
- **Then** an event should be published to the Kafka `cosmos.customerorder.update.1` topic.
  - The event payload should include information about the edited customer order (CO) with before-after tags.
  - The "before" section should contain the original values of the order (quantity, delivery date, destination, and warehouse).
  - The "after" section should contain the new values of the order (quantity, delivery date, destination, and warehouse).

### Definition of Done (DOD)

- The user can successfully edit an existing customer order, modifying the order quantity, delivery date, destination, and warehouse.
- The edited order is saved with the updated information.
- After successfully saving the edited order, an event is published to the Kafka `cosmos.customerorder.update.1` topic with the updated customer order information.
