## ВКР Омельченко Максим Александрович, Коринецкая Юлия Владимировна
Тема: Разработка сервиса формализации разделов электронной медицинской карты по частично структурированным историям болезни.

Научный руководитель: Грибова Валерия Викторовна

Группа: Б9121-09.03.04прогин

## Описание системы
Система предназначена для формализации частично-структурированных электронных медицинских книжек в формате html. И генерации, на основе формализованных данных, инфоресурса для платформы [Iacpaas](https://iacpaas.dvo.ru/). [Видео демонстрация](https://drive.google.com/file/d/1vAz3aKklntOHdfyw21zy_4JGCilB40xI/view?usp=sharing).

## Требования для запуска
- Видеокарта с >= 6gb vram
- 9gb на жестком диске
- [ubuntu 22.0.4.5](https://releases.ubuntu.com/jammy/)
- [cuda>=11.8](https://developer.nvidia.com/cuda-11-8-0-download-archive)
- [Пакетный менеджер uv](https://docs.astral.sh/uv/getting-started/installation/)
- Аккаунт на [hugging face](https://huggingface.co/settings/tokens) и выпущенный Access Token


## Запуск 

1. Сохранить Access Token c hugging face в переменной окружения HF_TOKEN

    `export HF_TOKEN=your_access_token_here`

2. Запустить сервер и дождаться загрузки llm модели (будет скачена llm размером 9gb)

    `uv run llm/server/server.py llm/server/configs/gemma-3-4b-it.json`

3. Запустить веб-интерфйес

    `uv run -m streamlit run admin/main.py`
4. Веб интерфес теперь доступен по `http://localhost:8501/`. 

    Примеры электронных книжек для загрузки можно найти в исходном коде в директории `extractor/samples`.