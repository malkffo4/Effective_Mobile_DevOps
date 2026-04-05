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