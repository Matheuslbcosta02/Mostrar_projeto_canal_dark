# Automação Pipeline do meu canal dark no youtube Nexo Roxo

Uma pipeline automatizada de ponta a ponta para a criação, edição e publicação de conteúdo "Dark" para o YouTube. O sistema gerencia todo o ciclo de vida do vídeo: desde a geração de roteiro via IA, narração, busca de *B-roll* (cenas complementares), edição com legendas automatizadas até o upload e configuração da thumbnail.

### Acesse: https://www.youtube.com/@NexoRoxo

## 🛠️ Tecnologias e Stack Tecnológica

O projeto foi construído utilizando um ecossistema robusto de bibliotecas Python para garantir performance e qualidade:

| Etapa | Ferramenta / API | Motivo da Escolha |
| :--- | :--- | :--- |
| **Roteiro & Lógica** | OpenAI (GPT-4) / Groq | Processamento de linguagem natural rápido e estruturado (JSON). |
| **Narração (TTS)** | `edge-tts` | Vozes neurais de alta qualidade, naturais e totalmente gratuitas. |
| **Imagens/Thumb** | HuggingFace + `Pillow` | Geração de assets via modelos e manipulação gráfica via `Pillow`. |
| **B-Roll (Vídeos)** | Pexels API | Acesso a banco de vídeos em alta resolução (4K/HD). |
| **Edição** | `MoviePy` | Montagem, renderização e composição de trilha sonora/vídeo. |
| **Infra/Env** | `python-dotenv` | Gerenciamento seguro de variáveis de ambiente. |
| **Distribuição** | YouTube Data API v3 | Automação completa de publicação. |

## 🗂 Estrutura do Projeto

```text
CANAL_DARK/
├── assets/                 # Recursos estáticos
│   ├── efeitos_sonoros/    # Trilha sonora
│   ├── alegre/             # Trilha sonora
│   ├── dramatico/          # Trilha sonora
│   ├── estetica_canal/     
│   ├── inspirador/         # Trilha sonora
│   ├── raiva/              # Trilha sonora
│   ├── fonte_thumb/        # Fontes para thumbnails
│   ├── efeitos_sonoros/    # Transições (SFX)
│   └── sombrio/            # Trilha sonora
├── config/
│   └── config.py           # Gerenciamento de variáveis
├── services/               # Módulos de negócio
│   ├── audio_service.py    # Integração com edge-tts
│   ├── imagem_service.py   # Geração via HuggingFace
│   ├── pexels_service.py   # Download de vídeos B-roll
│   ├── scripts_service.py  # Integração com LLMs
│   ├── thumb_service.py    # Manipulação gráfica (Pillow)
│   ├── video_service.py    # Edição (MoviePy)
│   └── youtube_service.py  # Automação de upload/metadata
├── temp/                   # Área de trabalho (temporária)
├── .env                    # Variáveis de ambiente
├── main.py                 # Orquestrador da pipeline
├── requirements.txt        # Dependências do projeto
└── .gitignore
'''
