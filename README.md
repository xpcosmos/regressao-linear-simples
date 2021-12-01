# Regressão Linear - Pedição de preços de casa
O objetivo desse projeto é demonstrar entendimento de técnicas de regressão linear utilizando Sklearn/Skit-learn.

## Visualização dos dados:

### Verificando primeiros registros

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right">
      <th></th>
      <th>precos</th>
      <th>area</th>
      <th>garagem</th>
      <th>banheiros</th>
      <th>lareira</th>
      <th>marmore</th>
      <th>andares</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>51875</td>
      <td>25</td>
      <td>3</td>
      <td>4</td>
      <td>3</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>17875</td>
      <td>35</td>
      <td>1</td>
      <td>3</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>47075</td>
      <td>195</td>
      <td>2</td>
      <td>4</td>
      <td>2</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>38575</td>
      <td>33</td>
      <td>2</td>
      <td>2</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>33775</td>
      <td>11</td>
      <td>2</td>
      <td>3</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>

### Verificando colunas de dados:

* Precos
* Area
* Garagem
* Banheiros
* Lareira
* Marmore
* Andares

## Análise descritiva de dados
### Descrições gerais:
<table border="0" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Precos</th>
      <th>Area</th>
      <th>Garagem</th>
      <th>Banheiros</th>
      <th>Lareira</th>
      <th>Marmore</th>
      <th>Andares</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Contagem</th>
      <td>1000.00</td>
      <td>1000.00</td>
      <td>1000.00</td>
      <td>1000.00</td>
      <td>1000.00</td>
      <td>1000.00</td>
      <td>1000.00</td>
    </tr>
    <tr>
      <th>Média</th>
      <td>41985.60</td>
      <td>124.33</td>
      <td>2.01</td>
      <td>3.00</td>
      <td>2.03</td>
      <td>0.33</td>
      <td>0.48</td>
    </tr>
    <tr>
      <th>Desvio padrão</th>
      <td>12140.39</td>
      <td>72.39</td>
      <td>0.81</td>
      <td>1.43</td>
      <td>1.42</td>
      <td>0.47</td>
      <td>0.50</td>
    </tr>
    <tr>
      <th>Mínimo</th>
      <td>13150.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>Percentil (25%)</th>
      <td>33112.50</td>
      <td>60.75</td>
      <td>1.00</td>
      <td>2.00</td>
      <td>1.00</td>
      <td>0.00</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>Percentil (50%)</th>
      <td>41725.00</td>
      <td>123.00</td>
      <td>2.00</td>
      <td>3.00</td>
      <td>2.00</td>
      <td>0.00</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>Percentil (75%)</th>
      <td>51175.00</td>
      <td>187.00</td>
      <td>3.00</td>
      <td>4.00</td>
      <td>3.00</td>
      <td>1.00</td>
      <td>1.00</td>
    </tr>
    <tr>
      <th>Máximo</th>
      <td>73675.00</td>
      <td>249.00</td>
      <td>3.00</td>
      <td>5.00</td>
      <td>4.00</td>
      <td>1.00</td>
      <td>1.00</td>
    </tr>
  </tbody>
</table>

### Distribuição de preços:

