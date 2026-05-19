### Запуск
```bash
cd Effective_Mobile_DevOps
```

```bash
docker-compose up --build -d
```
#### Потушить
```bash
docker-compose down -v
```

### Проверка healthcheck
```bash
curl http://localhost/health
```

###### Ожидаемый ответ
"Hello from Effective Mobile!"

### Описание работы
##### Архитектура
- nginx принимает HTTP-запросы на порт 80
- проксирует их в backend
- backend отвечает клиенту
##### Схема взаимодействия
[ клиент ]
     ↓
[ nginx :80 ]
     ↓
[ backend :8080 ]


Что можно улучшить:
1) Отсутствует .dockerignore для backend и nginx
2) Отсутствует заголовок X-Forwarded-Proto в nginx.conf
3) Не указана restart policy в docker-compose
4) Нет event {} worker_connections в nginx.conf
5) healthcheck для nginx проверяет backend, а не сам nginx
6) В backend используется HTTPServer без логирования
