# Implement Client Script & UI Policy (Incident)

## Project Overview

The project **"Implement Client Script & UI Policy (Incident)"** is developed using the ServiceNow platform to improve data accuracy and control the behavior of Incident records.

In Incident Management, users may enter incomplete, inconsistent, or incorrect information while creating or updating incidents. To reduce such errors, this project uses **UI Policies, UI Policy Actions, and Client Scripts** to dynamically control fields, automatically update values, validate user inputs, and prevent unwanted changes.

---

## Project Objective

The main objective of this project is to implement client-side controls in ServiceNow Incident Management.

The project focuses on:

- Improving data accuracy in Incident records.
- Dynamically controlling Incident form fields.
- Making required fields mandatory based on conditions.
- Automatically updating field values.
- Validating Incident records before submission.
- Preventing unwanted State changes through list editing.
- Allowing valid changes through the Incident form.

---

## Platform Used

**Platform:** ServiceNow

**Module:** Incident Management

**Environment:** ServiceNow Personal Developer Instance (PDI)

---

# Project Phases

The project was completed through the following eight phases:

1. Brainstorming & Ideation Phase
2. Requirement Analysis Phase
3. Project Design Phase
4. Project Planning Phase
5. Project Development Phase
6. Project Testing Phase
7. Project Documentation Phase
8. Project Demonstration Phase

---

# Phase 1 – Brainstorming & Ideation

The project was started by identifying a problem in Incident Management.

Users may enter incomplete or incorrect information while creating or updating Incident records. Manual checking of every field can also lead to errors.

The proposed idea was to use **UI Policies and Client Scripts** to automatically control Incident fields according to specific conditions.

The main objective identified during this phase was to improve data accuracy and provide controlled Incident form behavior.

---

# Phase 2 – Requirement Analysis

The required functionalities were identified before development.

### Functional Requirements

- Create a UI Policy for High Impact Incidents.
- Make Assignment Group mandatory when Impact is High.
- Make Urgency read-only when Impact is High.
- Automatically set Urgency to High when Impact is High.
- Prevent saving when Assigned To is empty for High Impact incidents.
- Prevent State changes through direct list editing.
- Allow State changes through the Incident form.
- Reverse the UI Policy behavior when Impact changes from High to another value.

### Software Requirements

- ServiceNow PDI
- Web Browser
- ServiceNow Incident Management
- UI Policy
- UI Policy Action
- Client Scripts

---

# Phase 3 – Project Design

The project was designed to control Incident records based on the value entered in the Impact field.

The main workflow is:

**Incident Form → Impact = High → UI Policy / Client Script → Field Control & Validation → Record Submission**

### UI Policy Design

A UI Policy named **High Impact Control** was created for the Incident table.

When Impact is set to **1 – High**:

- Assignment Group becomes mandatory.
- The policy condition controls the required field behavior.
- Reverse if false is enabled to restore the normal behavior when the condition is no longer true.

### UI Policy Action

A UI Policy Action was configured for **Urgency**.

When Impact is High, the Urgency field becomes **read-only**.

### Client Script Design

Three Client Scripts were implemented:

- **onChange** – Automatically sets Urgency to High when Impact is High.
- **onSubmit** – Prevents saving when Assigned To is empty for a High Impact Incident.
- **onCellEdit** – Prevents State changes through direct list editing.

---

# Phase 4 – Project Planning

The project was planned as a sequence of configuration and testing activities.

### Development Tasks

1. Create High Impact Control UI Policy.
2. Configure Urgency UI Policy Action.
3. Create onChange Client Script.
4. Create onSubmit Client Script.
5. Create onCellEdit Client Script.

### Testing Plan

The following scenarios were planned for testing:

- High Impact validation.
- Successful Incident submission.
- Reverse condition testing.
- State list-edit restriction.
- State update through the Incident form.

The planned workflow was:

**Planning → Configuration → Client Script Development → Testing → Result Verification → Demonstration**

---

# Phase 5 – Project Development

The required ServiceNow configurations were implemented step by step.

### Task 1 – High Impact Control

A UI Policy named **High Impact Control** was created for the Incident table.

