# AI Market Research Agent

AI-агент для автоматического ресёрча AI-рынка РФ на базе n8n.

## Что делает

Принимает тему от пользователя → разбивает на подвопросы →
вызывает поиск в интернете → анализирует результаты →
выдаёт структурированный отчёт.

## Стек

- **n8n** — оркестрация агента
- **Groq (Llama)** — LLM
- **Tavily** — поиск, оптимизированный под LLM

## Архитектура

ReAct-паттерн:
1. Chat Trigger принимает запрос
2. AI Agent (LLM) решает, что искать
3. HTTP Request Tool вызывает Tavily API
4. LLM читает результаты и формирует отчёт

## Как запустить

1. Развернуть n8n (Railway / Render / self-hosted)
2. Импортировать `workflow.json`
3. Создать credentials:
   - Groq API key: console.groq.com
   - Tavily API key: tavily.com
4. Заменить `YOUR_TAVILY_API_KEY` в HTTP Request ноде на свой ключ
5. Открыть Chat и задать тему

## Примеры запросов

- `Обзор Evolution AI Factory от Cloud.ru`
- `Сравни Cloud.ru, YandexGPT и SberGPT`
- `Тренды AI-агентов в России 2025`
