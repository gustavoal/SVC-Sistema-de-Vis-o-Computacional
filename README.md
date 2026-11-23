# SVC — Sistema de Visão Computacional

Sistema de Visão Computacional (SVC) desenvolvido no contexto de uma pesquisa de doutorado, com o objetivo de integrar métodos computacionais para análise de imagens aéreas obtidas por veículos aéreos não tripulados (VANTs/drones), visando à identificação de potenciais focos relacionados à proliferação do mosquito *Aedes aegypti*.

A plataforma disponibiliza uma interface para gerenciamento de missões, execução de modelos de Inteligência Artificial, visualização dos resultados e análise espacial de objetos e cenários identificados nas imagens.

## 1. Sobre o projeto

O SVC foi desenvolvido para centralizar, em uma única aplicação, os métodos computacionais utilizados na análise de imagens coletadas por drones.

O sistema permite organizar os arquivos por missões, selecionar imagens para processamento e executar diferentes métodos de análise computacional. Os resultados são disponibilizados em galerias específicas, possibilitando a inspeção das imagens processadas e, quando aplicável, a visualização de informações georreferenciadas.

A arquitetura funcional da plataforma contempla dois módulos principais:

- **Segmentação de imagens:** aplicação de modelos de segmentação para identificação e geração de máscaras correspondentes às regiões de interesse nas imagens.
- **Detecção de objetos e cenários:** aplicação de modelos de detecção para identificação e anotação de objetos e cenários presentes nas imagens.

Adicionalmente, para imagens no formato GeoTIFF, o módulo de detecção contempla a extração das coordenadas geográficas dos objetos e cenários identificados, permitindo relacionar os resultados à localização espacial correspondente.

## 2. Funcionalidades

As principais funcionalidades disponibilizadas pelo SVC são:

| Funcionalidade | Descrição |
|---|---|
| Cadastro de missões | Registro e organização das atividades de análise. |
| Listagem de missões | Consulta das missões cadastradas e de suas informações. |
| Gerenciamento de imagens | Associação e organização das imagens utilizadas em cada missão. |
| Segmentação | Processamento de imagens por modelos de segmentação. |
| Detecção de objetos e cenários | Identificação e anotação dos elementos presentes nas imagens. |
| Galeria de segmentação | Visualização dos resultados produzidos pelo módulo de segmentação. |
| Galeria de detecção | Consulta das imagens processadas pelo módulo de detecção. |
| Mosaicos georreferenciados | Disponibilização e visualização espacial dos resultados gerados a partir de imagens GeoTIFF. |
| Download do código-fonte | Acesso aos códigos da plataforma e dos métodos computacionais. |

## 3. Interface do sistema

A navegação do SVC é organizada por meio de quatro opções principais:

- **Início:** acesso à página principal da plataforma.
- **Cadastrar missão:** interface para registro de uma nova missão e associação das imagens correspondentes.
- **Listar missões:** consulta às missões cadastradas e acesso às respectivas funcionalidades.
- **Download SVC:** acesso ao código-fonte da plataforma e dos métodos computacionais.

### 3.1. Cadastro de missões

O cadastro de missões permite registrar as informações de identificação de cada atividade de análise e associar as imagens que serão utilizadas nos processamentos.

Cada missão representa uma unidade de organização dos dados, permitindo manter os arquivos e os resultados vinculados à atividade correspondente.

### 3.2. Listagem e seleção de missões

A listagem apresenta as missões cadastradas e suas informações, incluindo:

- Nome da missão;
- Descrição;
- Quantidade de imagens;
- Pasta associada;
- Data de criação.

Por meio da opção de seleção, o usuário acessa a página específica da missão, onde ficam disponíveis os recursos de processamento e consulta dos resultados.

### 3.3. Processamento de imagens

Na página de uma missão, o usuário pode selecionar o método computacional que deseja executar:

**Segmentação de imagens**

Utiliza modelos de segmentação para gerar máscaras correspondentes às regiões identificadas nas imagens.

**Detecção de objetos e cenários**

Utiliza modelos de detecção para identificar e realizar a anotação dos objetos e cenários presentes nas imagens.

Para imagens GeoTIFF, esse módulo também contempla a extração das coordenadas geográficas dos elementos identificados.

O processamento permite selecionar imagens individualmente ou utilizar os recursos de seleção e desmarcação de todos os arquivos disponíveis na missão.

Antes da execução, o sistema verifica se existe pelo menos uma imagem selecionada e apresenta uma confirmação contendo o método escolhido e a quantidade de arquivos envolvidos.

### 3.4. Galerias de resultados

Após o processamento, os resultados ficam disponíveis em galerias organizadas de acordo com o método computacional utilizado.

