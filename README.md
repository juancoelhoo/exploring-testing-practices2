# Explorando Práticas de Teste

Neste exercício, vamos explorar práticas de teste em sistemas reais utilizando a ferramenta [TestMiner](https://andrehora.github.io/testminer).

O TestMiner permite visualizar e analisar testes de software em repositórios do GitHub, fornecendo dados sobre como os projetos organizam seus testes, como eles evoluem entre versões e quais bibliotecas de teste são utilizadas.
Explore a ferramenta antes de começar para se familiarizar com seu funcionamento.

Mais detalhes no GitHub da ferramenta: https://github.com/andrehora/testminer.

---

## Passo 1: Selecionar DOIS repositórios

Escolha dois repositórios reais que possuam testes de software.
Abaixo estão alguns links para ajudá-lo a encontrar projetos interessantes:

- Python: https://github.com/topics/python?l=python
- JavaScript: https://github.com/topics/javascript?l=javascript
- TypeScript: https://github.com/topics/typescript?l=typescript
- Java: https://github.com/topics/java?l=java

- Tópicos: [ai](https://andrehora.github.io/testminer/#topic:ai), [llm](https://andrehora.github.io/testminer/#topic:llm), [api](https://andrehora.github.io/testminer/#topic:api), [nodejs](https://andrehora.github.io/testminer/#topic:nodejs), [android](https://andrehora.github.io/testminer/#topic:android)

- Por organização: [Google](https://andrehora.github.io/testminer/#google), [Microsoft](https://andrehora.github.io/testminer/#microsoft), [Apple](https://andrehora.github.io/testminer/#apple), [Facebook](https://andrehora.github.io/testminer/#facebook), [Netflix](https://andrehora.github.io/testminer/#netflix), 
[GitHub](https://andrehora.github.io/testminer/#github), [Apache](https://andrehora.github.io/testminer/#apache), [HuggingFace](https://andrehora.github.io/testminer/#huggingface)

## Passo 2: Explorar os repositórios selecionados

Busque os repositórios escolhidos no [TestMiner](https://andrehora.github.io/testminer) e analise os dados de teste gerados pela ferramenta.

## Passo 3: Explicar as prática de teste

Para cada repositório, escolha uma prática ou dado de teste relevante e explique com suas próprias palavras.

---

## Instruções de entrega

1. Faça um `fork` deste repositório (saiba mais sobre forks [aqui](https://docs.github.com/pt/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo)).
2. Responda às questões abaixo diretamente neste arquivo `README.md` do seu fork. Pode adicionar imagens para enriquecer sua explicação.
3. No Moodle, submeta apenas a URL do seu fork.

---

## Respostas

### Repositório 1 

Repositório: https://github.com/pallets/flask
URL TestMiner: https://andrehora.github.io/testminer/#pallets/flask
Explicação: O Flask mantém a maior parte de seus testes em um diretório próprio,
tests, separado do código da biblioteca, que fica em src/flask. Um dado que
notei no TestMiner é a distinção entre arquivos de teste e arquivos
auxiliares porque, na versão analisada, a ferramenta classificou 36 arquivos como
testes e 35 como test helpers. Entre esses auxiliares existem modelos HTML,
arquivos de configuração e outros dados usados durante a execução dos testes.
Essa organização evita repetir a preparação de cenários em cada caso de teste e
deixa as verificações mais focadas no comportamento esperado. O repositório
também tem exemplos com seus próprios testes, ajudando a validar não só a
biblioteca principal, mas também a forma recomendada de a utilizar. Como o
TestMiner classifica os arquivos automaticamente a partir de seus nomes e
caminhos, esses números devem ser entendidos como uma visão geral da estrutura,
e não como a quantidade exata de funções de teste executadas.

### Repositório 2

Repositório: https://github.com/pallets/itsdangerous
URL TestMiner: https://andrehora.github.io/testminer/#pallets/itsdangerous
Explicação: O ItsDangerous é uma biblioteca pequena para assinar dados de forma
segura. Na versão analisada, o TestMiner identificou cinco módulos de teste no
diretório tests/test_itsdangerous: test_encoding.py, test_serializer.py,
test_signer.py, test_timed.py e test_url_safe.py. Essa divisão demonstra
uma prática importante: organizar a suíte de acordo com as responsabilidades
do sistema. Assim, os testes de codificação, serialização, assinatura, validade
por tempo e geração de valores seguros para URL ficam separados, facilitando a
localização de falhas e a manutenção da suíte. A ferramenta também identificou
o arquivo .github/workflows/tests.yaml, indicando que os testes fazem parte
da integração contínua e podem ser executados automaticamente a cada mudança.
Embora seja um projeto bem menor, ele mantém testes para seus principais
comportamentos, algo especialmente relevante em uma biblioteca relacionada à
segurança e à integridade de dados. As quantidades apresentadas são resultado
da classificação automática do TestMiner e não representam o número de funções
ou cenários executados dentro de cada arquivo.
