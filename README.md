# Aplicacoes-do-AWS-Rekognition

![Configuração AWS](images/logo.jpg)

Este projeto tem como objetivo demonstrar como utilizar o AWS Rekognition para detectar celebridades em imagens. A ferramenta AWS Rekognition permite identificar pessoas famosas com base em um banco de dados extenso de celebridades de diversas categorias, como entretenimento, política, esportes, entre outros.

## Descrição do Projeto

O projeto está dividido em várias etapas:

1. **Configuração da Conta AWS**  
   Antes de iniciar, você precisa de uma conta AWS com permissões para usar o serviço Rekognition. Caso ainda não tenha, acesse [AWS Free Tier](https://aws.amazon.com/free/) para criar uma conta gratuita.

2. **Carregamento de Imagem no S3**  
   As imagens que serão analisadas precisam estar armazenadas em um bucket no Amazon S3. Crie um bucket no S3 e carregue suas imagens.

   ```bash
   aws s3 cp /caminho/para/sua/imagem.jpg s3://seu-bucket/imagens/
   ```

3. **Detecção de Celebridades com AWS CLI**  
   Após carregar a imagem no S3, você pode usar a AWS CLI para chamar a função de detecção de celebridades.

   ```bash
   aws rekognition recognize-celebrities \
     --image "S3Object={Bucket='seu-bucket',Name='imagens/imagem.jpg'}"
   ```

4. **Análise dos Resultados**  
   O AWS Rekognition retorna uma lista de celebridades detectadas com informações detalhadas, como nome, URL para mais informações e a posição da face detectada na imagem.

   Exemplo de resposta:

   ```json
   {
     "CelebrityFaces": [
       {
         "Name": "Tom Cruise",
         "Urls": ["https://en.wikipedia.org/wiki/Tom_Cruise"],
         "Face": {
           "BoundingBox": {
             "Width": 0.3,
             "Height": 0.4,
             "Left": 0.5,
             "Top": 0.2
           }
         }
       }
     ]
   }
   ```

## Prints do Processo

### 1. Criando sua Conta AWS

![Configuração AWS](images/signup_page.png)

### 2. Conhecendo os serviços do AWS Rekognition

![AWS Rekognition CLI](images/functions.png)

### 3. Analisando Resultados da análise

![Resultados JSON](images/result.png)

## Insights e Possibilidades

- **Reconhecimento de Celebridades**:
  É uma aplicação interessante para eventos, redes sociais ou sistemas de gerenciamento de conteúdo que precisam identificar pessoas famosas automaticamente.

- **Segurança e Conformidade**:
  Pode ser usado para verificação de conteúdo em tempo real em plataformas de vídeo e imagem.

- **Marketing e Publicidade**:
  Identificar automaticamente influenciadores em conteúdos enviados por usuários, ajudando a gerar insights sobre o impacto de campanhas.

## Conclusão

Este projeto explica como o AWS Rekognition pode ser utilizado para detectar celebridades em imagens de forma automatizada. Com algumas etapas simples, é possível implementar soluções poderosas que fazem uso do reconhecimento de imagem. O serviço oferece uma grande oportunidade para empresas que lidam com conteúdo visual e precisam extrair informações automaticamente.

Para mais detalhes, consulte a [documentação oficial do AWS Rekognition](https://docs.aws.amazon.com/rekognition/latest/dg/recognize-celebrities.html).

## Onde me encontrar

[![Linkedin](https://img.shields.io/badge/-Edson-blue?style=flat-square&logo=Linkedin&logoColor=white&link=www.linkedin.com/in/edson-oliveira-9a580a231)](www.linkedin.com/in/edson-oliveira-9a580a231)
[![Gmail Badge](https://img.shields.io/badge/-eedsoncarlos359@gmail.com-006bed?style=flat-square&logo=Gmail&logoColor=white&link=mailto:eedsoncarlos359@gmail.com)](mailto:eedsoncarlos359@gmail.com)
[![GitHub](https://img.shields.io/github/followers/EdsonOliveira18?label=follow&style=social)](https://github.com/EdsonOliveira18)