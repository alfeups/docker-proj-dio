# Criando um Container de uma Aplicação WEB

## Docker compose para executar uma aplicação HTML in um container Apache.

<br>

### Requirements:

<li>Ubuntu</li>
<li>Docker</li>
<li>Docker compose</li>
<li>Apache</li>

<br>

### Steps:

<li>Criar um arquivo YML com a config do servidor apache;</li>
<li>Especificar no yml o path da app;</li>
<li>Subir o arquivo e a app para o Github;</li>
<br>

<p>Criar um arquivo compose de extensão yml.</p>

```
nano docker-compose.yml
```

<p>Inserir as definições do Apache:</p>

```
version: '3'
services:
  apache:
    image: httpd:latest
    container_name: my-apache-container
    ports:
      - 80:80
    volumes:
      - ./html:/usr/local/apache2/htdocs/
``` 


<p>Criar e acessar o diretório para armazenar a aplicação(app):</p>

```
mkdir app
cd app
```

<p>Criar o arquivo HTML que seria utilizado como aplicação(index.html) e colocar o conteúdo nele:</p>

```
nano index.html
```

```
<!DOCTYPE html>
<html>
<title>W3.CSS Template</title>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<link rel="stylesheet" href="https://www.w3schools.com/w3css/4/w3.css">
<link rel='stylesheet' href='https://fonts.googleapis.com/css?family=Roboto'>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
<style>
    html,body,h1,h2,h3,h4,h5,h6 {font-family: "Roboto", sans-serif}
</style>
<body class="w3-light-grey">

<!-- Page Container -->
<div class="w3-content w3-margin-top" style="max-width:1400px;">

    <!-- The Grid -->
    <div class="w3-row-padding">

        <!-- Left Column -->
        <div class="w3-third">

            <div class="w3-white w3-text-grey w3-card-4">
                <div class="w3-display-container">
                    <img src="alfeups.JPG" style="width:100%" alt="Avatar">
                    <div class="w3-display-bottomleft w3-container w3-text-white">
                        <h2>Alfeu Pereira</h2>
                    </div>
                </div>
                <div class="w3-container">
                    <p><i class="fa fa-briefcase fa-fw w3-margin-right w3-large w3-text-teal"></i>Software Developer</p>
                    <p><i class="fa fa-home fa-fw w3-margin-right w3-large w3-text-teal"></i>Recife, BR</p>
                    <p><i class="fa fa-envelope fa-fw w3-margin-right w3-large w3-text-teal"></i>alfeups@hotmail.com</p>
                    <p><i class="fa fa-phone fa-fw w3-margin-right w3-large w3-text-teal"></i>+5581989241097</p>
                    <hr>

                    <p class="w3-large"><b><i class="fa fa-asterisk fa-fw w3-margin-right w3-text-teal"></i>Skills</b></p>
                    <p>Java</p>
                    <p>Spring Boot</p>
                    <p>MySQL</p>
                    <p>AWS</p>
                    <p>JavaScript</p>

                    <br>

                    <p class="w3-large w3-text-theme"><b><i class="fa fa-globe fa-fw w3-margin-right w3-text-teal"></i>Languages</b></p>
                    <p>Portuguese</p>
                    <div class="w3-light-grey w3-round-xlarge">
                        <div class="w3-round-xlarge w3-teal" style="height:24px;width:100%;text-align:center;">Native</div>
                    </div>
                    <p>English</p>
                    <div class="w3-light-grey w3-round-xlarge">
                        <div class="w3-round-xlarge w3-teal" style="height:24px;width:100%;text-align:center;">Advanced</div>
                    </div>
                    <p>German</p>
                    <div class="w3-light-grey w3-round-xlarge">
                        <div class="w3-round-xlarge w3-teal" style="height:24px;width:100%;text-align:center;" >Beginner</div>
                    </div>
                    <br>
                </div>
            </div><br>

            <!-- End Left Column -->
        </div>

        <!-- Right Column -->
        <div class="w3-twothird">

            <div class="w3-container w3-card w3-white w3-margin-bottom">
                <h2 class="w3-text-grey w3-padding-16"><i class="fa fa-suitcase fa-fw w3-margin-right w3-xxlarge w3-text-teal"></i>Work Experience</h2>
                <div class="w3-container">
                    <h5 class="w3-opacity"><b>Back-End Developer / NTT DATA</b></h5>
                    <h6 class="w3-text-teal"><i class="fa fa-calendar fa-fw w3-margin-right"></i>Sept 2021 - <span class="w3-tag w3-teal w3-round">Current</span></h6>
                    <p>
                    <li>Working in Banking – Agricultural Loans & Financing Systems.
                    <li>Good skills at building Java web applications using Spring/Spring Boot, Hibernate, MVC frameworks and
                        MySQL database.
                    <li> Working daily with Git, Maven, Mockito, JUnit 5, Pitest.
                    <li> Working with AWS Services such as S3, Lambda, SQS and EC2 instances.
                    <li> Able to develop useful and replicable solutions in order to speed up team development.
                    <li> Good understanding of data structures and algorithms.
                    <li> Experience with Agile methodologies, including Scrum and Kanban daily.
                    <li> Have been working in a DevOps culture squad.

                    </p>
                    <hr>
                </div>
            </div>

            <div class="w3-container w3-card w3-white">
                <h2 class="w3-text-grey w3-padding-16"><i class="fa fa-certificate fa-fw w3-margin-right w3-xxlarge w3-text-teal"></i>Education</h2>
                <div class="w3-container">
                    <h5 class="w3-opacity"><b>Centro Universitario dos Guararapes – UNIFG</b></h5>
                    <h6 class="w3-text-teal"><i class="fa fa-calendar fa-fw w3-margin-right"></i>Jan 2021 – Dec 2023</h6>
                    <p>BSc. Information Systems</p>
                    <p>Recife, Brazil</p>
                    <hr>
                </div>
                <div class="w3-container">
                    <h5 class="w3-opacity"><b>Centro Universitario dos Guararapes - UNIFG </b></h5>
                    <h6 class="w3-text-teal"><i class="fa fa-calendar fa-fw w3-margin-right"></i>July 2020 – Dec 2022</h6>
                    <p>B.Sc. Big Data & Analytical Intelligence</p>
                    <p>Recife, Brazil</p>
                    <hr>
                </div>
                <div class="w3-container">
                    <h5 class="w3-opacity"><b>Emerald Cultural Institute – English Exchange</b></h5>
                    <h6 class="w3-text-teal"><i class="fa fa-calendar fa-fw w3-margin-right"></i>May 2019 – Dec 2019</h6>
                    <p>English Course Certification C1, English</p>
                    <p>Dublin, Republic of Ireland</p><br>
                </div>
            </div>
            <!-- End Right Column -->
        <div class="w3-container w3-card w3-white">
            <h2 class="w3-text-grey w3-padding-16"><i class="fa fa-certificate fa-fw w3-margin-right w3-xxlarge w3-text-teal"></i>Certifications</h2>
            <div class="w3-container">
                <h5 class="w3-opacity"><b>Amazon AWS Cloud Practitioner Certified.</b></h5>
                <h6 class="w3-text-teal"><i class="fa fa-calendar fa-fw w3-margin-right"></i>Dec 2022 – Dec 2025.</h6>
                <p>International English Language Test</p>
                <p>AWS Partner: Accreditation (Business)</p>
                <p>AWS Partner: Cloud Economics Accreditation</p>
                <p>AWS Partner: Accreditation (Technical)</p>
                <p>Building a Machine Learning Ready Organization</p>
                <p>Introduction to Machine Learning: The art of possible</p>
                <p>Planning a Machine Learning Project</p>
                <hr>
            </div>
        </div>
        <!-- End Grid -->
        </div>

    <!-- End Page Container -->
</div>

<footer class="w3-container w3-teal w3-center w3-margin-top">
    <p>Find me on social media.</p>

    <a class="fa fa-instagram w3-hover-opacity" target="_blank" href="https://www.instagram.com/alfeups/"> </a>
    <!--...
    <i class="fa fa-facebook-official w3-hover-opacity"></i>
    <i class="fa fa-snapchat w3-hover-opacity"></i>
    <i class="fa fa-pinterest-p w3-hover-opacity"></i>
     <i class="fa fa-twitter w3-hover-opacity"></i>
     -->
    <a class="fa fa-linkedin w3-hover-opacity" target="_blank" href="https://www.linkedin.com/in/alfeups/"></a>
    <p>Powered by <a href="https://www.w3schools.com/w3css/default.asp" target="_blank">w3.css</a></p>
</footer>

</body>
</html>

```

<p>Após preencher o arquivo, pressionar CTRL+O e CTRL+X e subir o docker compose detachado.</p>

```
docker compose up -d
```


