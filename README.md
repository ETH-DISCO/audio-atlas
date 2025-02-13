
# Audio Atlas

Audio Atlas is a web application designed to visualize audio data using text-audio embeddings. It allows users to explore large-scale datasets of audio samples, such as musical genres or custom datasets, in an intuitive 2D graph format. This tool leverages contrastive learning techniques to map both textual and audio queries into a shared vector space for efficient searching and visualization.

## Features

- **Interactive Audio Data Visualization**: Audio samples are represented as individual nodes in a 2D plane, enabling users to explore data based on proximity, which reflects audio similarity.
- **Multimodal Search**: Users can search datasets using either text or audio inputs. Text descriptions and audio samples are embedded into the same vector space for seamless querying.
- **Real-Time Audio Playback**: Preview audio samples directly from the results.
- **Multiple Dataset Support**: Import and visualize multiple datasets simultaneously. Easily add custom datasets with a streamlined import process.
- **Interactive Graph**: Use zoom and click functions to explore nodes in detail, highlight categories, and view metadata for each audio sample.

## Technologies Used

- **Contrastive Learning**: The system uses Contrastive Language-Audio Pretraining (CLAP) to model text and audio data into the same vector space.
- **Milvus Vector Database**: Handles the vector embeddings for efficient similarity search.
- **WebGL**: Used for rendering large datasets on the browser with smooth zoom and interactive functionalities, powered by the Deepscatter library.
- **t-SNE**: High-dimensional audio data is reduced to 2D using t-distributed stochastic neighbor embedding for visualization.
- **Docker**: The application is containerized, making it easily deployable across environments.

## Installation

### Prerequisites

- Docker and Docker Compose
- Python 3.8+
- Node.js

### Steps

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/audio-atlas.git
   cd audio-atlas
   ```

2. Install dependencies and build the frontend:

   ```bash
   cd frontend
   npm install
   ```
3. Install dependencies and build deepscatter:
   ```bash
   cd deepscatter
   npm install
   ```
   
4. Run the application using Docker Compose:

   ```bash
   docker-compose up --build -d
   ```

4. Access the web app at `http://localhost:3000`.

## Dataset Import

To add a new dataset, configure the `config.json` file with the following details:

- `DATASET`: Link to the dataset.
- `DATASET_NAME`: Collection name in Milvus.
- `EMBEDDING_FIELD`: Name of the embedding field.
- `MODEL`: The model used for processing.

Run the provided script to process and import the dataset:

```bash
bash import_dataset.sh
```

## Usage

1. **Search**: Enter a text query or upload an audio file to perform a search. The system will retrieve the most similar audio samples from the selected dataset.
2. **Dataset Selection**: Choose from available datasets via the dropdown menu.
3. **Graph Interaction**: Zoom into clusters of audio samples and click on nodes to view more information or listen to audio previews.

## Contributors

- Uzeyir Valizada ([uvalizada@ethz.ch](mailto:uvalizada@ethz.ch))
- Luca Lanzendörfer ([lanzendoerfer@ethz.ch](mailto:lanzendoerfer@ethz.ch))
- Florian Grötschla ([fgroetschla@ethz.ch](mailto:fgroetschla@ethz.ch))

## License

This project is licensed under the MIT License.
