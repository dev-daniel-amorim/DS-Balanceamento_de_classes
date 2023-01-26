# Balanceamento de classes
Classes desbalanceadas são aquelas classes discretas que queremos prever que possuem muitos valores de um tipo (majoritária) e sua classe oposta possui poucos exemplos (minoritária), onde o algoritimo vai aprender muito sobre um e pouco sobre a outra trazendo um viés negativo para predição.<br>

Calcular a acurácia de uma classe desbalanceada é como enxugar gelo, pois o modelo pode "chutar" que uma transação não é "fraudulenta" e acertar 99% das vezes mas no deploy, com dados reais, essa realidade pode ser cruel e trazer prejuizos. Vamos entender a seguir.

Exemplo de classes desbalanceadas: <br>
* Imagine uma variável alvo com classes negativas = não fraude, e positiva = fraude onde:<br>

- 99% não são fraudes
- 1% são fraudes

![Captura](https://user-images.githubusercontent.com/115194365/213556359-bde17c25-012f-4996-a9e8-8aab6075b54f.jpg)

Tabela de grau de desiquilibrio:

| Grau de desequilibrio | Proporção das classes minoritárias |
|-----------------------|------------------------------------|
| Leve                  | 20 a 40% dos dados                 |
| Moderado              | 01 a 20% dos dados                 |
| Extrema               | < 1%     dos dados                 |


Notamos claramente o desbalanceamento extremo. Isso pode implicar no nosso modelo "viciar" em prever somente ações que não são fraudes. Muito cuidado com isso, um modelo com classes desbalanceadas podem ter uma acuracia altissima pois em 99% dos casos ele vai acertar causando overfitting (acerto elevado dos dados).

# Tipos de balanceamentos
É muito comum encontrarmos classes desbalanceadas, mas pra isso existem algumas tecnicas de balanceamento:
    
## Undersampling
Consiste em reduzir de forma aleatória o volume de dados da classe majoritária, causando perda de dados que podem ser importantes deixando nosso modelo enfraquecido, 
        
* NearMiss é um modelo de balanceamento undersampling.
* Biblioteca:

        from imblearn.under_sampling import NearMiss

        
## Oversampling
Replica dados da classe minoritária para manter igualdade entre a classe maioritária procurando caracteristicas dos dados vizinhos, mas atenção, pode causar overfitting (acerto elevado dos dados). O ajuste excessivo é um comportamento indesejável de aprendizado de máquina que ocorre quando o modelo de aprendizado fornece previsões precisas para dados de treinamento, mas não para novos dados.
        
* Smote é um modelo de balanceamento oversampling.
* Biblioteca:

        from imblearn.over_sampling import SMOTE
<br>

![smote](https://user-images.githubusercontent.com/115194365/213033541-39484a5f-6085-4d51-870a-fff62caa5e5e.jpg)

 
 ## Engenharia de features
 Consiste na geração de novas features para dar mais robustez e melhorar a classe minoritária, porém esse método demanda tempo e aumenta significativamente os custos do projeto.

## Projeto
<a href='https://github.com/dev-daniel-amorim/DS-Balanceamento_de_classes/blob/main/Balanceamento%20de%20classes.ipynb'> Clique aqui para ir para o projeto de balanceamento de classes! </a> 
