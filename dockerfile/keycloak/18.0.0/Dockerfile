# verificar versões em https://quay.io/repository/keycloak/keycloak?tab=tags
FROM quay.io/keycloak/keycloak:18.0.0 as builder

# Features adicionais para habilitar
ARG KC_FEATURES=account2,impersonation,admin2,token-exchange,client-secret-rotation,recovery-codes
# Vendor do banco de dados que vai ser utilizado, mysql, postgres
ARG KC_DB=mysql
# jdbc:mysql://hostdomysql:porta/nomedobanco
ARG KC_DB_URL=jdbc:mysql://mysql_keycloak:3306/keycloak
# Usuário do banco de dados
ARG KC_DB_USERNAME=keycloak
# Senha do banco de dados
ARG KC_DB_PASSWORD=keycloak
# Hostname do keycloak
ARG KC_HOSTNAME=keycloak
# Usuário admin inicial do keycloak
ARG KEYCLOAK_ADMIN=admin
# Senha do usuário admin inicial do keycloak
ARG KEYCLOAK_ADMIN_PASSWORD=admin


ENV KC_HEALTH_ENABLED=true
ENV KC_METRICS_ENABLED=true
ENV KC_FEATURES=${KC_FEATURES}
ENV KC_DB=${KC_DB}
ENV KC_DB_URL=${KC_DB_URL}
ENV KC_DB_USERNAME=${KC_DB_USERNAME}
ENV KC_DB_PASSWORD=${KC_DB_PASSWORD}
ENV KC_HOSTNAME=${KC_HOSTNAME}
ENV KEYCLOAK_ADMIN=${KEYCLOAK_ADMIN}
ENV KEYCLOAK_ADMIN_PASSWORD=${KEYCLOAK_ADMIN_PASSWORD}
ENV KC_HOSTNAME_STRICT=false
ENV KC_HTTP_ENABLED=true

# custom provider
RUN curl -sL https://github.com/aerogear/keycloak-metrics-spi/releases/download/2.5.3/keycloak-metrics-spi-2.5.3.jar -o /opt/keycloak/providers/keycloak-metrics-spi-2.5.3.jar
RUN /opt/keycloak/bin/kc.sh build

FROM quay.io/keycloak/keycloak:18.0.0
COPY --from=builder /opt/keycloak/ /opt/keycloak/
WORKDIR /opt/keycloak

ENTRYPOINT ["/opt/keycloak/bin/kc.sh", "start"]