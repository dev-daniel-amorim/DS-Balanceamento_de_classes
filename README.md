# Balanceamento de classes
Classes desbalanceadas são quando uma representação de classe com muitos valores de um tipo (majoritária ou minoritária) e sua classe oposta possui poucos exemplos, onde o algoritimo vai aprender muito sobre um e pouco sobre a outra trazendo um viés negativo para predição.<br>

Exemplo de classes desbalanceadas: <br>
* Imagine uma coluna "detecção de fraude" com classes 0 = não fraude, e 1 = fraude onde:<br>
- 90% não são fraudes
- 10% são fraudes

Notamos claramente o desbalanceamento, onde a classe majoritária 0 tem 90% de exemplos de operações não fraudulentas contra 10% de exemplos de fraude (1). Isso pode implicar no nosso modelo "viciar" em prever somente ações que não são fraudes.

# Tipos de balanceamentos
É muito comum encontrarmos classes desbalanceadas, mas pra isso existem algumas tecnicas de balanceamento:
    
## Undersampling
Consiste em reduzir de forma aleatória o volume de dados da classe majoritária, causando perda de dados que podem ser importantes deixando nosso modelo enfraquecido, 
        
* NearMiss é um modelo de balanceamento undersampling.
* Biblioteca:

        from imblearn.under_sampling import NearMiss

        
## Oversampling
Replica dados da classe minoritária para manter igualdade entre os dados procurando caracteristicas dos dados vizinhos, mas pode causar overfit (O ajuste excessivo é um comportamento indesejável de aprendizado de máquina que ocorre quando o modelo de aprendizado fornece previsões precisas para dados de treinamento, mas não para novos dados).
        
* Smote é um modelo de balanceamento oversampling.
* Biblioteca:

        from imblearn.over_sampling import SMOTE
<br>

![smote](https://user-images.githubusercontent.com/115194365/213033541-39484a5f-6085-4d51-870a-fff62caa5e5e.jpg)

 
 ## Engenharia de features
 Consiste na geração de novas features para dar mais robustez e melhorar a classe minoritária, porém esse método demanda tempo e aumenta significativamente os custos do projeto.

## Projeto
<a href='https://github.com/dev-daniel-amorim/DS-Balanceamento_de_classes/blob/main/Balanceamento%20de%20classes.ipynb'> Clique aqui para ir para o projeto de balanceamento de classes! </a> 
