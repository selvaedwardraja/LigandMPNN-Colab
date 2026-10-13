# LigandMPNN Colab

**An interactive Google Colab interface for ligand-aware protein sequence design using LigandMPNN.**

LigandMPNN is a deep-learning method for designing protein sequences conditioned on a protein backbone and, when appropriate, surrounding non-protein atoms. This notebook provides a beginner-friendly interface for running the official LigandMPNN implementation in Google Colab.

## Features

- Interactive configuration of protein structure, design chain, sequence count, temperature and random seed.
- Ligand atom context option for ligand-aware design.
- Explicit confirmation before model inference starts.
- Downloadable designed sequences in FASTA format.
- Generated backbone structures in PDB format.
- Results archive and run report for record keeping and reproducibility.

## Launch in Google Colab

**[Open LigandMPNN Colab](https://colab.research.google.com/github/selvaedwardraja/LigandMPNN-Colab/blob/main/LigandMPNN_Colab.ipynb)**

You will need a Google account. GPU availability depends on your Colab plan, current resource availability and session limits.

## Getting started

1. Open the notebook using the Colab link above.
2. Read the introduction and runtime instructions.
3. Run the setup cells in order. The notebook prepares the Python environment, retrieves the required model files and checks the installation.
4. Upload a compatible PDB structure or select a structure already available in the notebook environment.
5. Review the detected protein chains and select the chain to redesign.
6. Configure the design settings, including the number of sequences, sampling temperature and random seed.
7. Review the final configuration and resource requirements.
8. Tick the explicit confirmation checkbox and click **Start Design** when you are ready to run inference.
9. Download the FASTA sequences, designed backbone structures, results ZIP and run report using the available download controls.

**Important:** Running setup or interface cells should not start sequence design automatically. Model inference should begin only after the explicit confirmation and Start Design action.

## Input structure considerations

- Use a valid PDB structure containing the protein backbone for the chain you intend to redesign.
- Check the chain identifier and residue numbering before starting.
- For ligand-aware design, inspect the structure to ensure that the relevant ligand or other molecular context is represented correctly.
- Non-protein atoms, waters, ions, alternate conformations and unusual residue records may affect structure parsing and should be reviewed where relevant.
- The notebook's supported inputs and options depend on the installed version of the official LigandMPNN implementation.

## Understanding the outputs

| Output | Purpose |
|---|---|
| FASTA file | Contains the reference and/or designed protein sequences produced by the run. Check the headers to distinguish the records. |
| Backbone PDB files | Structure files generated for the designed sequences. |
| Results ZIP | Convenient archive of the available run outputs and report. |
| Run report | Records key settings, execution information and diagnostic log content. |
| Run log | Provides additional information for troubleshooting failed or incomplete runs. |

Exact output files depend on the selected settings and the results produced by the model.

## Reproducibility

For each run, record the input structure, selected chain, model checkpoint, sequence count, sampling temperature and random seed. Also retain the run report and log.

A fixed random seed helps make runs reproducible, but identical results are not guaranteed across different software versions, hardware, numerical environments or implementation changes. The input structure and model checkpoint should be retained alongside the results.

## Troubleshooting

**The setup or model download fails**
- Check the runtime's internet connection and rerun the relevant setup cell.
- Confirm that the required checkpoint file exists before launching a design.

**No protein chains are detected**
- Check that the uploaded file is a valid PDB structure and contains the expected protein atoms.
- Inspect the chain identifiers and residue records.

**The design run fails**
- Review the run status, output log and run report.
- Confirm that the selected input file, checkpoint and output directory are accessible.
- Check that the Colab runtime has not disconnected or exhausted its available resources.

**The download buttons do not work**
- Confirm that the run generated the requested files.
- Try the download control again and check whether the browser or Colab session blocked the download.

## Scientific limitations

LigandMPNN generates candidate protein sequences conditioned on structural information. A computationally generated sequence is not evidence that the protein will fold correctly, bind the intended target, retain ligand interactions or exhibit the desired biological activity.

Model scores and confidence-related metrics should not be interpreted as experimental binding affinity or proof of function. Designed candidates require appropriate structural assessment and experimental validation.

## Credits and references

This notebook builds on the official LigandMPNN implementation:

- **Official repository:** https://github.com/dauparas/LigandMPNN
- **Notebook repository:** https://github.com/selvaedwardraja/LigandMPNN-Colab

Please consult the official repository and associated publication for the original method, scientific background, licensing terms and citation requirements. Follow the applicable licenses and attribution requirements for the software, model checkpoints and any third-party resources used.

## Disclaimer

This notebook is provided as a research and educational interface. Users are responsible for checking the input structures, understanding the scientific limitations, managing their compute usage and validating designed candidates before drawing biological conclusions.
