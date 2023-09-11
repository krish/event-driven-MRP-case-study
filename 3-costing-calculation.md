## User Story: Calculate Costing for Customer Orders

As a system administrator or user responsible for order management,  
I want the system to automatically calculate the costing for each new customer order when it is created,  
So that I can provide accurate cost estimates to customers and make informed business decisions.

### Acceptance Criteria

#### Scenario 1: Initial Order Creation

1. **Given** a new customer order is received through Kafka,
2. **And** the order contains one or more order lines with product information and quantities,
3. **And** the Bill of Materials (BOM) for each style in the order is available in the system,
4. **And** the BOM includes the following product cost components per unit: labor cost, machine cost, and storage cost,
5. **And** the system maintains raw material (RM) costing data for transportation and storage on a warehouse-wise basis,
6. **When** the system calculates the costing for each order line,
7. **Then** it should calculate the cost for each order line by summing the product cost components (labor cost, machine cost, and storage cost) based on the BOM of the style,
8. **And** it should consider the relevant transportation and storage costs based on the warehouse associated with the order line,
9. **And** it should store the calculated cost for each order line.

#### Scenario 2: Cost Summation for the Entire Order

1. **Given** a new customer order is received through Kafka,
2. **And** the order contains one or more order lines with product information and quantities,
3. **And** the system has successfully calculated the cost for each order line based on the BOM and RM costing data,
4. **When** the system calculates the total cost of the order,
5. **Then** it should sum the costs of all order lines to determine the total cost of the entire customer order.

**Definition of Done:**

- The system accurately calculates the product cost components (labor cost, machine cost, and storage cost) for each order line based on the BOM of the style.
- The system considers warehouse-specific RM costing data for transportation and storage costs.
- The calculated costs for each order line are stored and associated with the respective order line.
- The system correctly sums up the costs of all order lines to provide the total cost for the entire customer order.
- The costing calculations are triggered automatically upon receiving a new customer order through Kafka.
- The calculated costs are made available for viewing and reporting within the system.
- Appropriate error handling and logging mechanisms are in place to handle any issues during the costing calculation process.
