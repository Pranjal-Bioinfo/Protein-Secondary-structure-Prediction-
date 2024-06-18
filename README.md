
# Protein Secondary Structure Prediction

This project involves predicting the secondary structure of proteins using a deep learning model. The model is trained to classify the secondary structure of each amino acid in a protein sequence into three categories: Helix (H), Sheet (E), and Coil (C).

## Project Overview

Protein secondary structure prediction is a critical task in bioinformatics, as it provides valuable insights into protein function and stability. This project leverages a Convolutional Neural Network (CNN) to make accurate predictions based on protein sequences.

## Features

- **Convolutional Neural Network (CNN)**: Utilizes CNNs to capture patterns in protein sequences.
- **Three-state Secondary Structure**: Predicts secondary structures as Helix (H), Sheet (E), or Coil (C).
- **Customizable**: Easily adaptable to new datasets or extended to more states or features.
- **Model Persistence**: Saves the trained model in Keras native format for easy reuse.

## Dataset

The dataset used in this project includes protein sequences and their corresponding secondary structures. It consists of the following columns:

- `pdb_id`: PDB ID of the protein.
- `chain_code`: Chain code of the peptide.
- `seq`: Sequence of amino acids.
- `sst8`: Eight-state (Q8) secondary structure (not used in this project).
- `sst3`: Three-state (Q3) secondary structure.
- `len`: Length of the peptide.
- `has_nonstd_aa`: Indicates the presence of non-standard amino acids, marked with `*`.

Non-standard amino acids are removed to ensure consistency.

## Installation

1. **Clone the Repository**:

    ```bash
    git clone https://github.com/yourusername/protein-secondary-structure-prediction.git
    cd protein-secondary-structure-prediction
    ```

2. **Create a Virtual Environment** (optional but recommended):

    ```bash
    python -m venv env
    source env/bin/activate  # On Windows use `env\Scripts\activate`
    ```

3. **Install Dependencies**:

    ```bash
    pip install -r requirements.txt
    ```

    If you don't have a `requirements.txt` file, use the following command to install the necessary packages:

    ```bash
    pip install numpy pandas tensorflow scikit-learn matplotlib
    ```

## Usage

1. **Prepare the Dataset**:
   
    Ensure the dataset (`protein_sequences.csv`) is placed in the `data/` directory. The project uses a preprocessed dataset, so no additional preprocessing is required.

2. **Run the Training Script**:

    You can train the model by running the `train_model.ipynb` notebook or executing the `train_model.py` script:

    ```bash
    python train_model.py
    ```

    The script will train the model and save it as `protein_secondary_structure_model.keras` in the root directory.

3. **Predict Secondary Structure**:

    To predict the secondary structure of a new protein sequence, you can use the `predict_secondary_structure.py` script or run the `predict_secondary_structure.ipynb` notebook:

    ```bash
    python predict_secondary_structure.py
    ```

    Example usage in Python:

    ```python
    from predict_secondary_structure import predict_structure

    # Example protein sequence
    new_sequence = "ACDEFGHIKLMNPQRSTVWY"

    # Predict secondary structure
    predicted_structure = predict_structure(new_sequence)
    print(f'Predicted secondary structure: {predicted_structure}')
    ```

    The output will be a string representing the secondary structure, e.g., "CCCCCHHHHHHHCCCEEEEE".

## File Structure

- `data/`: Directory containing the dataset.
- `train_model.ipynb`: Jupyter notebook for training the model.
- `train_model.py`: Python script for training the model.
- `predict_secondary_structure.ipynb`: Jupyter notebook for predicting secondary structures.
- `predict_secondary_structure.py`: Python script for predicting secondary structures.
- `protein_secondary_structure_model.keras`: Saved Keras model.
- `README.md`: This readme file.

## Contributing

Contributions are welcome! Please fork the repository and create a pull request with your changes. Ensure your code adheres to the project’s coding standards and is well-documented.

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.

## Acknowledgments

- The dataset used in this project was obtained from [data source].
- Inspiration for the project structure was drawn from various bioinformatics resources and tutorials.

## Contact

For any questions or feedback, please open an issue in the repository or contact the project maintainers at [email@example.com].

---

Feel free to adapt and extend this project for your research or educational purposes. Happy coding!

