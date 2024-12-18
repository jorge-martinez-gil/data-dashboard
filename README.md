
# Data Analysis and Knowledge Graph Application

This project is a comprehensive data analysis and visualization dashboard, integrated with knowledge graph functionality. It allows users to upload datasets, perform correlation analysis, apply inference rules, and visualize relationships through an interactive RDF-based knowledge graph.

A live demo of this component can be found at: [https://airedgio-dashboard.streamlit.app/](https://airedgio-dashboard.streamlit.app/)

![Screenshot](screen.png)

## Features

- **Data Upload and Preprocessing**:  
  - Upload datasets via file input or URL.  
  - Handle missing values using various imputation methods.  
  - Encode categorical variables and coerce numeric data.

- **Correlation Analysis**:  
  - Compute Pearson and Spearman correlations, as well as Euclidean similarity.  
  - User-defined thresholds for filtering significant relationships.

- **Knowledge Graph Creation**:  
  - Automatically generate RDF graphs representing significant correlations.  
  - Define relationships using user-specified thresholds.

- **Inference Rules**:  
  - Input custom IF-THEN rules to add inferred relationships to the RDF graph.

- **Visualization**:  
  - Visualize correlations using interactive Plotly subplots.  
  - Display the knowledge graph as a network with customizable aesthetics.

- **SPARQL Querying**:  
  - Query the RDF graph using SPARQL with a user-friendly interface.  

## Technologies Used

- **Backend**:  
  - `pandas`, `numpy`, and `scipy` for data handling and analysis.  
  - `rdflib` for RDF graph management.  
  - `sklearn.preprocessing` for data preprocessing.  

- **Visualization**:  
  - `plotly` for dynamic data visualization.  
  - `pyvis` for RDF graph network visualization.  

- **Frontend**:  
  - `streamlit` for an interactive web interface.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo-name.git
   cd your-repo-name
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the application:
   ```bash
   streamlit run app5.py
   ```

## Usage

1. **Upload a Dataset**:  
   Upload a `.csv` file for analysis.

2. **Select Columns**:  
   Choose pairs of columns for correlation analysis.

3. **Set Thresholds**:  
   Adjust thresholds for Pearson, Spearman, and Euclidean similarity using sidebar sliders.

4. **Analyze Data**:  
   View correlation visualizations and an interactive knowledge graph.

5. **Apply Inference Rules**:  
   Enter custom rules in the IF-THEN format to infer new relationships.

6. **SPARQL Queries**:  
   Use the SPARQL query interface to explore the RDF graph.

## Examples

### Sample Rule
```
IF _pearson > 0.7 AND _spearman > 0.7 THEN _strongCorrelation
```

### Sample SPARQL Query
```sparql
SELECT ?subject ?object
WHERE {
  ?subject <https://www.ai-redgio.eu/_pearson> ?object .
}
```

## Project Structure

- `app5.py`: Main Streamlit application script.
- `requirements.txt`: List of dependencies.
- `knowledge_graph.html`: Generated visualization for the RDF graph.

## Citation
For academic use, please refer to our work:

```
@article{martinez2023examining,
  title={Examining the Adoption of Knowledge Graphs in the Manufacturing Industry: A Comprehensive Review},
  author={Martinez-Gil, Jorge and Hoch, Thomas and Pichler, Mario and Heinzl, Bernhard and Moser, Bernhard and Kurniawan, Kabul and Kiesling, Elmar and Krause, Franz},
  journal={Artificial Intelligence in Manufacturing: Enabling Intelligent, Flexible and Cost-Effective Production Through AI},
  pages={55--70},
  year={2023},
  publisher={Springer Nature Switzerland Cham}
}
```

## License

This project is licensed under the MIT License. 

## Acknowledgement
This work is performed in the context of the AI REDGIO 5.0 “Regions and (E)DIHs alliance for AI-at-the-Edge adoption by European Industry 5.0 Manufacturing SMEs” EU Innovation Action Project under Grant Agreement No 101092069.
