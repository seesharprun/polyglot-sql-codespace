FROM mcr.microsoft.com/mssql/server:2022-CU5-ubuntu-20.04

ENV ACCEPT_EULA=Y
ENV MSSQL_SA_PASSWORD=P@ssw.rd

RUN mkdir -p /opt/scripts

COPY seed.sql /opt/scripts

RUN ( /opt/mssql/bin/sqlservr --accept-eula & ) | grep -q "Service Broker manager has started" \
    && /opt/mssql-tools/bin/sqlcmd -S localhost -U SA -P 'P@ssw.rd' -i /opt/scripts/seed.sql