# DataCon 3.0

Data description:

1. Mixed CPPs.
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

2. Natural CPPs.
Contains only sequences with natural amino acids.

   2.1. CPPBase
   Contains sequences of CPPs with experimentally proved activity in .fasta format.

   2.2. Experimental and Experimental2
   Contain more sequences of CPPs with experimentally proved activity in .txt format.

   2.3. Experimental_high_uptake
   Contain CPP sequences with high (but not stated) uptake in .txt format.

3. Non-CPPs.
Contains negative CPP samples in .txt format.

   3.1. Generated
   Contains randomly generated sequences treated as negative.

   3.2. Experimental
   Contains non-CPP sequences shown not to demonstrate activity experimentally.

4. Non-Natural CPPs.
Contains CPPs consisting of non-natural amino acids.

   4.1. CPPBase_modified
   Contains a list of modified CPPs with experimentally proved activity in .fasta format.
   
   4.2. CPPBase_modified_symbols
   Contains a list of abbreviations for modified amino acids  in .txt format (ABBREVIATION: NAME; ...: ...).
