## Exercício ID3 - Árvore de Decisão

### a) Escolha da Raiz (Cálculo do Ganho de Informação)

Primeiro, calculamos a **Entropia Geral** do conjunto de dados ($S$), que possui 15 registros (3 Nenhuma, 8 Gelatinosa, 4 Dura).

Fórmula:
$E(S) = - \left(\frac{3}{15}\log_2\frac{3}{15}\right) - \left(\frac{8}{15}\log_2\frac{8}{15}\right) - \left(\frac{4}{15}\log_2\frac{4}{15}\right) = 1,46$

Com base nos cálculos da planilha, os Ganhos de Informação ($IG$) para cada atributo na primeira iteração (utilizando 2 casas decimais) são:

- $IG(\text{Idade}) = 0,05$
- $IG(\text{Diagnóstico}) = 0,01$
- $IG(\text{Astigmatismo}) = 0,09$
- $IG(\text{Taxa Lacrimal}) = 0,49$

**Justificativa:** O atributo **Taxa Lacrimal** é escolhido como o nó raiz da árvore porque apresenta o maior Ganho de Informação ($0,49$), dividindo os dados da melhor forma nesta etapa inicial.

---

### b) Desenvolvimento do Ramo: Taxa lacrimal = reduzida

Para continuar a árvore, filtramos o dataset original apenas para as linhas onde `Taxa lacrimal = reduzida`. Isso nos dá um novo subconjunto ($S_{red}$) de 5 registros: 3 classificados como "Nenhuma", 2 como "Gelatinosa" e 0 como "Dura".

**Entropia deste novo subconjunto ($S_{red}$):**
$E(S_{red}) = - \left(\frac{3}{5}\log_2\frac{3}{5}\right) - \left(\frac{2}{5}\log_2\frac{2}{5}\right) = 0,97$

Agora, calculamos o Ganho de Informação para os atributos restantes dentro deste ramo específico:

**1. Atributo Idade:**

- **jovem** (1 registro: 1 Nenhuma, 0 Gel.): $E = 0,00$
- **pré-presbiopia** (3 registros: 1 Nenhuma, 2 Gel.): $E = 0,92$
- **presbiopia** (1 registro: 1 Nenhuma, 0 Gel.): $E = 0,00$
- $IG(\text{Idade}) = 0,97 - \left(\frac{1}{5} \times 0 + \frac{3}{5} \times 0,92 + \frac{1}{5} \times 0\right) = 0,97 - 0,55 = \mathbf{0,42}$

**2. Atributo Diagnóstico:**

- **miopia** (3 registros: 2 Nenhuma, 1 Gel.): $E = 0,92$
- **hipermetropia** (2 registros: 1 Nenhuma, 1 Gel.): $E = 1,00$
- $IG(\text{Diagnóstico}) = 0,97 - \left(\frac{3}{5} \times 0,92 + \frac{2}{5} \times 1,00\right) = 0,97 - 0,95 = \mathbf{0,02}$

**3. Atributo Astigmatismo:**

- **não** (4 registros: 2 Nenhuma, 2 Gel.): $E = 1,00$
- **sim** (1 registro: 1 Nenhuma, 0 Gel.): $E = 0,00$
- $IG(\text{Astigmatismo}) = 0,97 - \left(\frac{4}{5} \times 1,00 + \frac{1}{5} \times 0\right) = 0,97 - 0,80 = \mathbf{0,17}$

**Resultado Final da Etapa:** O próximo nó de decisão para o ramo `Taxa lacrimal = reduzida` será o atributo **Idade**, pois ele obteve o maior Ganho de Informação local ($0,42$).
