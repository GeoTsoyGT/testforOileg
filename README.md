# Oileg Data Exchange Repo

Репозиторий для обмена материалами на анализ:
- команда кладёт входные данные в `inbox/`
- Oileg обрабатывает и складывает результаты в `outbox/`
- обработанные/проблемные кейсы переносятся в `archive/`

## Структура
- `inbox/raw/` — входные файлы (CSV/XLSX/PDF/MD)
- `inbox/requests/` — постановка задачи (YAML)
- `outbox/reports/` — итоговые отчёты (MD)
- `outbox/tables/` — результирующие таблицы (CSV/XLSX)
- `archive/processed/` — закрытые кейсы
- `archive/failed/` — кейсы с ошибками/неполными данными
- `templates/` — шаблоны заявок
- `logs/` — журнал выполнений

## Быстрый старт для команды
1. Скопируйте `templates/request_template.yaml` в `inbox/requests/<task_id>.yaml`
2. Положите входные файлы в `inbox/raw/<task_id>/`
3. Закоммитьте и запушьте.
4. Уведомьте в Telegram: `@knc_agent_bot task_id=<task_id>`

## Нейминг
`task_id` формат:
`YYYYMMDD-<asset>-<short-topic>-v1`

Пример:
`20260223-vereisky-pvt-screen-v1`

## SLA формат ответа Oileg
- Техническая часть
- Экономическая часть
- Риски
- Практические рекомендации

Итоги по задаче будут в:
- `outbox/reports/<task_id>_report.md`
- `outbox/tables/<task_id>_*.csv`
