<h2 id="pré-requisitos">Implementando NGINX container usando Terraform</h2>

Para encorajar Learning by doing ao invez de apenas citar comandos com Terraform neste repositorio, pensei e cheguei a conclusão para uma forma mais dinâmica para quem esteja analisando este teste estou adicionado uma solução de estudo da Kota<oda onde você encontrará uma ferramenta de treino e deploy em um terminal real!
Ao meu ponto de vista é a melhor forma e modelo de garantir a melhor capacidade dos profissionais de sua equipe, com este tipo recurso que ensina end-end como realizar diversos tipos de deploy de soluções,porem exclusivamente para nosso caso proposto precisamos realizar um deploy de NGINX usando terraform, então vamos fazer junto clica no link abaixo:

[Deploy NGINX container using Terraform](https://www.katacoda.com/courses/terraform/deploy-nginx)

<h2 id="pré-requisitos">Pré-requisitos e Instalação servidor Web Nginx com PHP e servidor MySQL </h2>

<p>Para completar este tutorial, você precisará de acesso a uma conta na Microsoft Azure ou a um Cloud Providor de sua preferência e a um servidor Ubuntu 20.04, como um usuário <code>sudo</code> regular, não root , e um firewall habilitado em seu servidor. Para configurar isto, segue link de referencia para configuração com Microsoft Azure.
  
  [Azure Quickstart- Create a Linux virtual machine in the Azure portal](https://docs.microsoft.com/en-us/azure/virtual-machines/linux/quick-create-portal)
  

<h2 id="passo-1-—-como-instalar-o-servidor-web-nginx">Passo 1 — Como instalar o servidor Web Nginx</h2>

<p>Para mostrar páginas Web aos visitantes de nosso site, vamos usar o Nginx, um servidor Web de alto desempenho. Usaremos o gerenciador de pacotes <code>apt</code> para obter esse software.</p>

<p>Uma vez que essa é a primeira vez que vamos usar o <code>apt</code> para esta sessão, atualize o índice de pacotes do seu servidor. Em seguida, você pode usar o <code>apt install</code> para instalar o Nginx:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo apt update
</li><li class="line" prefix="$">sudo apt install nginx
</li></ul></code></pre>
<p>Quando solicitado, digite <code>y</code> para confirmar se deseja instalar o Nginx. Assim que a instalação terminar, o servidor web Nginx estará ativo e em execução em seu servidor Ubuntu 20.04.</p>

<p>Se você tiver o firewall <code>ufw</code> habilitado, conforme recomendado em nosso guia de configuração inicial de servidor, você precisará permitir conexões com o Nginx. O Nginx registra alguns perfis diferentes de aplicações no UFW após a instalação. Para verificar quais perfis do UFW estão disponíveis, execute:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo ufw app list
</li></ul></code></pre><pre class="code-pre "><code><div class="secondary-code-label " title="Output">Output</div>Available applications:
  Nginx Full
  Nginx HTTP
  Nginx HTTPS
  OpenSSH
</code></pre>
<p>É recomendável que você habilite o perfil mais restritivo que, ainda assim, permitirá o tráfego que você precisa. Como você ainda não configurou o SSL para seu servidor neste guia, você precisará apenas permitir o tráfego HTTP regular na porta <code>80</code>.</p>

<p>Habilite isso digitando:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo ufw allow 'Nginx HTTP'
</li></ul></code></pre>
<p>Verifique a mudança executando:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo ufw status
</li></ul></code></pre>
<p>A saída deste comando irá mostrar que o tráfego HTTP está permitido agora:</p>
<pre class="code-pre "><code><div class="secondary-code-label " title="Output">Output</div>Status: active

To                         Action      From
--                         ------      ----
OpenSSH                    ALLOW       Anywhere
<span class="highlight">Nginx HTTP                 ALLOW       Anywhere</span>
OpenSSH (v6)               ALLOW       Anywhere (v6)
<span class="highlight">Nginx HTTP (v6)            ALLOW       Anywhere (v6)</span>
</code></pre>
<p>Com essas novas regras adicionadas no firewall, você pode testar se o servidor está funcionando acessando o nome do domínio do seu servidor ou endereço IP público no seu navegador Web.</p>

<p>Se você não tiver um nome de domínio apontando para o seu servidor e você não souber o endereço IP público dele, é possível encontrá-lo executando o seguinte comando:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">ip addr show eth0 | grep inet | awk '{ print $2; }' | sed 's/\/.*$//'
</li></ul></code></pre>
<p>Isso irá mostrar na tela alguns endereços IP. Você pode testar cada um deles em seu navegador Web.</p>

<p>Como uma alternativa, verifique qual endereço IP está acessível, como visto por outros locais na internet:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">curl -4 icanhazip.com
</li></ul></code></pre>
<p>Digite o endereço que receber no seu navegador Web e ele irá levá-lo para a página inicial do Nginx:</p>
<pre class="code-pre "><code>http://<span class="highlight">server_domain_or_IP</span>
</code></pre>
<p><img src="https://assets.digitalocean.com/articles/lemp_ubuntu2004/nginx_default.png" alt="Nginx default page"></p>

<p>Se você vir essa página, significa que você instalou o Nginx com sucesso e habilitou o tráfego HTTP para seu servidor web.</p>

<h2 id="passo-2-—-instalando-o-mysql">Passo 2 — Instalando o MySQL</h2>

<p>Agora que você tem um servidor web funcionando, você precisa instalar um sistema de banco de dados, para conseguir armazenar e gerenciar os dados do seu site. O MySQL é um sistema de gerenciamento de banco de dados popular, usado em ambientes PHP.</p>

<p>Novamente, utilize o <code>apt</code> para adquirir e instalar este software:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo apt install mysql-server
</li></ul></code></pre>
<p>Quando solicitado, confirme a instalação digitando <code>Y</code> e, depois, <code>ENTER</code>.</p>

<p>Quando a instalação terminar, é recomendável que você execute um script de segurança que vem pré-instalado com o MySQL. Esse script removerá algumas configurações padrão inseguras e irá bloquear o acesso ao seu sistema de banco de dados. Inicie o script interativo executando:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo mysql_secure_installation
</li></ul></code></pre>
<p>Este script irá perguntar se você deseja configurar o <code>VALIDATE PASSWORD PLUGIN</code>.</p>

<p><span class='warning'><strong>Atenção:</strong> ativar esta característica é uma decisão sua. Se habilitada, as senhas que não corresponderem ao critério especificado serão rejeitadas pelo MySQL com um erro. É seguro deixar a validação desativada, mas sempre utilize senhas fortes e únicas para as credenciais do banco de dados.<br></span></p>

<p>Responda <code>Y</code> para sim, ou qualquer outra coisa para continuar sem a habilitar.</p>
<pre class="code-pre "><code>VALIDATE PASSWORD PLUGIN can be used to test passwords
and improve security. It checks the strength of password
and allows the users to set only those passwords which are
secure enough. Would you like to setup VALIDATE PASSWORD plugin?

Press y|Y for Yes, any other key for No:
</code></pre>
<p>Se você responder &quot;yes&rdquo;, você será solicitado a selecionar um nível de validação por senha. Lembre-se de que se você digitar <code>2</code> para o nível mais forte você receberá erros ao tentar definir qualquer senha que não contenha números, letras maiúsculas e minúsculas, e caracteres especiais, ou que baseiam-se em palavras comuns do dicionário.</p>
<pre class="code-pre "><code>There are three levels of password validation policy:

LOW    Length &gt;= 8
MEDIUM Length &gt;= 8, numeric, mixed case, and special characters
STRONG Length &gt;= 8, numeric, mixed case, special characters and dictionary              file

Please enter 0 = LOW, 1 = MEDIUM and 2 = STRONG: <span class="highlight">1</span>
</code></pre>
<p>Independentemente de você ter escolhido <code>VALIDATE PASSWORD PLUGIN</code>, seu servidor irá pedir a você para selecionar e confirmar uma senha para o.<strong>root</strong> user do MySQL. Isso não deve ser confundido com o <strong>root do sistema</strong>. O usuário <strong>root do banco de dados</strong> é um usuário administrativo com privilégios totais sobre o sistema de banco de dados. Embora o método de autenticação predefinido para o usuário root dispense o uso de uma senha, <strong>mesmo quando uma senha está definida</strong>, você deve definir uma senha forte aqui como uma medida de segurança adicional. Vamos falar sobre isso em breve.</p>

<p>Se você habilitar a validação por senha, será apresentado a você a força da senha para a senha root. e o seu servidor perguntará se você deseja continuar com essa senha. Se estiver satisfeito com sua senha atual, digite <code>Y</code> para &ldquo;yes&rdquo; no prompt:</p>
<pre class="code-pre "><code>Estimated strength of the password: <span class="highlight">100</span>
Do you wish to continue with the password provided?(Press y|Y for Yes, any other key for No) : <span class="highlight">y</span>
</code></pre>
<p>Para o resto das perguntas, pressione <code>Y</code> e pressione a tecla <code>ENTER</code> em cada prompt. Isso removerá alguns usuários anônimos e o banco de dados de teste, desativará os logins remotos para o root e carregará essas novas regras para que o MySQL respeite imediatamente as alterações que você fez.</p>

<p>Quando terminar, teste se você consegue fazer login no console do MySQL digitando:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo mysql
</li></ul></code></pre>
<p>Isso conectará ao servidor MySQL como usuário administrativo <strong>root</strong> do banco de dados, o que é pressuposto pelo uso do <code>sudo</code> ao executar esse comando. Você deve ver um resultado como este:</p>
<pre class="code-pre "><code><div class="secondary-code-label " title="Output">Output</div>Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 22
Server version: 8.0.19-0ubuntu5 (Ubuntu)

Copyright (c) 2000, 2020, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql&gt;
</code></pre>
<p>Para sair do console do MySQL, digite:</p>
<pre class="code-pre custom_prefix prefixed"><code><ul class="prefixed"><li class="line" prefix="mysql&gt;">exit
</li></ul></code></pre>
<p>Note que você não precisa fornecer uma senha para se conectar como <strong>root</strong> user, embora você tenha definido uma ao executar o script <code>mysql_secure_installation</code>. Isso é porque o método de autenticação padrão para o usuário administrativo do MySQL é <code>unix_socket</code>, em vez de <code>password</code> (senha). Embora, num primeiro momento, isso possa parecer um problema de segurança, tal medida torna o servidor de banco de dados mais seguro, uma vez que que os únicos usuários autorizados a fazer login como usuário <strong>root</strong> do MySQL são os usuários do sistema com privilégios sudo que conectam-se pelo console ou através de uma aplicação executando com os mesmos privilégios. Em termos práticos, isso significa que você não conseguirá usar o usuário <strong>root</strong> do banco de dados administrativo para se conectar a partir do seu aplicativo PHP. Definir uma senha para a conta <strong>root</strong> do MySQL funciona como uma salvaguarda, caso o método de autenticação padrão seja alterado de <code>unix_socket</code> para <code>password</code>.</p>

<p>Para aumentar a segurança, o melhor é configurar contas de usuário dedicadas, com privilégios menos abrangentes em relação a cada banco de dados, especialmente se você planeja ter vários bancos de dados hospedados no seu servidor.</p>

<p><span class='note'><strong>Nota:</strong> no momento em que este artigo foi escrito, a biblioteca nativa do PHP para o MySQL <code>mysqlnd</code> <a href="https://www.php.net/manual/en/ref.pdo-mysql.php">não suporta</a> o <code>caching_sha2_authentication</code>, o método de autenticação padrão para o MySQL 8. Por essa razão, ao criar usuários de banco de dados para aplicações PHP no MySQL 8, você precisará garantir que eles estejam configurados para usar o <code>mysql_native_password</code>. Vamos demonstrar como fazer isso no <a href="#step-6-%E2%80%94-testing-database-connection-from-php-(optional)">Passo 6</a>.<br></span></p>

<p>Agora, seu servidor MySQL está instalado e protegido. Em seguida, instalaremos o PHP, o componente final na pilha LEMP.</p>

<h2 id="passo-3-—-instalando-o-php">Passo 3 — Instalando o PHP</h2>

<p>Você tem o Nginx instalado para exibir seu conteúdo e o MySQL instalado para armazenar e gerenciar seus dados. Agora, você pode instalar o PHP para processar código e gerar conteúdo dinâmico para o servidor Web.</p>

<p>Enquanto o Apache incorpora o interpretador PHP em cada solicitação, o Nginx necessita de um programa externo para lidar com o processamento PHP e atuar como uma ponte entre o próprio interpretador PHP e o servidor web. Isso permite um desempenho global melhor na maioria dos sites baseados em PHP, mas exige configuração adicional. Será necessário instalar o <code>php-fpm</code>, que significa &ldquo;Gerenciador de processos PHP fastCGI&rdquo;, e dizer ao Nginx para enviar as solicitações PHP para esse software para processamento. Adicionalmente, você precisará do <code>php-mysql</code> , um módulo PHP que permite ao PHP se comunicar com os bancos de dados baseados em MySQL. Os pacotes básicos do PHP serão instalados automaticamente como dependências.</p>

<p>Para instalar os pacotes <code>php-fpm</code> e <code>php-mysql</code>, execute:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo apt install php-fpm php-mysql
</li></ul></code></pre>
<p>Quando solicitado, digite <code>Y</code> e <code>ENTER</code> para confirmar a instalação.</p>

<p>Agora, você tem seus componentes PHP instalados. Em seguida, você configurará o Nginx para utilizá-los.</p>

<h2 id="passo-4-—-configurando-o-nginx-para-usar-o-processador-php">Passo 4 — Configurando o Nginx para Usar o Processador PHP</h2>

<p>Ao usar o servidor web Nginx, podemos utilizar os <em>blocos de servidor</em> (similares aos virtual hosts no Apache) para encapsular detalhes de configuração e hospedar mais de um domínio em um único servidor. Neste guia, usaremos <strong>your_domain</strong> como um nome de domínio de exemplo. Para aprender mais sobre como configurar um nome de domínio com a DigitalOcean, veja nossa <a href="https://www.digitalocean.com/docs/networking/dns/">Introdução ao DNS do DigitalOcean</a>.</p>

<p>No Ubuntu 20.04, o Nginx tem um bloco de servidor habilitado por padrão que está configurado para servir documentos do diretório <code>/var/www/html</code>. Enquanto isso funciona bem para um único site, isso se torna difícil de gerenciar se você estiver hospedando vários sites. Em vez de modificar o <code>/var/www/html</code>, vamos criar uma estrutura de diretórios dentro do <code>/var/www</code> para o site <strong>your_domain</strong>, deixando o <code>/var/www/html</code> intocado como o diretório padrão para ser servido se uma solicitação de cliente não corresponder a nenhum outro site.</p>

<p>Crie o diretório para <strong>your_domain</strong> como segue:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo mkdir /var/www/<span class="highlight">your_domain</span>
</li></ul></code></pre>
<p>Em seguida, atribua a propriedade do diretório com a variável de ambiente $USER, que deve fazer referência ao seu usuário de sistema atual:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo chown -R $USER:$USER /var/www/<span class="highlight">your_domain</span>
</li></ul></code></pre>
<p>Em seguida, abra um novo arquivo de configuração no diretório <code>sites-available</code> do Nginx usando seu editor de linha de comando preferido. Aqui, usaremos o <code>nano</code>:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo nano /etc/nginx/sites-available/<span class="highlight">your_domain</span>
</li></ul></code></pre>
<p>Isso criará um novo arquivo em branco. Cole nele a seguinte configuração:</p>
<div class="code-label " title="/etc/nginx/sites-available/your_domain">/etc/nginx/sites-available/your_domain</div><pre class="code-pre "><code>server {
    listen 80;
    server_name <span class="highlight">your_domain</span> www.<span class="highlight">your_domain</span>;
    root /var/www/<span class="highlight">your_domain</span>;

    index index.html index.htm index.php;

    location / {
        try_files $uri $uri/ =404;
    }

    location ~ \.php$ {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/var/run/php/php7.4-fpm.sock;
     }

    location ~ /\.ht {
        deny all;
    }

}


</code></pre>
<p>Aqui está o que cada um desses blocos de localização e diretrizes fazem:</p>

<ul>
<li><code>listen</code> — Define em qual porta o Nginx irá escutar. Neste caso, ele irá escutar na porta <code>80</code>, a porta padrão para o HTTP.</li>
<li><code>root</code> — Define o document root onde os arquivos servidos por este site são armazenados.</li>
<li><code>index</code> — Define em que ordem o Nginx irá priorizar os arquivos de index para este site. É uma prática comum listar arquivos <code>index.html</code> com uma precedência superior aos arquivos <code>index.php</code> para permitir uma configuração rápida de uma página inicial de manutenção em aplicações PHP. Você pode ajustar essas configurações para melhor se adaptar às necessidades da sua aplicação.</li>
<li><code>server_name</code> — Define para quais nomes de domínio e/ou endereços IP este bloco de servidor deve responder. <strong>Aponte esta diretiva para o nome de domínio do seu servidor ou endereço IP público.</strong></li>
<li><code>location/</code> — O primeiro bloco de localização inclui uma diretiva <code>try_files</code>, que verifica a existência de arquivos ou diretórios que correspondam a uma requisição de URI. Se o Nginx não puder encontrar o recurso apropriado, ele irá retornar um erro 404.</li>
<li><code>location ~ \.php$</code> — Este bloco de localização lida com o processamento PHP real, apontando o Nginx para o arquivo de configuração <code>fastcgi-php.conf</code> e o arquivo <code>php7.4-fpm.sock</code>, que declara qual soquete está associado ao <code>php-fpm</code>.</li>
<li><code>location ~ /\.ht</code> — O último bloco de localização lida com os arquivos <code>.htaccess</code>, que o Nginx não processa. Ao adicionar a diretiva <code>deny all</code>, se acontecer de algum arquivo <code>.htaccess</code> ser encontrado no caminho do document root, ele não será apresentado aos visitantes.</li>
</ul>

<p>Quando terminar de editar, salve e feche o arquivo. Se você estiver usando o <code>nano</code>, você pode fazer isso digitando <code>CTRL+X</code> e, depois, <code>y</code> e <code>ENTER</code> para confirmar.</p>

<p>Ative sua configuração vinculando ao arquivo de configuração no diretório <code>sites-enabled</code> do Nginx:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo ln -s /etc/nginx/sites-available/<span class="highlight">your_domain</span> /etc/nginx/sites-enabled/
</li></ul></code></pre>
<p>Isso dirá ao Nginx para usar a configuração da próxima vez que ela for recarregada. Teste a configuração para conferir erros de sintaxe digitando:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo nginx -t
</li></ul></code></pre>
<p>Se algum erro for reportado, volte para seu arquivo de configuração para revisar seu conteúdo antes de continuar.</p>

<p>Quando estiver pronto, recarregue o Nginx para aplicar as alterações:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo systemctl reload nginx
</li></ul></code></pre>
<p>Agora, seu novo site está ativo, mas o web root <code>/var/www/<span class="highlight">your_domain</span></code> ainda está vazio. Crie um arquivo <code>index.html</code> naquele local para que possamos testar se o seu novo bloco de servidor funciona conforme esperado:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">nano /var/www/<span class="highlight">your_domain</span>/index.html
</li></ul></code></pre>
<p>Inclua o conteúdo a seguir neste arquivo:</p>
<div class="code-label " title="/var/www/your_domain/index.html">/var/www/your_domain/index.html</div><pre class="code-pre "><code>&lt;html&gt;
  &lt;head&gt;
    &lt;title&gt;<span class="highlight">your_domain</span> website&lt;/title&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;h1&gt;Hello World!&lt;/h1&gt;

    &lt;p&gt;This is the landing page of &lt;strong&gt;<span class="highlight">your_domain</span>&lt;/strong&gt;.&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;
</code></pre>
<p>Agora, vá para seu navegador e acesse o nome de domínio ou endereço IP do seu servidor, conforme listado na diretiva <code>server_name</code> em seu arquivo de configuração de bloco de servidor:</p>
<pre class="code-pre "><code>http://<span class="highlight">server_domain_or_IP</span>
</code></pre>
<p>Você verá uma página como esta:</p>

<p><img src="https://assets.digitalocean.com/articles/lemp_ubuntu2004/landing_page.png" alt="Nginx server block"></p>

<p>Se você vir esta página, isso significa que seu bloco de servidor do Nginx está funcionando como esperado.</p>

<p>Você pode deixar esse arquivo funcionando como uma página principal temporária para sua aplicação até que você configure um arquivo <code>index.php</code> para substituí-lo. Assim que fizer isso, lembre-se de remover ou renomear o arquivo <code>index.html</code> de seu document root pois isso teria precedência sobre um arquivo <code>index.php</code> por padrão.</p>

<p>Sua pilha LEMP está totalmente configurada agora. No próximo passo, criaremos um script PHP para testar se o Nginx é, de fato, capaz de lidar com arquivos <code>.php</code> dentro do seu site recém configurado.</p>

<h2 id="passo-5-—-testando-o-php-com-o-nginx">Passo 5 — Testando o PHP com o Nginx</h2>

<p>Sua pilha LEMP agora deve estar configurada completamente. Você pode testá-la para validar que o Nginx pode manusear corretamente os arquivos <code>.php</code> para o seu processador PHP.</p>

<p>Você pode fazer isso criando um arquivo PHP de teste em seu document root. Abra um novo arquivo chamado <code>info.php</code> dentro do documento raiz no editor de texto:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">nano /var/www/<span class="highlight">your_domain</span>/info.php
</li></ul></code></pre>
<p>Digite ou cole as seguintes linhas dentro do novo arquivo: Este é um código PHP válido que irá retornar informações sobre seu servidor:</p>
<div class="code-label " title="/var/www/your_domain/info.php">/var/www/your_domain/info.php</div><pre class="code-pre "><code>&lt;?php
phpinfo();
</code></pre>
<p>Quando você terminar, salve e feche o arquivo digitando <code>CTRL</code>+<code>X</code> e, depois, <code>y</code> e <code>ENTER</code> para confirmar.</p>

<p>Agora, você pode acessar essa página em seu navegador web visitando o nome de domínio ou o endereço IP público que você configurou em seu arquivo de configuração do Nginx, seguido por <code>/info.php</code>:</p>
<pre class="code-pre "><code>http://<span class="highlight">server_domain_or_IP</span>/info.php
</code></pre>
<p>Você verá uma página web contendo informações detalhadas sobre seu servidor:</p>

<p><img src="https://assets.digitalocean.com/articles/lemp_ubuntu2004/phpinfo.png" alt="PHPInfo Ubuntu 20.04"></p>

<p>Após verificar as informações relevantes sobre seu servidor PHP através dessa página, é melhor remover o arquivo que você criou, uma vez que ele contém informações sensíveis sobre seu ambiente PHP e seu servidor Ubuntu. Use o <code>rm</code> para remover esse arquivo:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo rm /var/www/<span class="highlight">your_domain</span>/info.php
</li></ul></code></pre>
<p>Você sempre pode gerar esse arquivo novamente se você precisar dele mais tarde.</p>

<h2 id="passo-6-—-testando-a-conexão-com-o-banco-de-dados-pelo-php-opcional">Passo 6 — Testando a Conexão com o Banco de Dados pelo PHP (Opcional)</h2>

<p>Se você quiser testar se o PHP é capaz de se conectar ao MySQL e executar consultas ao banco de dados, você pode criar uma tabela de teste, com dados fictícios, e fazer uma consulta em seu conteúdo, a partir de um script PHP. Antes que possamos fazer isso, precisamos criar um banco de dados de teste e um novo usuário do MySQL corretamente configurado para acessá-lo.</p>

<p>No momento em que este artigo foi escrito, a biblioteca <code>mysqlnd</code> nativa do PHP para o MySQL <a href="https://www.php.net/manual/en/ref.pdo-mysql.php">não suporta</a> o <code>caching_sha2_authentication</code>, o método de autenticação padrão para o MySQL 8. Precisaremos criar um novo usuário com o método de autenticação <code>mysql_native_password</code> para conseguir se conectar ao banco de dados MySQL a partir do PHP.</p>

<p>Vamos criar um banco de dados chamado <strong>example_database</strong> e um usuário chamado <strong>example_user</strong>, mas você pode substituir esses nomes por valores diferentes.</p>

<p>Primeiro, conecte-se ao console do MySQL usando a conta <strong>root</strong>:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo mysql
</li></ul></code></pre>
<p>Para criar um novo banco de dados, execute o seguinte comando a partir do seu console do MySQL:</p>
<pre class="code-pre custom_prefix prefixed"><code><ul class="prefixed"><li class="line" prefix="mysql&gt;">CREATE DATABASE <span class="highlight">example_database</span>;
</li></ul></code></pre>
<p>Agora, crie um usuário e lhe conceda privilégios completos sobre o banco de dados personalizado que acabou de criar.</p>

<p>O comando a seguir cria um novo usuário chamado <code><span class="highlight">example_user</span></code> usando o <code>mysql_native_password</code> como o método de autenticação padrão. Vamos definir a senha do usuário como <code><span class="highlight">password</span></code>, mas você deve substituir esse valor por uma senha segura de sua própria escolha:</p>
<pre class="code-pre custom_prefix prefixed"><code><ul class="prefixed"><li class="line" prefix="mysql&gt;">CREATE USER '<span class="highlight">example_user</span>'@'%' IDENTIFIED WITH mysql_native_password BY '<span class="highlight">password</span>';
</li></ul></code></pre>
<p>Agora, precisamos dar a este usuário permissão para o banco de dados <code>example_database</code>:</p>
<pre class="code-pre custom_prefix prefixed"><code><ul class="prefixed"><li class="line" prefix="mysql&gt;">GRANT ALL ON example_database.* TO 'example_user'@'%';
</li></ul></code></pre>
<p>Isso dará ao usuário <strong>example_user</strong> privilégios totais sobre o banco de dados <strong>example_database</strong>, ao mesmo tempo que impedirá que esse usuário crie ou altere outros bancos de dados no seu servidor.</p>

<p>Agora, saia do shell do MySQL com:</p>
<pre class="code-pre custom_prefix prefixed"><code><ul class="prefixed"><li class="line" prefix="mysql&gt;">exit
</li></ul></code></pre>
<p>Você pode testar se o novo usuário tem as permissões adequadas fazendo login no console MySQL novamente, desta vez usando as credenciais de usuário personalizadas:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">mysql -u <span class="highlight">example_user</span> -p
</li></ul></code></pre>
<p>Note a flag <code>-p</code> neste comando, a qual irá solicitar a senha utilizada ao criar o usuário <strong>example_user</strong>. Após fazer login no console do MySQL, confirme se você tem acesso ao banco de dados <strong>example_database</strong>:</p>
<pre class="code-pre custom_prefix prefixed"><code><ul class="prefixed"><li class="line" prefix="mysql&gt;">SHOW DATABASES;
</li></ul></code></pre>
<p>Isso gerará o seguinte resultado:</p>
<pre class="code-pre "><code><div class="secondary-code-label " title="Output">Output</div>+--------------------+
| Database           |
+--------------------+
| <span class="highlight">example_database</span>   |
| information_schema |
+--------------------+
2 rows in set (0.000 sec)
</code></pre>
<p>Em seguida, criaremos uma tabela de teste chamada <strong>todo_list</strong>. A partir do console do MySQL, execute a seguinte instrução:</p>
<pre class="code-pre custom_prefix prefixed"><code><ul class="prefixed"><li class="line" prefix="mysql&gt;">CREATE TABLE <span class="highlight">example_database</span>.<span class="highlight">todo_list</span> (
</li><li class="line" prefix="mysql&gt;">    item_id INT AUTO_INCREMENT,
</li><li class="line" prefix="mysql&gt;">    content VARCHAR(255),
</li><li class="line" prefix="mysql&gt;">    PRIMARY KEY(item_id)
</li><li class="line" prefix="mysql&gt;">);
</li></ul></code></pre>
<p>Insira algumas linhas de conteúdo na tabela de teste. Talvez queira repetir o próximo comando algumas vezes, usando valores diferentes:</p>
<pre class="code-pre custom_prefix prefixed"><code><ul class="prefixed"><li class="line" prefix="mysql&gt;">INSERT INTO <span class="highlight">example_database</span>.<span class="highlight">todo_list</span> (content) VALUES ("<span class="highlight">My first important item</span>");
</li></ul></code></pre>
<p>Para confirmar se os dados foram salvos com sucesso em sua tabela, execute:</p>
<pre class="code-pre custom_prefix prefixed"><code><ul class="prefixed"><li class="line" prefix="mysql&gt;">SELECT * FROM <span class="highlight">example_database</span>.<span class="highlight">todo_list</span>;
</li></ul></code></pre>
<p>Você verá o seguinte resultado:</p>
<pre class="code-pre "><code><div class="secondary-code-label " title="Output">Output</div>+---------+--------------------------+
| item_id | content                  |
+---------+--------------------------+
|       1 | My first important item  |
|       2 | My second important item |
|       3 | My third important item  |
|       4 | and this one more thing  |
+---------+--------------------------+
4 rows in set (0.000 sec)

</code></pre>
<p>Após confirmar que você tem dados válidos em sua tabela de teste, saia do console do MySQL:</p>
<pre class="code-pre custom_prefix prefixed"><code><ul class="prefixed"><li class="line" prefix="mysql&gt;">exit
</li></ul></code></pre>
<p>Agora, você pode criar o script PHP que se conectará ao MySQL e irá consultar seu conteúdo. Crie um arquivo do PHP no seu diretório raiz da Web personalizado, usando seu editor preferido. Usaremos o <code>nano</code> para isso:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">nano /var/www/<span class="highlight">your_domain</span>/<span class="highlight">todo_list.php</span>
</li></ul></code></pre>
<p>O script PHP a seguir se conecta ao banco de dados MySQL e consulta o conteúdo da tabela <strong>todo_list</strong>, mostrando os resultados em uma lista. Se houver um problema com a conexão do banco de dados, ele irá gerar uma exceção. Copie este conteúdo para seu script <code>todo_list.php</code>:</p>
<div class="code-label " title="/var/www/your_domain/todo_list.php">/var/www/your_domain/todo_list.php</div><pre class="code-pre "><code class="code-highlight language-php">&lt;?php
$user = "<span class="highlight">example_user</span>";
$password = "<span class="highlight">password</span>";
$database = "<span class="highlight">example_database</span>";
$table = "<span class="highlight">todo_list</span>";

try {
  $db = new PDO("mysql:host=localhost;dbname=$database", $user, $password);
  echo "&lt;h2&gt;TODO&lt;/h2&gt;&lt;ol&gt;";
  foreach($db-&gt;query("SELECT content FROM $table") as $row) {
    echo "&lt;li&gt;" . $row['content'] . "&lt;/li&gt;";
  }
  echo "&lt;/ol&gt;";
} catch (PDOException $e) {
    print "Error!: " . $e-&gt;getMessage() . "&lt;br/&gt;";
    die();
}
</code></pre>
<p>Salve e feche o arquivo quando terminar de editar.</p>

<p>Agora, você pode acessar esta página em seu navegador web visitando o nome de domínio ou o endereço IP público para seu site, seguido de <code>/todo_list.php</code>:</p>
<pre class="code-pre "><code>http://<span class="highlight">server_domain_or_IP</span>/todo_list.php
</code></pre>
<p>Você deve ver uma página como esta, mostrando o conteúdo que você inseriu em sua tabela de teste:</p>

<p><img src="https://assets.digitalocean.com/articles/lemp_debian10/todo_list.png" alt="Example PHP todo list​​​​​"></p>

<p>Isso significa que seu ambiente PHP está pronto para se conectar e interagir com seu servidor MySQL.</p>

<h2 id="conclusão">Conclusão</h2>

<p>Neste guia, construímos uma base flexível para servir sites e aplicações PHP aos seus visitantes, usando o Nginx como servidor web e o MySQL como sistema de banco de dados.</p>

<p>Há um número de passos que você pode tomar a partir daqui. Por exemplo, certifique-se de que as conexões para seu servidor estejam seguras. Para isso, você pode <a href="https://www.digitalocean.com/community/tutorials/how-to-secure-nginx-with-let-s-encrypt-on-ubuntu-20-04">proteger sua instalação Nginx com o Let&rsquo;s Encrypt</a>. Ao seguir este guia, você receberá um certificado TLS/SSL gratuito para seu servidor, permitindo que apresente conteúdo em HTTPS.</p>
  </body>
</html>

Muito Obrigado por está oportunidade de guia-os atraves desde tutorial para criação de recursos para este desafio!

Diego Machado
