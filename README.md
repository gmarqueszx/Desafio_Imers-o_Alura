Uma das tarefas mais trabalhosas que eu enfrentava era a distribuição da lista de compensação. Este código automatiza todos os cálculos que eu costumava fazer manualmente, economizando horas de trabalho e aumentando significativamente a minha produtividade.

Este script Python calcula a compensação de energia solar para múltiplos beneficiários de um sistema fotovoltaico. 

**Funcionalidades:**

- Calcula a geração mensal de energia com base na potência do sistema (kWp) e irradiação solar.
- Determina o excedente de energia gerada, subtraindo o consumo da unidade geradora.
- Distribui o excedente entre os beneficiários, proporcionalmente ao consumo de cada um.

**Como funciona:**

1. **Entrada de dados:**
    - `kwp`: Potência do sistema fotovoltaico em kWp.
    - `irradiacao`: Irradiação solar média mensal no local em kWh/m²/mês.
    - `consumo_geradora`: Consumo mensal da unidade geradora em kWh.
    - `beneficiarios`: Dicionário com nome do beneficiário como chave e consumo mensal em kWh como valor.

2. **Cálculo da geração mensal:**
    - `geracao_mensal = kwp * irradiacao`

3. **Cálculo do excedente:**
    - `excedente = geracao_mensal - consumo_geradora`

4. **Cálculo da compensação:**
    - Itera sobre o dicionário `beneficiarios`.
    - Para cada beneficiário:
        - Calcula a porcentagem do consumo em relação ao consumo total dos beneficiários.
        - Armazena a porcentagem no dicionário `compensacao`, com o nome do beneficiário como chave.

5. **Saída:**
    - Imprime um relatório com a porcentagem de compensação para cada beneficiário.

**Exemplo:**
```python
kwp = 11.4  # kWp
irradiacao = 130  # kWh/m²/mês
consumo_geradora = 120  # kWh
beneficiarios = {
    "B1": 100,  # kWh
    "B2": 200,  # kWh
    "B3": 50   # kWh
}
compensacao = calcular_compensacao(kwp, irradiacao, consumo_geradora, beneficiarios)
print("-" * 30)
print("Compensação de Energia Solar")
print("-" * 30)
for beneficiario, percentual in compensacao.items():
    print(f"{beneficiario:<15}: {percentual:6.2f}%")
print("-" * 30)

Resultado:
------------------------------
Compensação de Energia Solar
------------------------------
Beneficiário 1   :  27.03%
Beneficiário 2   :  54.05%
Beneficiário 3   :  13.51%
------------------------------
