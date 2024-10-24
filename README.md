# Advanced-Image-and-Data-Retrieval-System-Using-ChromaDB (Multimedia Search Engine with ChromaDB)

A powerful multimedia search engine that uses ChromaDB for vector storage and CLIP for generating embeddings. This application supports both text-to-image and image-to-image search capabilities with an intuitive web interface built using Streamlit.

## 🌟 Features

- **Dual Search Modes**
  - Text-based image search
  - Image-based similarity search
  - Vector similarity-based retrieval

- **Efficient Data Management**
  - Single image upload with custom captions
  - Batch import functionality
  - Integration with popular computer vision datasets (CIFAR10, CIFAR100, FashionMNIST, STL10)
  - Visual database management interface

- **Performance Optimizations**
  - Built-in caching system for faster repeated queries
  - Persistent storage using ChromaDB
  - Efficient vector embeddings using CLIP model

## 🛠️ Technology Stack

- **Backend**
  - ChromaDB: Vector database for efficient similarity search
  - CLIP: Neural network for generating image and text embeddings
  - PyTorch: Deep learning framework
  - Python 3.8+

- **Frontend**
  - Streamlit: Web interface
  - PIL: Image processing
  - Torchvision: Dataset management

## 📋 Prerequisites

- Python 3.8 or higher
- CUDA-capable GPU (optional, but recommended for better performance)
- At least 4GB of RAM
- 500MB of free disk space for the base system (more needed for storing images)

## ⚡ Installation

1. Clone the repository:
```bash
git clone https://github.com/abojotemi/Advanced-Image-and-Data-Retrieval-System-Using-ChromaDB.git
cd Advanced-Image-and-Data-Retrieval-System-Using-ChromaDB

```

2. Create and activate a virtual environment (optional but recommended):
```bash
python -m venv venv
source venv/bin/activate  # On Windows, use: venv\Scripts\activate
```

3. Install required packages:
```bash
pip install -r requirements.txt
```

## 🚀 Usage

1. Start the application:
```bash
streamlit run app.py
```

2. Access the web interface at `http://localhost:8501`

### Search Interface

The application provides two main search methods:

1. **Text Search**
   - Enter descriptive text to find matching images
   - Results are ranked by similarity to the text query

2. **Image Search**
   - Upload an image to find similar images
   - View results sorted by visual similarity

### Database Management

The system offers multiple ways to populate the database:

1. **Single Upload**
   - Upload individual images
   - Add custom captions
   - Preview before adding to database

2. **Batch Import**
   - Import multiple images from a directory
   - Optional CSV file for bulk caption assignment
   - Progress tracking for large imports

3. **Dataset Import**
   - Import from standard computer vision datasets
   - Configurable sample size
   - Automatic caption generation based on classes

## 💾 Data Storage

- Images are stored in the `stored_images/` directory
- Vector embeddings are maintained by ChromaDB in `chroma_db/`
- Cache data is maintained in memory during runtime

## ⚙️ System Architecture

The application is structured into several key components:

1. **Main Application (`app.py`)**
   - Initializes models and databases
   - Manages the web interface
   - Coordinates between components

2. **Search Interface (`search_interface.py`)**
   - Handles user queries
   - Manages search operations
   - Displays results

3. **Database Manager (`database_manager.py`)**
   - Manages image and caption storage
   - Handles data import operations
   - Provides database viewing capabilities

4. **Cache System (`cache.py`)**
   - Implements LRU caching
   - Optimizes repeated queries
   - Manages cache invalidation

## 🔍 Search Pipeline

1. Query Processing
   - Text queries are tokenized using CLIP
   - Images are preprocessed to 224x224 pixels
   - Embeddings are generated using the CLIP model

2. Vector Search
   - Query embeddings are compared against stored vectors
   - ChromaDB performs efficient similarity search
   - Top matches are retrieved based on vector distance

3. Result Presentation
   - Matching images are displayed with captions
   - Results are sorted by similarity score
   - File paths and metadata are shown for reference

## 🛡️ Error Handling

The application includes comprehensive error handling for:
- Invalid file formats
- Missing files
- Database connection issues
- Model loading failures
- Memory constraints
