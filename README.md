# AI Security Guidance Tool

The AI Security Guidance Tool is a modern, web-based application that provides tailored guidance on AI security frameworks based on user-selected personas. This tool helps organizations and security professionals quickly access role-specific information—linking frameworks, guidance, and resources—to improve the security posture of their AI systems.

## Features

- **Dynamic Persona Selection:** Choose from various personas (e.g., Executives, CISO/SSO, IT Architects) using a dropdown menu.
- **Tailored Guidance:** View role-specific guidance and recommended AI security frameworks.
- **Unified Resources:** Displays a de-duplicated list of relevant resource links for each persona.
- **Modular Data Structure:** Data is stored in a separate JSON file (`data.json`) with a normalized structure for easy maintenance and future expansion.
- **Modern Design:** Responsive, sleek design using HTML, CSS, Flexbox, and Google Fonts.

## Repository Structure

- **index.html**: Main web page for the tool.
- **data.json**: Contains the normalized data for resources and personas.
- **data-schema.json**: JSON Schema used to validate the structure of `data.json`.
- **DATA_UPDATE_INSTRUCTIONS.md**: Guidelines for updating and maintaining the data.
- **README.md**: This documentation file.

## Getting Started

### Prerequisites

Since modern browsers enforce strict CORS policies for local files, you will need to run a web server to view the tool. Here are a couple of simple options:

- **Using Python 3:**
  ```bash
  python -m http.server
  ```
  This command starts a server on [http://localhost:8000](http://localhost:8000).

- **Using Node.js (http-server):**
  Install the server globally:
  ```bash
  npm install -g http-server
  ```
  Then run:
  ```bash
  http-server
  ```
  Your repository will be served on [http://localhost:8080](http://localhost:8080) (or another port).

### Running the Tool

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/your-username/your-repository.git
   cd your-repository
   ```
2. **Start Your Web Server:**  
   Run one of the above commands in the repository directory.
3. **Open Your Browser:**  
   Navigate to the local server URL (e.g., [http://localhost:8000](http://localhost:8000)).
4. **Use the Tool:**  
   Select a persona from the dropdown to view the corresponding guidance and resource links.

## Updating Data

### Data Structure

The tool’s data is stored in `data.json`, which is divided into two sections:

- **resources:** A list of unique resource objects (each with an `id`, `title`, and `url`).
- **personas:** A list of persona objects that include:
  - `id`: A unique identifier for the persona.
  - `name`: The display name.
  - `frameworks`: An array of resource IDs representing core frameworks.
  - `guidance`: Role-specific guidance text.
  - `resourceRefs`: An array of resource IDs for additional resources.

### JSON Schema

The file `data-schema.json` defines the expected structure for `data.json`. It ensures data consistency and helps with validation during updates.

### Guidelines for Data Updates

Refer to [DATA_UPDATE_INSTRUCTIONS.md](DATA_UPDATE_INSTRUCTIONS.md) for:
- Detailed instructions on updating the `resources` and `personas` sections.
- Best practices to maintain consistency (e.g., referencing resource IDs correctly).
- Steps for validating the updated data against the JSON Schema.

## Contributing

Contributions, bug reports, and feature requests are welcome! Feel free to open issues or submit pull requests to improve the tool.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.


## Contact

For questions, feedback, or further information, please open an issue on this repository.