Condition:

**Impact is 1 – High**

When the condition is satisfied, the **Assignment Group** field becomes mandatory.

---

### Task 2 – Urgency UI Policy Action

A UI Policy Action was created under **High Impact Control**.

The field selected was:

**Urgency**

The **Read-only** option was enabled so that Urgency could not be directly changed when Impact was High.

---

### Task 3 – Auto Set Urgency

An **onChange Client Script** named:

**Auto set urgency for high impact**

was created for the Impact field.

When Impact changes to High, the script automatically sets Urgency to High and displays an information message.

---

### Task 4 – Prevent Save if Assigned To is Missing

An **onSubmit Client Script** named:

**Prevent save if Assigned To missing**

was created.

When Impact is High and Assigned To is empty, the script prevents the Incident from being submitted and displays the validation message.

---

### Task 5 – Prevent State Change Through List Editing

An **onCellEdit Client Script** named:

**Prevent state change via list edit**

was created for the State field.

When a user attempts to change State directly from the Incident list, the system displays an alert and prevents the change.

State changes can still be performed through the Incident form.

---

# Phase 6 – Project Testing

The implemented features were tested using different Incident scenarios.

### Activity 1 – Create New Incident

An Incident was created with Impact set to High and Assigned To left empty.

The system prevented the Incident from being submitted and displayed the required validation message.

### Activity 2 – Successful Incident Submission

Assigned To was provided and the Incident was submitted again.

The Incident was saved successfully and the configured field behavior was verified.

### Activity 3 – Reverse Condition Test

Existing Incident **INC0010003** was tested.

Impact was changed from High to Medium.

After changing the Impact:

- Assigned To was no longer mandatory.
- Urgency became editable.
- The Incident was saved successfully.

### Activity 4 – State List Edit Test

The Incident list was opened and an attempt was made to directly edit the State field.

The configured alert was displayed and the State change was prevented.

### Activity 5 – State Form Update Test

The Incident was opened through the Incident form.

The State was changed and the record was updated.

The State change was saved successfully through the form.

---

# Phase 7 – Project Documentation

The complete project implementation and testing activities were documented.

The documentation contains:

- Project problem identification
- Project objective
- Requirements
- Project design
- Project planning
- Development activities
- Testing activities
- Testing results
- Screenshots of important configurations and outputs
- Final project outcome

The complete project report is available in this repository as:

**`project.pdf`**

---

# Phase 8 – Project Demonstration

A complete demonstration of the project is prepared using the ServiceNow environment.

The demonstration covers:

- Project Name
- Purpose of the Project
- Use and Benefits
- Project Execution
- Working Process
- UI Policy configuration
- Client Script configuration
- Testing process
- Final Output

The demonstration video will be uploaded to Google Drive and the public viewing link will be added to this README.

---

# Project Benefits

The project provides the following benefits:

- Helps improve Incident data accuracy.
- Reduces incomplete or incorrect submissions.
- Provides automatic field updates.
- Dynamically controls Incident form fields.
- Validates required information before submission.
- Prevents unwanted State changes through list editing.
- Provides consistent Incident record handling.

---

# Final Output

The project successfully demonstrates the implementation of **UI Policies and Client Scripts** in ServiceNow Incident Management.

The configured features control field behavior, automatically update values, validate Incident information, and restrict unwanted list-based State changes.

The project was tested using the required Incident scenarios and the results were documented.

---

# Project Documentation

The complete project report containing all eight phases is available here:

**[View Complete Project Report](./project.pdf)**

---

# Project Demonstration Video

The complete project demonstration video will be available through the Google Drive link below.

**Google Drive Video Link:**  
`https://drive.google.com/file/d/1n-FMtacxT7LORkD4AD_BSkFDU2I699Kq/view?usp=sharing`

---

# Conclusion

The **Implement Client Script & UI Policy (Incident)** project demonstrates how ServiceNow UI Policies and Client Scripts can be used to provide dynamic field control and validation in Incident Management.

The project covers planning, design, development, testing, documentation, and demonstration of the required functionality in the ServiceNow environment.
