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
