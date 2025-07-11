# GeNet Framework Repository

GeNet is a multimodal co-pilot framework designed to simplify and automate network engineering workflows described in our paper: [GeNet a Multimodal LLM Based Co Pilot for Network Topology and Configuration- ICDCS25](https://github.com/networkcopilot/GeNet-Framewok/blob/main/GeNet%20a%20Multimodal%20LLM%20Based%20Co%20Pilot%20for%20Network%20Topology%20and%20Configuration%20ICDCS%20Short.pdf) (DOI 10.1109/ICDCSW63273.2025.00026). By leveraging large language models (LLMs) and integrating both textual and visual data, GeNet enables enterprise network engineers to design, interpret, and modify network topologies and device configurations based on user intents.

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
1. **Initial Files** - The initial files consist a directory per scenario which consist of the input intent textual file and configuration textual file
2. **Scoring Keys** - The scoring keys for each scenario for measuring the level of success in implementing the intent
3. **Topology Image Variants** - The dataset for the Topology Understanding Module
4. **Topologies Ground Truth Representations** - The structured representations of the topologies per scenario which are used as a ground truth for the Topology Understanding part

The Topology Image Variants directory architecture:
 - Topology_image_variants
   - {visualization_format}
     - {diagram_type}
        - {scenario_name}
          - {scenario_name}.jpg (the diagram image)
          - GNS3 file or Powerpoint slide of the diagram (according to the visualization format)


Visualization_formats : [GNS3, Paper_Sketches, PowerPoint]

Diagram_type: [Messy_Layout, No_Labels_On_Edges, Normal]

---
## Citing our paper
If you use or find GeNet valuable please cite our paper:

[GeNet a Multimodal LLM Based Co Pilot for Network Topology and Configuration - ICDCS25](https://github.com/networkcopilot/GeNet-Framewok/blob/main/GeNet%20a%20Multimodal%20LLM%20Based%20Co%20Pilot%20for%20Network%20Topology%20and%20Configuration%20ICDCS%20Short.pdf)

@article{ifland2024genet,
  title={Genet: A multimodal llm-based co-pilot for network topology and configuration},
  author={Ifland, Beni and Duani, Elad and Krief, Rubin and Ohana, Miro and Zilberman, Aviram and Murillo, Andres and Manor, Ofir and Lavi, Ortal and Kenji, Hikichi and Shabtai, Asaf and others},
  journal={arXiv preprint arXiv:2407.08249},
  year={2024}
}

---

## License

This project is licensed under [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.en).
