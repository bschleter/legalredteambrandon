# agent-sim


Much the same as original COT agent-sim code with changes to prompts and scenario descriptions. Minor changes to int for allowing longer or more conversation changes. Original credit and repo is from Barry Zhang @nub3Ar.
Original repo @ (https://github.com/NomosArtificial/agent-sim.git)
Adversarial COT was main use. 
****************************************************
Law-making and legal interpretation convert opaque human goals and values into legible directives. At Stanford, we are working on [A Legal Informatics Approach to Aligning Artificial Intelligence with Humans](https://law.stanford.edu/projects/a-legal-informatics-approach-to-aligning-artificial-intelligence-with-humans/), a research agenda leveraging legal processes and concepts for AI alignment. Like how parties to a legal contract cannot foresee every potential “if-then” contingency of their future relationship, and legislators cannot predict all the circumstances under which their bills will be applied, we cannot ex ante specify “if-then” rules that provably direct good AI behavior. Legal theory and practice offer arrays of tools to address these problems. For instance, legal standards allow humans to develop shared understandings and adapt them to novel situations, i.e., to generalize expectations regarding actions taken to unspecified states of the world. We are leveraging the data generated by legal processes and the tools of law (methods of law-making, statutory interpretation, contract drafting, applications of standards, and legal reasoning) to facilitate the robust specification of inherently vague human goals to increase human-AI alignment.

To enable more deployments of LLMs in higher stakes use-cases, we are conducting in-depth LLM-powered multi-agent simulations demonstrating alignment of the actions of the LLM agents with legal standards through a variety of techniques. We have also received a research grant to pay human lawyers to review and rank outputs for legal human feedback on the outputs.

Our [initial focus is on fiduciary duties](https://law.stanford.edu/publications/large-language-models-as-fiduciaries-a-case-study-toward-robustly-communicating-with-artificial-intelligence-through-legal-standards/).

## How to run

### 1. Install dependencies

```bash
poetry install
```

### 2. Start the monitoring server

```bash
poetry run langchain plus start
```

### 3. Run the notebook

```bash
OPENAI_API_KEY="<your_api_key>" poetry run jupyter notebook
```

### Components

### 1. Agents

We have provided a simple implementation of an agent that supports conversation and memory as a starting point. Here are a couple of its features:

1. Model Instantiation: The agents could be generated with any model through langchain and will take in a role and an inception (role-definition) prompt
2. Memory: The agent has a selective and alterable conversation memory such that it could converse without remembering the conversation and additional/altered
   memory could be injected
3. Reflection: To support longer memory windows, a memory summarization function (called "reflection") is automatically triggered as the conversation gets longer.

Please feel free to modify this class or create your own as needed

### 2. Simulation Environment

We have provided some examples in Simulation Examples.ipynb but this is where you can get creative!
