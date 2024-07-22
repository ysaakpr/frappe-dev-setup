Follow https://github.com/frappe/frappe_docker/blob/main/docs/development.md

```
bench init --skip-redis-config-generation frappe-bench
```

```
bench set-config -g db_host mariadb
bench set-config -g redis_cache redis://redis-cache:6379
bench set-config -g redis_queue redis://redis-queue:6379
bench set-config -g redis_socketio redis://redis-queue:6379
```
```
bench new-site --mariadb-root-password 123 --admin-password admin --mariadb-user-host-login-scope='%' krp.localhost
```
```
bench --site krp.localhost set-config developer_mode 1
bench --site krp.localhost clear-cache
```