A plataforma disponibiliza duas galerias:

- **Galeria de segmentação:** reúne os resultados produzidos pelo modelo de segmentação.
- **Galeria de detecção:** reúne as imagens processadas pelo modelo de detecção de objetos e cenários.

As galerias permitem visualizar individualmente as imagens processadas e consultar os resultados associados à missão selecionada.

### 3.5. Visualização de mosaicos georreferenciados

Para os processamentos de detecção realizados sobre imagens GeoTIFF, o sistema disponibiliza uma seção específica para consulta dos mosaicos georreferenciados gerados.

Os mosaicos podem ser visualizados em uma interface cartográfica, permitindo observar os resultados da detecção sobre imagens de satélite ou bases cartográficas.

Esse recurso possibilita relacionar os objetos e cenários identificados pelo modelo às suas respectivas posições geográficas, contribuindo para a análise espacial dos resultados.

## 4. Métodos computacionais

O SVC integra métodos computacionais independentes e complementares, organizados em módulos específicos de processamento.

### 4.1. Segmentação de imagens

O módulo de segmentação utiliza modelos de Inteligência Artificial para identificar regiões de interesse nas imagens, produzindo máscaras que representam as áreas reconhecidas pelo modelo.

### 4.2. Detecção de objetos e cenários

O módulo de detecção utiliza modelos de Inteligência Artificial para identificar e realizar a anotação dos objetos e cenários presentes nas imagens.

Quando aplicável, especialmente em imagens GeoTIFF, os resultados também podem ser associados a coordenadas geográficas, permitindo sua posterior visualização espacial.

> A descrição detalhada das arquiteturas, dos modelos utilizados, dos parâmetros de treinamento e dos procedimentos de avaliação deve ser apresentada em documentação específica de cada método.

## 5. Fluxo geral de utilização

O fluxo de utilização da plataforma pode ser resumido nas seguintes etapas:

1. Acessar a interface do SVC.
2. Cadastrar uma nova missão.
3. Associar as imagens correspondentes à missão.
4. Consultar e selecionar a missão cadastrada.
5. Escolher o método computacional desejado.
6. Selecionar as imagens que serão processadas.
7. Confirmar e iniciar o processamento.
8. Consultar os resultados nas galerias correspondentes.
9. Acessar os mosaicos georreferenciados, quando disponíveis.

## 6. Tecnologias e arquitetura

Esta seção deverá apresentar as tecnologias utilizadas no desenvolvimento da plataforma e a arquitetura de execução da aplicação.

Serão documentados:

- Linguagens de programação;
- Frameworks e bibliotecas;
- Modelos de Inteligência Artificial;
- Estrutura de armazenamento dos arquivos;
- Serviços de infraestrutura;
- Comunicação entre a interface e os componentes de processamento;
- Fluxo de execução dos métodos computacionais.

## 7. Instalação e execução

As instruções de instalação e execução serão apresentadas de acordo com a estrutura definitiva do projeto e suas dependências.

Esta seção deverá contemplar:

- Pré-requisitos;
- Configuração do ambiente;
- Instalação das dependências;
- Configuração das variáveis de ambiente;
- Disponibilização dos modelos computacionais;
- Inicialização da aplicação;
- Execução dos métodos de processamento.

## 8. Estrutura do repositório

A organização dos diretórios e arquivos será documentada conforme a estrutura efetiva do código-fonte disponibilizado neste repositório.

## 9. Dados e modelos computacionais

Os dados utilizados para treinamento, validação e avaliação dos modelos, assim como os arquivos de pesos dos modelos treinados, deverão possuir suas respectivas descrições e orientações de acesso.

A disponibilização de conjuntos de dados e modelos deverá respeitar as condições de uso, armazenamento e compartilhamento aplicáveis a cada recurso.

## 10. Considerações finais

O SVC constitui uma plataforma de integração dos métodos computacionais desenvolvidos para análise de imagens aéreas, reunindo recursos para gerenciamento de missões, processamento por modelos de Inteligência Artificial, consulta dos resultados e visualização de informações georreferenciadas.

A organização modular permite utilizar os métodos de segmentação e detecção de forma complementar, mantendo os resultados associados às respectivas missões e facilitando sua inspeção e interpretação.

## 11. Autor e desenvolvimento

Projeto desenvolvido no contexto de pesquisa de doutorado na área de Computação, com foco na aplicação de métodos computacionais e Inteligência Artificial para análise de imagens aéreas e identificação de potenciais focos relacionados à proliferação do mosquito *Aedes aegypti*.

**Autor:** Gustavo Araújo

**Projeto:** Sistema de Visão Computacional (SVC)
