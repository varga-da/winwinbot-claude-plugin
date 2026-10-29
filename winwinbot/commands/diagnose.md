---
description: Разобрать, почему просели подписки, вовлечённость или продажи, и что с этим делать
argument-hint: "[что просело и за какой период]"
---

Задача: диагностика просадки бота WinWinBot. Симптом: $ARGUMENTS

Работай по скиллу `winwinbot`, деревом замеров, а не догадкой:

1. Пачкой: `get_bot_overview` за текущий и прошлый период, `get_bot_health`, `get_playbook` по разделам analytics и funnels.
2. Что просело — трафик, вовлечённость или конверсия:
   - трафик — `get_audience_stats`, `get_traffic_sources`, `get_distribution` по месяцу подписки и utm_source;
   - вовлечённость — `get_content_engagement`, `get_scenario_stats` (не остановился ли сценарий), `get_message_stats` по последним рассылкам;
   - конверсия — `get_payment_stats`, `simulate_funnel` от подписки до оплаты, `get_payment_webhook_logs` при ошибках оплаты.
3. Что меняли недавно — `get_edit_impact`.
4. Ответ: что просело (цифра), где место потерь (этап и цифра), вероятная причина только под цифрой, 1–3 действия с метрикой проверки. Нет нужной цифры — так и скажи.
