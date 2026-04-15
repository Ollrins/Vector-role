# Ansible Role: Vector

Устанавливает и настраивает Vector для сбора логов.

## Требования
- Rocky Linux / RHEL 8+
- Ansible 2.9+

## Переменные
| Параметр | Описание | Значение по умолчанию |
|----------|----------|----------------------|
| vector_config_dir | Директория конфигов | `/etc/vector` |
| vector_config_file | Имя файла конфига | `vector.toml` |
| vector_log_sources | Источники логов | `['/var/log/clickhouse-server/*.log']` |
| vector_output_path | Путь для сохранения логов | `/var/log/vector/collected.log` |

## Пример использования
```yaml
- hosts: vector
  roles:
    - role: vector
      vars:
        vector_output_path: "/var/log/custom/collected.log"
