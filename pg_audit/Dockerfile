from ubuntu
copy . /root
workdir /root

run apt-get update
run apt-get upgrade
run apt-get install -y wget
run wget https://repo.postgrespro.ru/std-15/keys/pgpro-repo-add.sh
run sh pgpro-repo-add.sh
run apt-get install -y postgrespro-std-15

run mkdir /var/lib/postgresql/data
run chown postgres /var/lib/postgresql/data
run su postgres -c "initdb -D /var/lib/postgresql/data"

user postgres
workdir /var/lib/postgresql
cmd ["pg_ctl -D /var/lib/postgresql/data start"]