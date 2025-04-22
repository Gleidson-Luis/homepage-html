# homepage-html

Este projeto é um exemplo básico de um site estático desenvolvido apenas com HTML e CSS. Ideal para iniciantes que estão aprendendo os fundamentos da criação de páginas web.

**## 🌐 Demonstração

Você pode visualizar a página abrindo o arquivo `index.html` em qualquer navegador.

## 🚀 Como Usar

1. Clone este repositório: git clone https://github.com/Gleidson-Luis/homepage-html.git
2. Navegue até o diretório do projeto: cd site-simples
3. Abra o arquivo index.html em seu navegador.

## ✏️ Personalização através de Script

#! /bin/bash

if [ ! -x /etc/init.d/apache2 ]; then
echo "Apache nao encontrado, iniciando a instalação..."
sudo apt-get update
sudo apt-get install apache2 -y
else
echo "Voce ja possui um apache instalado"
fi

sudo mkdir -p /var/www/ifrn/public_html
cd /var/www/ifrn/public_html
sudo git clone https://github.com/matheusmanuel/site-simples-com-html-e-css-.git
sudo cp -r site-simples-com-html-e-css-/* .
sudo rm -rf site-simples-com-html-e-css-/
cd /etc/apache2/sites-available/
sudo tee ifrn.conf<<EOF
<VirtualHost *:80>
	ServerAdmin admin@ifrn
	ServerName ifrn
	ServerAlias www.ifrn
	DocumentRoot /var/www/ifrn/public_html
	ErrorLog ${APACHE_LOG_DIR}/error.log
	CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
EOF

sudo a2ensite ifrn.conf

sudo echo "127.0.0.1	ifrn" | sudo tee -a /etc/hosts

sudo /etc/init.d/apache2 restart
sudo /etc/init.d/apache2 status

## 📌 Requisitos
Nenhum requisito especial. Apenas um navegador web moderno (Chrome, Firefox, Edge, etc).

## 🤝 Contribuindo
Sinta-se à vontade para fazer um fork do projeto, criar novas features ou corrigir bugs. Pull requests são bem-vindos!
