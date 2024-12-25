# GeNet Framework Repository

GeNet is a multimodal co-pilot framework designed to simplify and automate network engineering workflows. By leveraging large language models (LLMs) and integrating both textual and visual data, GeNet enables enterprise network engineers to design, interpret, and modify network topologies and device configurations based on user intents.

---


### Key Features
- **Topology Understanding:** Automatically interprets network topology images (including low-quality handwritten diagrams) into textual representations.
- **Intent Implementation:** Modifies network configurations and topologies to align with user intents using a large language model.
- **Automatic Evaluation:** Includes an LLM-based evaluation framework to assess implementation quality with strong correlation to human evaluation.
- **Wide Input Support:** Works with various topology formats like emulation software outputs (e.g., GNS3), PowerPoint diagrams, and even hand-drawn sketches.

### Motivation

Managing network topologies in enterprise environments is complex, error-prone, and time-consuming. GeNet was developed to bridge the gap between high-level network intents and low-level implementations, streamlining network design and configuration processes.

### Core Modules
1. **Topology Understanding Module:**
   - Converts network topology images into detailed textual descriptions.
   - Supports diverse diagram formats and varying quality levels.
2. **Intent Implementation Module:**
   - Updates network configurations and topologies based on user-defined intents.
   - Provides explanations for every change to enhance user understanding.
3. **Evaluation Framework:**
   - Automates the evaluation of implemented intents against predefined quality metrics.

### Use Cases
- **Network Expansion:** Add devices to a network with configurations automatically updated (e.g., adding PCs or servers to a topology).
- **Policy Updates:** Modify network configurations for tasks such as adding firewalls or changing access lists.
- **Visualization Enhancement:** Simplify the interpretation of complex or messy network diagrams.

### Performance
- High accuracy in interpreting network topology images, achieving strong agreement with human evaluations.
- Processes intents with an average response time of 81 seconds.
- Supports complex tasks while maintaining reliability, even with incomplete or low-quality input specifications.


---


## Dataset 
The dataset is splitted into 2 main directory - **Topology based Scenarios** and **Configuration Based Scenarios**.

#### The Topology based scenarios:
- Adding Communication Servers (E)
- Adding DMZ (M)
- Adding DRA (H)
- Adding Local PCs (E)
- Internet Connectivity (M)

#### The Configuration base scenarios:
- Basic Zone Based Firewall (H)
- IP Traffic Export (M)
- Role Based CLI Access (E)
- Time Based Access List (E)
- Transparent IOS Firewall (M)

(scenarios divided into scenario types and complexity levels where (E) marks Easy, (M) marks Medium, and (H) marks Hard, based on expert survey)

### Dataset Directory Structure
Each directory consist of 3 folders:
1. **Input Files** - The input files consist a directory per scenario which consist of intent textual file and configuration textual file
2. **Scoring Keys** - The scoring keys for each scenario for measuring the level of success in implementing the intent
3. **Topology Image Variance** - The dataset for the Topology Understanding Module

The Topology Image Variance directory architecture:
 - Topology_image_variance
   - {visualization_format}
     - {diagram_type}
        - {scenario_name}
          - {scenario_name}.jpg (the diagram image)
          - GNS3 file or Powerpoint slide of the diagram (according to the visualization format)


Visualization_formats : [GNS3, Paper_Sketches, PowerPoint]

Diagram_type: [Messy_Layout, No_Labels_On_Edges, Normal]


