# Automação Pipeline do meu canal dark no youtube Nexo Roxo

Uma pipeline automatizada de ponta a ponta para a criação, edição e publicação de conteúdo "Dark" para o YouTube usando Python. O sistema gerencia todo o ciclo de vida do vídeo: desde a geração de roteiro via IA, narração, busca de *B-roll* (cenas complementares), edição com legendas automatizadas até o upload e configuração da thumbnail.

### Acesse: https://www.youtube.com/@NexoRoxo

## 🛠️ Tecnologias e Stack Tecnológica

O projeto foi construído utilizando um ecossistema robusto de bibliotecas Python para garantir performance e qualidade:

| Etapa | Ferramenta / API | Motivo da Escolha |
| :--- | :--- | :--- |
| **Roteiro & Lógica** | OpenAI (GPT-4) / Groq | Processamento de linguagem natural rápido e estruturado (JSON). |
| **Revisão/controle de qualidade**|gemini model="gemini-3.5-flash"|traz pontos de melhoria no roteiro.|
| **Narração (TTS)** | `edge-tts` | Vozes neurais de alta qualidade, naturais e totalmente gratuitas. |
| **Imagens/Thumb** | Stability + `Pillow` +opencv + numpy | Geração de assets via modelos e manipulação gráfica via `Pillow`. |
| **animações** | runwayml,Lottifiles,popvidAI, vmakeAI + openCV + Numpy | Obter animações específicas e tratar. |
| **B-Roll (Vídeos)** | Pexels API | Acesso a banco de vídeos em alta resolução (4K/HD). |
| **Edição** | `MoviePy` | Montagem, renderização e composição de trilha sonora/vídeo. |
| **Infra/Env** | `python-dotenv` | Gerenciamento seguro de variáveis de ambiente. |
| **Distribuição** | YouTube Data API v3 | Automação completa de publicação. |

## 🗂 Estrutura do Projeto

```text
CANAL_DARK/
├── assets/                 # Recursos estáticos
│   ├── efeitos_sonoros/    # Transições (SFX)
│   ├── animacoes/          # animacoes de like e se inscrever e o nexo (site runwayml)
│   ├── musicas/            # Trilha sonora
│   ├── estetica_canal/       
│   └── fonte_thumb/        # Fontes para thumbnails
├── backup/                 # pasta com videos para emergencia e o prompt antigo para groq
├── config/
│   └── config.py           # Gerenciamento de variáveis
├── services/               # Módulos de negócio
│   ├── audio_service.py    # Integração com edge-tts
│   ├── gemini_revisor_service.py   # Geração de revisão e controle qualidade do roteiro
│   ├── imagem_service.py   # Geração via Stability
│   ├── pexels_service.py   # Download de vídeos B-roll
│   ├── scripts_service.py  # Integração com LLMs
│   ├── thumb_service.py    # Manipulação gráfica (Pillow)
│   ├── tratar_animacoes.py # Manipulação dos videos com opencv e numpy
│   ├── video_service.py    # Edição (MoviePy)
│   └── youtube_service.py  # Automação de upload/metadata
├── temp/                   # Área de trabalho (temporária)
├── .env                    # Variáveis de ambiente
├── main.py                 # Orquestrador da pipeline
├── requirements.txt        # Dependências do projeto
└── .gitignore
'''
