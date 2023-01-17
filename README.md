# Balanceamento de classes
Classes desbalanceadas são quando uma representação de classe com muitos valores de um tipo (majoritária ou minoritária) e sua classe oposta possui poucos exemplos, onde o algoritimo vai aprender muito sobre um e pouco sobre a outra trazendo um viés negativo para predição.<br>

* Exemplo: Coluna detecção de fraude:<br>
- 90% não são fraudes
- 10% são fraudes

# Tipos de balanceamentos
É muito comum encontrarmos classes desbalanceadas, mas pra isso existem algumas tecnicas de balanceamento:
    
## Undersampling
Consiste em reduzir de forma aleatória o volume de dados da classe majoritária, causando perda de dados que podem ser importantes deixando nosso modelo enfraquecido.
        
## NearMiss
Consiste em reduzir de forma aleatória o volume de dados da classe majoritária, porém buscando reduzir os dados que se aproximam da classe minoritária, causando tbm perda de dados.
        
## Oversampling
Replica dados da classe minoritária para manter igualdade entre os dados mas pode causar overfit (O ajuste excessivo é um comportamento indesejável de aprendizado de máquina que ocorre quando o modelo de aprendizado fornece previsões precisas para dados de treinamento, mas não para novos dados).
        
## Smote
Procura caracteristicas dos dados vizinhos para criar novos dados sem replica-los, efetuando cálculos e criando assim novos dados.<br>
 ![smote](https://user-images.githubusercontent.com/115194365/212982317-a3fc43b4-d2a9-4e4e-8412-b1372bacc4aa.jpg)<br>

