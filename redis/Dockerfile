# Используем официальный образ Redis
FROM redis:7.2.4

# Опционально: указываем порт, который будет открыт в контейнере
EXPOSE 6379

# Задаём команду для запуска Redis с настройками
# --appendonly yes включает AOF-логирование
# --requirepass ${REDIS_PASSWORD} использует переменную окружения для пароля
CMD ["redis-server", "--appendonly", "yes", "--requirepass", "${REDIS_PASSWORD}"]

# Настройка healthcheck
HEALTHCHECK --interval=10s --timeout=3s --retries=3 \
  CMD redis-cli --raw incr ping