![fig_1](https://github.com/xpcosmos/regressao-linear-simples/blob/main/assets/fig_1.png)

### Tabela de correlação de dados:

<table border="0" class="dataframe">
  <thead>
    <tr style="text-align: right">
      <th></th>
      <th>precos</th>
      <th>area</th>
      <th>garagem</th>
      <th>banheiros</th>
      <th>lareira</th>
      <th>marmore</th>
      <th>andares</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>precos</th>
      <td>1.000000</td>
      <td>0.117689</td>
      <td>0.102752</td>
      <td>0.124390</td>
      <td>0.107209</td>
      <td>0.430767</td>
      <td>0.631529</td>
    </tr>
    <tr>
      <th>area</th>
      <td>0.117689</td>
      <td>1.000000</td>
      <td>-0.007530</td>
      <td>-0.011374</td>
      <td>0.012114</td>
      <td>-0.015270</td>
      <td>-0.018006</td>
    </tr>
    <tr>
      <th>garagem</th>
      <td>0.102752</td>
      <td>-0.007530</td>
      <td>1.000000</td>
      <td>0.067142</td>
      <td>0.060455</td>
      <td>-0.015629</td>
      <td>-0.020588</td>
    </tr>
    <tr>
      <th>banheiros</th>
      <td>0.124390</td>
      <td>-0.011374</td>
      <td>0.067142</td>
      <td>1.000000</td>
      <td>0.048363</td>
      <td>-0.025281</td>
      <td>-0.018203</td>
    </tr>
    <tr>
      <th>lareira</th>
      <td>0.107209</td>
      <td>0.012114</td>
      <td>0.060455</td>
      <td>0.048363</td>
      <td>1.000000</td>
      <td>0.029591</td>
      <td>-0.003513</td>
    </tr>
    <tr>
      <th>marmore</th>
      <td>0.430767</td>
      <td>-0.015270</td>
      <td>-0.015629</td>
      <td>-0.025281</td>
      <td>0.029591</td>
      <td>1.000000</td>
      <td>-0.006527</td>
    </tr>
    <tr>
      <th>andares</th>
      <td>0.631529</td>
      <td>-0.018006</td>
      <td>-0.020588</td>
      <td>-0.018203</td>
      <td>-0.003513</td>
      <td>-0.006527</td>
      <td>1.000000</td>
    </tr>
  </tbody>
</table>

### Gráfico de regressão:

![fig_2](https://github.com/xpcosmos/regressao-linear-simples/blob/main/assets/fig_2.png)

Verificamos uma alta correlação entre a acabamento em mármore e andares em relação ao preço dos imóveis. Vamos verificar como essas características variam em relação ao preço:
<br><br>
<a><img src="https://github.com/xpcosmos/regressao-linear-simples/blob/main/assets/fig_6.png" alt="fig_6" width="450"></a>
<a><img src="https://github.com/xpcosmos/regressao-linear-simples/blob/main/assets/fig_7.png" alt="fig_7" width="450"></a><br>

### Relação Entre área e preço:

![fig_8](https://github.com/xpcosmos/regressao-linear-simples/blob/main/assets/fig_8.png)

Temos uma regressão positiva.

### Categorizando preço de imóveis:

#### Tebela de distribuição:

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right">
      <th></th>
      <th>Frequência (qnt)</th>
      <th>Frequência (%)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>35159.091 -  40661.364</th>
      <td>166</td>
      <td>16.6</td>
    </tr>
    <tr>
      <th>46163.636 - 51665.909</th>
      <td>151</td>
      <td>15.1</td>
    </tr>
    <tr>
      <th>40661.364 - 46163.636</th>
      <td>141</td>
      <td>14.1</td>
    </tr>
    <tr>
      <th>29656.818 - 35159.091</th>
      <td>134</td>
      <td>13.4</td>
    </tr>
    <tr>
      <th>51665.909 - 57168.182</th>
      <td>131</td>
      <td>13.1</td>
    </tr>
    <tr>
      <th>24154.545 - 29656.818</th>
      <td>100</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>57168.182 - 62670.455</th>
      <td>57</td>
      <td>5.7</td>
    </tr>
    <tr>
      <th>18652.273 - 24154.545</th>
      <td>49</td>
      <td>4.9</td>
    </tr>
    <tr>
      <th>62670.455 - 68172.727</th>
      <td>38</td>
      <td>3.8</td>
    </tr>
    <tr>
      <th>13089.474 - 18652.273</th>
      <td>23</td>
      <td>2.3</td>
    </tr>
    <tr>
      <th>68172.727 - 73675.0</th>
      <td>10</td>
      <td>1.0</td>
    </tr>
  </tbody>
</table>


#### Visualização gráfica:

![fig_11](https://github.com/xpcosmos/regressao-linear-simples/blob/main/assets/fig_11.png)

#### Guia de categoria:

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right">
      <th></th>
      <th>Categoria</th>
    </tr>
    <tr>
      <th>Correspondente</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>35159.091 -  40661.364</td>
    </tr>
    <tr>
      <th>2</th>
      <td>46163.636 - 51665.909</td>
    </tr>
    <tr>
      <th>3</th>
      <td>40661.364 - 46163.636</td>
    </tr>
    <tr>
      <th>4</th>
      <td>29656.818 - 35159.091</td>
    </tr>
    <tr>
      <th>5</th>
      <td>51665.909 - 57168.182</td>
    </tr>
    <tr>
      <th>6</th>
      <td>24154.545 - 29656.818</td>
    </tr>
    <tr>
      <th>7</th>
      <td>57168.182 - 62670.455</td>
    </tr>
    <tr>
      <th>8</th>
      <td>18652.273 - 24154.545</td>
    </tr>
    <tr>
      <th>9</th>
      <td>62670.455 - 68172.727</td>
    </tr>
    <tr>
      <th>10</th>
      <td>13089.474 - 18652.273</td>
    </tr>
    <tr>
      <th>11</th>
      <td>68172.727 - 73675.0</td>
    </tr>
  </tbody>
</table>

## Modelo de regressão:

### Coeficiente de estimação:
R² = 0.64

### Exemplos de dados estimados:

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right">
      <th></th>
      <th>Real</th>
      <th>Previsto</th>
      <th>Diferença</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>53375</td>
      <td>50619.33</td>
      <td>-2755.67</td>
    </tr>
    <tr>
      <th>1</th>
      <td>40975</td>
      <td>44605.39</td>
      <td>3630.39</td>
    </tr>
    <tr>
      <th>2</th>
      <td>26350</td>
      <td>32787.95</td>
      <td>6437.95</td>
    </tr>
    <tr>
      <th>3</th>
      <td>27950</td>
      <td>31133.66</td>
      <td>3183.66</td>
    </tr>
    <tr>
      <th>4</th>
      <td>31650</td>
      <td>29823.02</td>
      <td>-1826.98</td>
    </tr>
  </tbody>
</table>

## Considerações finais:

Fizemos um modelo de regressão com um coeficiente de regressão relativamente alta e predições consideravalmente precisas.<br>
Para aumentar o coeficiente precisaríamos de mais dados e mais detalhes dos imóveis.


# Tecnologias utilizadas

* Python
* VS CODE
* Jupyter Notebook
* Numpy
* Pandas
* Sklearn
* Seaborn
* Matplotlib

# Autor

<a href="https://www.linkedin.com/in/mikeias-o-5a4b2a184/"><img src="https://github.com/xpcosmos/simulador-de-dados/blob/main/assets/linkedin.png" alt="linkedin" width="20"></a> <a href="mailto:mikeias.d.s.o@gmail.com"><img src="https://github.com/xpcosmos/simulador-de-dados/blob/main/assets/gmail.png" alt="gmail" width="20">

# Licença

MIT License

Copyright (c) 2021 xpcosmos

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
