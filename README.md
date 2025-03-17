# Explorando os Recursos de IA Generativa com Copilot e OpenAI

Este projeto visa explorar os recursos de IA generativa, utilizando o poder do **Tesseract OCR** para o reconhecimento de texto em imagens. O código inclui a criação de pastas para armazenar imagens e resultados, processamento de OCR e armazenamento dos resultados extraídos.

## Estrutura do Projeto

O projeto é estruturado da seguinte forma:

- **inputs/**: Contém as imagens que serão processadas com OCR.
- **output/**: Armazena os arquivos de texto extraídos das imagens.
- **prompt-para-codigo.md**: Este arquivo contém uma coleção de prompts de IA que geraram códigos para as tarefas realizadas no projeto.
- **readme.md**: Arquivo de documentação do projeto.

## Funcionalidades

1. **Reconhecimento de Texto (OCR)**:
   Utiliza a biblioteca **Tesseract OCR** para extrair texto de imagens na pasta `inputs/` e salva o texto extraído na pasta `output/`.

2. **Criação Automática de Pastas**:
   O script cria automaticamente as pastas `inputs/` e `output/` para organizar as imagens e resultados.

## Como Usar

### Pré-requisitos

1. **Instalar as Dependências**:
   O projeto utiliza as bibliotecas `pytesseract` e `Pillow` para realizar o OCR. Para instalar as dependências, execute o seguinte comando:

   ```bash
   pip install pytesseract pillow
