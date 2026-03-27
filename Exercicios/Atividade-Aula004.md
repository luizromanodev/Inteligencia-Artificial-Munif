## Exercícios - Naive Bayes

### 1. Tabela de Contagens e Probabilidades Suavizadas

| Atributo ($V$)            | Valor         | Classe: Nenhuma (n=3) | Classe: Gelatinosa (n=8) | Classe: Dura (n=4) |
| :------------------------ | :------------ | :-------------------- | :----------------------- | :----------------- |
| **Idade** ($V=3$)         | infantil      | $\frac{2}{6}$         | $\frac{3}{11}$           | $\frac{2}{7}$      |
|                           | adolescente   | $\frac{2}{6}$         | $\frac{3}{11}$           | $\frac{3}{7}$      |
|                           | adulto        | $\frac{2}{6}$         | $\frac{5}{11}$           | $\frac{2}{7}$      |
| **Diagnóstico** ($V=2$)   | miopia        | $\frac{3}{5}$         | $\frac{5}{10}$           | $\frac{3}{6}$      |
|                           | hipermetropia | $\frac{2}{5}$         | $\frac{5}{10}$           | $\frac{3}{6}$      |
| **Astigmatismo** ($V=2$)  | não           | $\frac{3}{5}$         | $\frac{6}{10}$           | $\frac{2}{6}$      |
|                           | sim           | $\frac{2}{5}$         | $\frac{4}{10}$           | $\frac{4}{6}$      |
| **Taxa Lacrimal** ($V=2$) | reduzida      | $\frac{4}{5}$         | $\frac{3}{10}$           | $\frac{1}{6}$      |
|                           | normal        | $\frac{1}{5}$         | $\frac{7}{10}$           | $\frac{5}{6}$      |

### 2. Previsão para o Paciente

**Paciente:** Idade = infantil, Diagnóstico = hipermetropia, Astigmatismo = não, Taxa lacrimal = reduzida.

**Cálculos dos Scores:**

- **Nenhuma:** $\left(\frac{3}{15}\right) \times \left(\frac{2}{6}\right) \times \left(\frac{2}{5}\right) \times \left(\frac{3}{5}\right) \times \left(\frac{4}{5}\right) = 0,01280$
- **Gelatinosa:** $\left(\frac{8}{15}\right) \times \left(\frac{3}{11}\right) \times \left(\frac{5}{10}\right) \times \left(\frac{6}{10}\right) \times \left(\frac{3}{10}\right) \approx 0,01309$
- **Dura:** $\left(\frac{4}{15}\right) \times \left(\frac{2}{7}\right) \times \left(\frac{3}{6}\right) \times \left(\frac{2}{6}\right) \times \left(\frac{1}{6}\right) \approx 0,00212$

**Normalização das Probabilidades:**
0,02801$

- $P(\text{Nenhuma}) = \frac{0,01280}{0,02801} \approx \mathbf{45,70\%}$
- $P(\text{Gelatinosa}) = \frac{0,01309}{0,02801} \approx \mathbf{46,73\%}$
- $P(\text{Dura}) = \frac{0,00212}{0,02801} \approx \mathbf{7,57\%}$
