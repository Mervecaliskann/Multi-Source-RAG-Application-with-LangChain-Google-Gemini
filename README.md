# Multi-Source-RAG-Application-with-LangChain-Google-Gemini
This project demonstrates a powerful Retrieval-Augmented Generation (RAG) application built using Python, LangChain, and Streamlit. It enhances the capabilities of Google's Gemini LLM by providing it with real-time, external context from web pages (URLs) and PDF documents.

The application allows users to ask questions about the content of a specific URL or a PDF file, showcasing the difference between a standard LLM response and a context-aware RAG response.

# LangChain & Google Gemini ile Çok Kaynaklı RAG Uygulaması

Bu proje, Python, LangChain ve Streamlit kullanılarak oluşturulmuş güçlü bir Geri-Getirme Destekli Üretim (Retrieval-Augmented Generation - RAG) uygulamasını sergilemektedir. Google'ın Gemini dil modelinin yeteneklerini, web sayfalarından (URL) ve PDF dokümanlarından alınan gerçek zamanlı, harici bağlamlarla zenginleştirir.

Uygulama, kullanıcıların belirli bir URL'nin veya PDF dosyasının içeriği hakkında sorular sormasına olanak tanır ve standart bir dil modeli yanıtı ile bağlama duyarlı bir RAG yanıtı arasındaki farkı gözler önüne serer.

# Key Features

**Dual Data Sources:** Processes information from both live web pages (URLs) and local PDF files.

**RAG vs. Standard LLM:** Provides a side-by-side comparison of answers generated with and without external context, clearly demonstrating the power of RAG in preventing hallucinations and providing factual responses.

**Multi-Model Integration:** Utilizes **Google Gemini (gemini-1.5-flash-latest)** for text generation and **OpenAI's Embeddings** for text vectorization, showcasing flexibility in using different AI services.

**Efficient Vector Search:** Employs **FAISS (Facebook AI Similarity Search)** for fast and efficient in-memory similarity searches on document vectors.

**Interactive Web UI:** A user-friendly interface built with **Streamlit** allows for easy interaction with the system.

# 🛠️ Tech Stack & Architecture

This project is built on a modern Generative AI stack:

* Framework: LangChain
* LLM (Generator): Google Gemini
* Embeddings Model: OpenAI
* Vector Store: FAISS
* UI: Streamlit
* Document Loaders: WebBaseLoader, PyPDFLoader

# How It Works (RAG Pipeline)

1. Load: The application loads data from the user-provided URL or PDF file.
2. Split: The raw text is split into smaller, manageable chunks using 3. RecursiveCharacterTextSplitter.
3. Embed: Each chunk is converted into a numerical vector using OpenAI's embedding model.
4. Store: These vectors are stored in a FAISS in-memory vector database.
5. Retrieve: When a user asks a question, the application embeds the query and uses FAISS to find the most semantically similar document chunks (the "context").
6. Generate: The original prompt and the retrieved context are passed to the Gemini LLM. The model then generates a final, context-aware answer based only on the provided information.

# Setup and Usage

## Create and Activate a Virtual Environment
```
# Windows
python -m venv venv
venv\Scripts\activate

# macOS / Linux
python3 -m venv venv
source venv/bin/activate
```

## Set Up Environment Variables

* Create a .env file in the root directory of the project
* Open the .env file and add your API keys from OpenAI and Google AI Studio.

## Prepare the Data Directory (for PDF)

The application expects uploaded PDFs to be temporarily handled. For a seamless experience with the provided code structure (filepath=f"./data/{selected_file.name}"), ensure a data folder exists in the root directory. Note: Streamlit's file uploader handles this in memory, but having a data folder is good practice if you wish to save files permanently.

## Run the Streamlit Application

```python
streamlit run app.py
```

Open your web browser and navigate to the local URL provided by Streamlit (usually http://localhost:8501).


TR

# Öne Çıkan Özellikler

**İkili Veri Kaynağı:** Hem canlı web sayfalarından (URL) hem de yerel PDF dosyalarından gelen bilgileri işler.
**RAG ve Standart LLM Karşılaştırması:** Harici bağlam kullanılarak ve kullanılmadan üretilen yanıtları yan yana karşılaştırarak, RAG'in halüsinasyonları önlemedeki ve gerçeğe dayalı yanıtlar vermedeki gücünü net bir şekilde gösterir.
**Çoklu Model Entegrasyonu:** Metin üretimi için Google Gemini (gemini-1.5-flash-latest) ve metin vektörleştirmesi için OpenAI Embeddings kullanarak farklı yapay zeka servislerini bir arada kullanma esnekliğini sergiler.
**Etkin Vektör Araması:** Doküman vektörleri üzerinde hızlı ve verimli bellek-içi benzerlik aramaları için FAISS (Facebook AI Similarity Search) kullanır.
**Etkileşimli Web Arayüzü:** Streamlit ile oluşturulmuş kullanıcı dostu bir arayüz, sistemle kolay etkileşim sağlar.

# Kurulum ve Çalıştırma

## Sanal Ortam Oluşturun ve Aktifleştirin
```
# Windows
python -m venv venv
venv\Scripts\activate

# macOS / Linux
python3 -m venv venv
source venv/bin/activate
```

## Ortam Değişkenlerini Ayarlayın

Projenin kök dizininde, bir .env dosyası oluşturun.

.env dosyasını açın ve OpenAI ve Google AI Studio'dan aldığınız API anahtarlarınızı ekleyin.

## Veri Klasörünü Hazırlayın (PDF için)

Uygulama, yüklenen PDF'lerin geçici olarak işlenmesini bekler. Mevcut kod yapısıyla (filepath=f"./data/{selected_file.name}") sorunsuz bir deneyim için kök dizinde bir data klasörünün bulunduğundan emin olun. Not: Streamlit'in dosya yükleyicisi bu işlemi bellekte yönetir, ancak dosyaları kalıcı olarak kaydetmek isterseniz bir data klasörüne sahip olmak iyi bir pratiktir.

## Streamlit Uygulamasını Çalıştırın

```python
streamlit run app.py
```
Web tarayıcınızı açın ve Streamlit tarafından sağlanan yerel URL'ye gidin (genellikle http://localhost:8501).

![Uygulama Arayüzü](https://github.com/Mervecaliskann/Multi-Source-RAG-Application-with-LangChain-Google-Gemini/blob/main/langchain-bellek-genisletme-url-pdf-Ekran%20g%C3%B6r%C3%BCnt%C3%BCs%C3%BC%202025-08-06%20232519.png)


