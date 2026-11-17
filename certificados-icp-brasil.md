# Certificados Digitais da ICP-Brasil — Tipos A, S, T e os novos

## Conceitos rápidos

- **ICP-Brasil:** Infraestrutura de Chaves Públicas Brasileira, criada pela
  **MP 2.200-2/2001**. Documentos assinados com certificado ICP-Brasil
  presumem-se verdadeiros em relação aos signatários.
- **AC Raiz:** o **ITI** (Instituto Nacional de Tecnologia da Informação).
  Fica no topo da cadeia e credencia as demais ACs.
- **AC (Autoridade Certificadora):** emite, renova e revoga certificados.
- **AR (Autoridade de Registro):** faz a **identificação do titular**
  e encaminha o pedido à AC. Não emite certificado.
- **DOC-ICP-04:** norma com os requisitos mínimos de cada tipo de certificado.

## Letras dos tipos

| Letra   | Significado                          |
|---------|--------------------------------------|
| **A**   | **Assinatura** (identidade, assinatura de documentos) |
| **S**   | **Sigilo** (cifrar dados) — *extinto em 2024* |
| **T**   | **Carimbo do tempo** (timestamp)     |
| **SE**  | **Selo Eletrônico** — *novo, 2024*   |
| **AE**  | **Aplicações Específicas** — *novo, 2024* |

O **número** (1 a 4) indica o **nível de segurança**: 1 é o menos rigoroso,
4 o mais rigoroso.

## Tabela clássica (A1–A4 / S1–S4)

É a tabela mais cobrada em provas.

| Tipo      | Mídia armazenadora                              | Geração da chave | Chave (original) | Validade (original) |
|-----------|-------------------------------------------------|------------------|------------------|---------------------|
| **A1/S1** | Repositório protegido por senha (arquivo)        | **Software**     | 1024 bits        | 1 ano               |
| **A2/S2** | Smart card/token **sem** capacidade de gerar chave | **Software**   | 1024 bits        | 2 anos              |
| **A3/S3** | Smart card/token **com** capacidade de gerar chave | **Hardware**   | 1024 bits        | 3 anos              |
| **A4/S4** | Smart card/token com geração de chave ou hardware criptográfico | **Hardware** | **2048 bits** | 3 anos |

**Para memorizar:**
- **1 e 2 → Software** · **3 e 4 → Hardware**
- **A2 x A3:** os dois usam token/smart card. A diferença é que no **A3 a
  chave é gerada dentro do dispositivo**; no A2 é gerada em software e
  depois gravada nele.
- **A3 x A4:** a diferença original é o **tamanho da chave** (1024 x 2048).
- Validade original: 1 · 2 · **3 · 3** (A4 **não** tinha 4 anos)

### Atualizações posteriores

- Validade máxima: **A3 → 5 anos** · **A4 → 6 anos** (ou 11 anos em
  cadeias de curvas elípticas)
- Tamanhos de chave atuais:
  - A1, A2, A3, S1, S2, S3, T3: RSA 1024, RSA 2048 ou ECDSA 256
  - A4, S4, T4: RSA 2048, RSA 4096 ou ECDSA 512

## Mudança de 2024 — Resolução CG ICP-Brasil nº 211

**Extintos:**
- Assinatura **A1** e **A2**
- Sigilo **S1, S2, S3 e S4**

**Criados:**

| Tipo     | Nome                               | Mídia     | Uso                                   |
|----------|------------------------------------|-----------|---------------------------------------|
| **SE-S** | Selo Eletrônico em Software        | Software  | Pessoa jurídica — garantia de origem e integridade |
| **SE-H** | Selo Eletrônico em Hardware        | Hardware  | Idem                                  |
| **AE-S** | Aplicações Específicas em Software | Software  | Equipamentos, servidores, aplicações e IoT |
| **AE-H** | Aplicações Específicas em Hardware | Hardware  | Idem                                  |

> O **selo eletrônico** não pode ser usado como assinatura que
> represente **manifestação de vontade** da pessoa jurídica.

**Os 10 tipos atuais para usuário final:**
A3 · A4 · SE-S · SE-H · T3 · T4 · AE-S · AE-H · A CF-e-SAT · OM-BR

**Validade máxima atual:**

| Tipo                    | Validade |
|-------------------------|----------|
| SE-S e AE-S             | 1 ano    |
| A3, SE-H, AE-H e T3     | 5 anos   |
| A4 e T4                 | 6 anos (11 em curvas elípticas) |
| A CF-e-SAT              | 5 anos   |
| OM-BR                   | 10 anos  |

**Mídia atual:**
- **Software** (repositório protegido por senha e/ou biometria): SE-S e AE-S
- **Hardware criptográfico** homologado: A3, A4, SE-H, T3, T4, AE-H e OM-BR

## Dica de prova

- Questão citando **"A1 a A4 e S1 a S4"** → use a **tabela clássica**
- Questão sobre a **norma atual** → A1, A2 e S1–S4 **extintos**;
  A3 = 5 anos; A4 = 6 anos
- Leia com atenção a **data do edital** e a **data da questão**

## Questões (certo ou errado)

**1.** O certificado do tipo A1 tem a chave gerada por software e
armazenada em repositório protegido por senha.

<details><summary>Gabarito</summary>

**Certo.**
</details>

**2.** Os certificados A2 e A3 são armazenados em token ou smart card, e
ambos geram o par de chaves dentro do dispositivo.

<details><summary>Gabarito</summary>

**Errado.** Só o A3 gera a chave no dispositivo. O A2 gera em software.
</details>

**3.** Na tabela original da ICP-Brasil, a diferença entre os certificados
A3 e A4 era o tamanho da chave: 1024 e 2048 bits, respectivamente.

<details><summary>Gabarito</summary>

**Certo.**
</details>

**4.** A Autoridade de Registro é responsável por emitir e revogar os
certificados digitais.

<details><summary>Gabarito</summary>

**Errado.** Quem emite e revoga é a **AC**. A AR faz a identificação do
titular.
</details>

**5.** Segundo a Resolução CG ICP-Brasil nº 211/2024, os certificados SE-S
e SE-H são certificados de sigilo que substituíram os tipos S1 a S4.

<details><summary>Gabarito</summary>

**Errado.** SE é **Selo Eletrônico**, não sigilo. Os S1 a S4 foram
extintos.
</details>

## Fontes

- [Resolução CG ICP-Brasil nº 211/2024](https://www.normasbrasil.com.br/norma/resolucao-211-2024_468443.html)
- [Resolução CG ICP-Brasil nº 7/2001 (tabela original)](https://mailman.iti.gov.br/images/repositorio/legislacao/resolucoes/revogadas/Resolucao_07.pdf)
- [ITI — Instituto Nacional de Tecnologia da Informação](https://www.gov.br/iti/pt-br)

---
Conteúdo sob licença CC BY 4.0 — Luis Gustavo dos Reis Kort Kamp.
