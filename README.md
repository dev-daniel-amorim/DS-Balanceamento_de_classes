# Balanceamento de classes
Classes desbalanceadas são aquelas classes discretas que queremos prever que possuem muitos valores de um tipo (majoritária) e sua classe oposta possui poucos exemplos (minoritária), onde o algoritimo vai aprender muito sobre um e pouco sobre a outra trazendo um viés negativo para predição.<br>

Calcular a acurácia de uma classe desbalanceada é como enxugar gelo, pois o modelo pode "chutar" que uma transação não é "fraudulenta" e acertar 99% das vezes, mas no deploy com dados reais, essa realidade pode ser cruel e trazer prejuizos.

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


Notamos claramente o desbalanceamento extremo, isso pode implicar no nosso modelo "viciar" em prever somente ações que não são fraudes. Muito cuidado com isso, um modelo com classes desbalanceadas podem ter uma acurácia altissima pois em 99% dos casos ele vai acertar causando overfitting (acerto elevado dos dados).

# Tipos de balanceamentos
É muito comum encontrarmos classes desbalanceadas, mas pra isso existem algumas técnicas para tratar essas classes, são elas:
    
## Undersampling
Consiste em reduzir de forma aleatória e artificial o volume de dados da classe majoritária, causando perda de dados que podem ser importantes deixando nosso modelo enfraquecido.
        
* NearMiss é um modelo de balanceamento undersampling.
* Biblioteca:

        from imblearn.under_sampling import NearMiss

        
## Oversampling
Aumenta artificialmente o número de classes minoritárias para igualar a classe majoritária.

Replica dados da classe minoritária para manter igualdade entre a classe majoritária procurando caracteristicas dos dados vizinhos, mas atenção, pode causar underfitting (erro elevado dos dados). O ajuste excessivo é um comportamento indesejável de aprendizado de máquina que ocorre quando o modelo de aprendizado fornece previsões precisas para dados de treinamento, mas não para novos dados.
        
* SMOTE (Synthetic Minority Over-sampling Technique).
* Copia e cola a classe minoritária para igualar a classe majoritária fazendo com que ela não tenha "preferência".
* Biblioteca:

        from imblearn.over_sampling import SMOTE
<br>

![smote](https://user-images.githubusercontent.com/115194365/213033541-39484a5f-6085-4d51-870a-fff62caa5e5e.jpg)

#### ⚠️ Muito cuidado com essa técnica!
- Uma dica importante, é que pode melhorar e muito acurácia do seu modelo é não fazer o balanceamento de classes antes do cross validation.
-  O problema está na validação, pois no momento em que igualamos artificilmente as classes e aumentamos a classe minoritária estamos dizendo que em tese, 50% sao "fraude" e 50% "não fraude" o que foge da realidade do mundo real, onde no mundo real há menos "transações fraudulentas" do que "não fraudulentas". Resumindo, já começariamos distorcendo o mundo real e ensinando errado ao nosso modelo.
-  Ao fazer o CV, o split de treino pode ter as classes já balanceadas, mas a validação onde vamos testar os dados não pode estar balanceada, ou seja, não pode fugir da realidade do mundo real.
-  Erro comum, balancear tudo antes do CV vai separar tudo (treino, validação e teste) já balanceado. ERRADO!
- O balanceamento deve ser feito SOMENTE nos splits de treino e não na validação.

#### ✅ Solução
- Criar os splits e realizar CV somente na base de treino! (faremos uma função para isso no notebook)

## Class weight
Da pesos diferentes para cada classe com base na sua proporção.

 
## Engenharia de features
Consiste na geração de novas features para dar mais robustez e melhorar a classe minoritária, porém esse método demanda tempo e aumenta significativamente os custos do projeto.

# Notebook
[Clique aqui para ver o notebook dessa aula](https://github.com/dev-daniel-amorim/DS-Balanceamento_de_classes/blob/main/Balanceamento%20de%20classes.ipynb)
<br>
<hr>

[<< Voltar para página inicial](https://github.com/dev-daniel-amorim)
