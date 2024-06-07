# DataCon 3.0. Design a Peptide Vector for Drug Delivery

![Project logo](https://t3.ftcdn.net/jpg/04/87/14/48/360_F_487144857_lwRd6hyeEktmt70UOAgojHzlwvY6OgQp.jpg)

## About the project :information_source:

### What are CPPs?

   **Cell-penetrating peptides (CPPs)** are short sequences of amino acids that have the remarkable ability to cross cellular membranes, facilitating the intracellular delivery of various therapeutic agents, including drugs, nucleic acids, and proteins. These peptides exploit mechanisms such as direct penetration or endocytosis to traverse cell membranes, making them powerful tools in drug delivery systems. 

![image](https://github.com/acid-design-lab/DataCon24/assets/82499756/2f5822f6-cac3-492f-9a73-40b3d3e60b3e)

   In real-world medical applications, CPPs are being leveraged to enhance the efficacy of treatments for a range of conditions. For instance, they are used in targeted cancer therapies to deliver chemotherapeutic agents directly to tumor cells, minimizing damage to healthy tissues. Additionally, CPPs are employed in gene therapy to transport genetic material into cells, offering potential treatments for genetic disorders like cystic fibrosis and muscular dystrophy. Their versatility and efficiency in overcoming cellular barriers position CPPs as a promising frontier in the development of advanced therapeutic strategies.

### Project pipeline :arrow_forward:

![ml-project-pipeline](https://github.com/acid-design-lab/DataCon24/assets/82499756/fe94406a-eaf2-46c0-8935-82e1fc4192ca)

   Our ultimate goal is to develop precise machine learning (ML) model allowing to **design CPPs with superior activity**. Here are the main steps which will allow you to build a precise model for CPP design:
   
   **1. Data curation and cleaning.** All inappropriate or ambiguous data should be removed or corrected.
   
   **2. Data unification.** The data presented in Datasets are heterogeneous and should be unified in terms of variables, measurement units etc.
   
   **3. System parametriation.** You need to choose the set of parameters to describe CPPs as well as experimental setup. Most of the models use symbolic representations lacking physico-chemical properties crucial for CPP activity prediction.
   
   **4. Model selection.** Best-performing models should be choosen for screening depending on the task complexity (sequence classification or sequence generation).
   
   **5. Feature selecction.** After model selection, features used in the model should be choosen showing optimal prediction performance, robustness, and interpretability.
   
   **6. Evaluation.** Every model should be evaluated beyond performance on train/test datasets. It can be structural analysis of CPP candidates, modelling of interaction with cellular membranes etc.
   
   **7. Project design.** All results should be structured and systematized on GitHub for transparency and reproducibility.

### Challenges :trophy:

   The main challenge here is to develop **unbiased model** not limited to existing CPP structures and cell penetration mechanisms. Another challenge is to develop CPPs **for particular drug delivery system and setup**, which includes multi-property optimization (amphiphilicity, molecular weight, toxicity etc.). Finally, models should be **interpretable**, which means user should know why particular CPP demonstrates its activity, and what are the possible ways to improve it further.

### Schedule :calendar:

   DataCon 3.0 includes not only practices but authoritative lectures and other activities, therefore check for any schedule updates [HERE](https://scamt.ifmo.ru/datacon/).

### Contents :open_book:

   This repository contains the following data:
   1. **Articles about CPPs** to read (see the relevant folder)
   2. **Available datasets** for model development (see **Data Description** section)
   3. **Useful tools** for property and structure prediction (see **Useful tools** section and relevant folder)

## Data description :floppy_disk:

### 1. Mixed CPPs
   
   Contains CPPs with natural or modified amino acids.

      1.1. POSEIDON
   
      Contains heterogeneous experimental data regarding CPP (natural and non-natural amino acids) activity measurements (.csv format), which are:
      - peptide name,
      - target cell line CPP was tested on cell penetration ability,
      - delivered molecule/protein,
      - paper PubMed ID,
      - cellular uptake measurement + measurement units,
      - CPP+cargo concentration,
      - incubation time,
      - incubation temperature,
      - determination method,
      - uptake type,
      - sequence.

### 2. Natural CPPs
   
   Contains only sequences with natural amino acids.

       2.1. CPPBase
      
       Contains sequences of CPPs with experimentally proved activity in .fasta format.

   
       2.2. Experimental and Experimental2
      
       Contain more sequences of CPPs with experimentally proved activity in .txt format.

   
       2.3. Experimental_high_uptake
      
       Contains CPP sequences with high (but not stated) uptake in .txt format.

       2.4. Balanced_dataset
       
       Represents a balanced dataset of CPPs and non-CPPs; often used for model benchmarking.

### 3. Non-CPPs
   
   Contains negative CPP samples in .txt format.

       3.1. Generated
      
       Contains randomly generated sequences treated as negative.

   
       3.2. Experimental
      
       Contains non-CPP sequences shown not to demonstrate activity experimentally.

### 4. Non-Natural CPPs
   
   Contains CPPs consisting of non-natural amino acids.

       4.1. CPPBase_modified
      
       Contains a list of modified CPPs with experimentally proved activity in .fasta format.

      
       4.2. CPPBase_modified_symbols
      
       Contains a list of abbreviations for modified amino acids  in .txt format (ABBREVIATION: NAME; ...: ...).


## Useful tools :bookmark_tabs:

### Structure prediction

   In the relevant folder you can find a Jupiter notebook with AlphaFold 2. 
   
   Just insert the sequence

   ![insert sequence](https://github.com/acid-design-lab/DataCon24/assets/82499756/607ad1b2-0b29-4490-8771-76de5fd6f9b3)

   and get a 3D structure!

   ![3d](https://github.com/acid-design-lab/DataCon24/assets/82499756/2b02a2e2-c471-4cbd-9824-28123bc12925)

### Modelling of interaction with membrane

   For CPPs from 7 to 24 amino acids you can use [PMIpred neural network model](https://pmipred.fkt.physik.tu-dortmund.de/curvature-sensing-peptide/) trained on Molecular Dynamics (MD) data to predict its interaction with the cellular membrane. Please use modelling on neutral membrane for better differentiation between CPPs and non-CPPs.

   Example: 

   CPP sequence FSLHRYMAWFCPWTGAWLMLD is predicted to **BIND** to the membrane.

### Membrane permeability prediction

   For so-called stapled peptides consisting of both natural and modified amino acids you can predict membrane permeability using [STAPEP package](https://github.com/dahuilangda/stapep_package) offering the full pipeline from data preprocessing to ML model development and use on novel samples.

   ![image](https://github.com/acid-design-lab/DataCon24/assets/82499756/b43c427b-c504-471d-97f8-fee6988ffd22)

   Non-CPP sequence is predicted **NOT TO BIND** to the membrane.

   ![image](https://github.com/acid-design-lab/DataCon24/assets/82499756/2b559f32-b117-49a0-a3a2-a3298dabcd6c)

