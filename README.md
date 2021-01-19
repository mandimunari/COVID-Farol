# Amanda ImpulsoGov

# Desafio ImpulsoGov | Cientista de Dados 🧪

## Questões

### Projeção subestimada

**1. (descritiva) O SimulaCovid, nosso simulador de demanda hospitalar por leitos enfermaria e UTI, está subestimando o número de internações por Covid-19 em diversos estados brasileiros. Leia com atenção o código fonte disponibilziado neste repositório e as instruções do cálculo de projeção no notebook, e responda: o que pode estar acontecendo?**

O fator que pode estar influenciando na projeção subestimada do número de internações por Covid-19 em diversos estados brasileiros pode ser o fato de que algumas variáveis selecionadas para a construção do modelo de projeção não possuem relação linear. 



**3. (descritiva) Quais são as vantagens e desvantagens dessa solução? (Caso tenha descrito mais de uma solução acima, escolha a mais pertinente) Existe alguma dificuldade dessa solução ser implementada no código da ferramenta?**

A solução seria usar um modelo de regressão não linear, as vantagens de se usá-lo é que enquanto as equações lineares possuem uma forma básica, as equações não-lineares podem assumir muitas formas diferentes; por isso, a regressão não-linear proporciona um ajuste de curva mais flexível, bem como as funções desse tipo de regressão podem ter mais de um parâmetro por variável preditora. Por outro lado, as principais desvantagens estão relacionadas ao fato de que, esse tipo de regressão, permite um número quase infinito de funções possíveis, isso pode gerar uma certa dificuldade de configurá-lo. Além disso, os intervalos de confiança podem ou não ser calculáveis, vai depender do modelo desenvolvido. Adicionalmente, os métodos de inferência são aproximados e requerem procedimentos iterativos de estimação baseados no fornecimento de valores iniciais para os parâmetros. 

A implementação de um modelo de regressão não linear se mostra viável, principalmente pelo fato dos autores Milhinhos & Costa (2020) **(paper disponível em arquivo andditional_material/ActiveCasesUsingNonlinearRegression.pdf)** terem descrito nesse estudo a modelagem da progressão dos casos ativos de Covid em Portugal por meio de regressão não linear. Nesse estudo, os autores optaram pela abordagem de regressão não linear justamente porque os dados do mês de Julho 2020 diferiram muito das indicações positivas do modelo anterior, o qual subestimou o número de casos ativos. No caso deste estudo, foram utilizados os parâmetros do modelo através da estimativa de mínimos quadrados usando o pacote *drc* do R. Além desse pacote, no R existem uma função e um pacote que são utilizadas nesses casos de regressão não linear: (1) a função *nls()*; e (2) o pacote *nlme*. Essas funções e pacotes do R, específicos para regressão não linear, podem ser usadas dentro do python através da biblioteca rpy2. Em vista disso, se mostra possível a integração de modelos de regressão não linear ao código já desenvolvido.
