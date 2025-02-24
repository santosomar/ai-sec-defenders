# Data Update Instructions for the AI Security Guidance Tool

This document explains the structure and guidelines for updating the `data.json` file used by the AI Security Guidance Tool. Keeping your data normalized and validated ensures consistency and simplifies future expansion.

## Overview

The `data.json` file contains two main sections:

1. **resources**: A list of unique resource objects.
2. **personas**: A list of persona objects that reference the resources by their IDs.

## JSON Schema

You can validate the file against the provided JSON Schema (see `data-schema.json`):

- **resources**: An array where each object must include:
  - **id** (string): A unique identifier for the resource (e.g., `nist_rmf`).
  - **title** (string): The display title of the resource (e.g., "NIST AI RMF").
  - **url** (string): A valid URL (must follow URI format).

- **personas**: An array where each object must include:
  - **id** (string): A unique identifier for the persona (e.g., `executives`).
  - **name** (string): The display name for the persona.
  - **frameworks** (array of strings): A list of resource IDs that represent the frameworks relevant to this persona.
  - **guidance** (string): A description or guidance text for the persona.
  - **resourceRefs** (array of strings): A list of resource IDs providing additional resource links for the persona.

## Updating the `resources` Section

- **Purpose:** Define unique resources used throughout the tool.
- **Required Fields:**
  - **id**: Unique string (e.g., `"nist_rmf"`).
  - **title**: Display name of the resource.
  - **url**: A valid URL for the resource.
- **Example:**

  ```json
  {
    "id": "nist_rmf",
    "title": "NIST AI RMF",
    "url": "https://www.nist.gov/ai-risk-management-framework"
  }
  ```

## Updating the `personas` Section

- **Purpose:** Map each persona to the relevant frameworks and guidance.
- **Required Fields:**
  - **id**: Unique identifier for the persona (e.g., `"executives"`).
  - **name**: Display name (e.g., `"Executives"`).
  - **frameworks**: Array of resource IDs corresponding to core frameworks.
  - **guidance**: Guidance text explaining the role or responsibilities.
  - **resourceRefs**: Array of resource IDs for additional related resources.
- **Example:**

  ```json
  {
    "id": "executives",
    "name": "Executives",
    "frameworks": ["nist_rmf", "nist_csf", "ztm"],
    "guidance": "Define the organization's risk tolerance, align strategy with business objectives, and oversee governance and compliance for AI systems.",
    "resourceRefs": ["nist_rmf", "nist_csf", "ztm"]
  }
  ```

## General Guidelines

- **Consistency:**  
  Ensure that any resource IDs referenced in `frameworks` and `resourceRefs` exist in the `resources` section.

- **Validation:**  
  Validate your updated `data.json` file against the provided JSON Schema (`data-schema.json`) to ensure proper structure.

- **Version Control:**  
  Keep track of changes to the `data.json` file with version control to monitor updates over time.

- **Future Expansion:**  
  You can add new properties (e.g., descriptions, images, metadata) as needed. If you do so, update the JSON Schema accordingly.

