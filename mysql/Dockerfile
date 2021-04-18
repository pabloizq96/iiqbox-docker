FROM mysql:5.7

#
# Sailpoint required settings
#
# 1) sql_mode setting must not contain 'STRICT_TRANS_TABLES'
# Required per SP docs
RUN sed -i 's~,STRICT_TRANS_TABLES~~' /etc/mysql/my.cnf && \
    sed -i 's~,STRICT_TRANS_TABLES~~' /etc/mysql/my.cnf && \
    echo "[mysqld]" >> /etc/mysql/my.cnf && \
    echo "default_time_zone = Europe/Madrid" >> /etc/mysql/my.cnf && \
    echo "innodb_large_prefix = 1" >> /etc/mysql/my.cnf && \
    echo "innodb_file_per_table = 1" >> /etc/mysql/my.cnf

# Recommended per SP docs
RUN echo "innodb_file_format = BARRACUDA" >> /etc/mysql/my.cnf && \
    echo "innodb_file_format_max = BARRACUDA" >> /etc/mysql/my.cnf && \
    echo "innodb_log_file_size = 64M" >> /etc/mysql/my.cnf

# Recommended by other users on Compass
RUN echo "max_allowed_packet = 256M" >> /etc/mysql/my.cnf && \
    echo "innodb_buffer_pool_size = 256M" >> /etc/mysql/my.cnf && \
    echo "innodb_log_buffer_size = 8M" >> /etc/mysql/my.cnf && \
    echo "innodb_lock_wait_timeout = 50" >> /etc/mysql/my.cnf && \
    echo "server-id=1" >> /etc/mysql/my.cnf && \
    echo "sql_mode=NO_ENGINE_SUBSTITUTION" >> /etc/mysql/my.cnf

