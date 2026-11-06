# 🚌 Caravanas Hub

> A caravana para o torcedor da Alta Paulista ver o jogo, a corrida ou a luta ao vivo — sem dirigir, sem perder o ingresso e sem depender de grupo de WhatsApp.

Professor: [@siriani](https://github.com/siriani)

---

## 1. Nome e frase

**Caravanas Hub** — organize, reserve e vá ao evento com transporte e ingresso garantidos, tudo em um lugar só.

---

## 2. A dor

O torcedor da Alta Paulista quer ver o time, o piloto ou o lutador ao vivo, mas chegar até o estádio ou arena é um problema real:

- Não tem carro ou não quer dirigir horas sozinho
- O transporte público até grandes centros é longo, caro e sem horário de volta garantido
- As caravanas informais são combinadas em grupos de WhatsApp: sem confirmação de vaga, sem ingresso garantido e sem organização de volta
- Quem tenta organizar uma caravana sozinho perde horas no WhatsApp, paga adiantado sem garantia e fica no prejuízo se não fechar o ônibus

**Quem sofre:** torcedores de futebol, fãs de Fórmula 1 e de MMA que moram nas cidades da Alta Paulista e querem ver eventos ao vivo sem a dor de cabeça de organizar tudo.

**Quanto custa hoje:** uma viagem de van informal para São Paulo, sem ingresso, pode custar R$ 80–150 por pessoa, sem nenhuma garantia de volta ou reembolso em caso de cancelamento.

---

## 3. Persona

**Lucas, 23 anos — torcedor apaixonado, sem carro**

- Mora em Marília, torce por um time da capital e acompanha a F1 desde criança
- Trabalha durante a semana e quer usar o fim de semana para ver jogos ao vivo
- Toda vez que um evento grande aparece, entra em cinco grupos de WhatsApp tentando montar caravana
- Já perdeu eventos porque a van não fechou, já comprou ingresso e ficou sem transporte, já voltou de madrugada em condições péssimas
- Pagaria por uma solução que resolvesse transporte e ingresso de uma vez, com confirmação real de vaga

---

## 4. Concorrentes e alternativas

| Alternativa | O que faz | O que faz mal |
|---|---|---|
| Grupos de WhatsApp | Organiza caravanas informais sem custo | Sem garantia de vaga, ingresso ou volta; depende de um organizador voluntário |
| Ônibus fretado de excursão | Transporte organizado | Caro, pouca variedade de eventos, sem ingresso incluso |
| Plataformas oficiais de ingresso | Vende ingresso com segurança | Não resolve o transporte; o torcedor ainda precisa chegar lá |
| Carona entre conhecidos | Barato e flexível | Pouco confiável para eventos com horário de volta definido |

---

## 5. Proposta de valor

Para o torcedor da Alta Paulista que não tem como chegar ao evento, o **Caravanas Hub** é a plataforma que reúne transporte e ingresso num só pacote, com vaga garantida, horário de volta definido e pagamento seguro — diferente das caravanas de WhatsApp, que não garantem nada.

---

## 6. Modelo de receita com Stripe

### Plano Free — gratuito para se cadastrar
- O torcedor cria conta, navega pelas caravanas disponíveis e compra a passagem com ingresso incluso
- O lucro vem da **margem da viagem**: preço da passagem menos combustível, motorista, pedágio e manutenção
- Sem revenda de ingresso acima do valor de face; o ingresso entra no pacote pelo valor oficial

### Plano Pro — R$ 19,90/mês (assinatura via Stripe)
- **Acesso antecipado**: vê e reserva a caravana antes dos usuários Free
- **Cupons de desconto** em caravanas selecionadas
- **Brindes** em eventos especiais (camisas, bandeiras, kits de torcida)
- Quanto mais viagens o assinante fizer, mais ele economiza em relação ao Free

### Receita complementar
- Marcas, lojas de artigos esportivos e bares próximos aos estádios podem patrocinar cupons do plano Pro

---

## 7. Métricas de sucesso

| Métrica | O que indica |
|---|---|
| Cadastros por mês | Crescimento da base |
| Passagens vendidas por evento | Validação da demanda |
| Taxa de ocupação do ônibus | Ponto de equilíbrio financeiro da viagem |
| Assinantes Pro | Receita recorrente (MRR) |
| Retenção mensal do Pro | Satisfação com os benefícios |
| Custo por passageiro por viagem | Saúde financeira da operação |

---

## 8. Lean Canvas

| Bloco | Resposta |
|---|---|
| **Problema** | Torcedores da Alta Paulista não conseguem ir a eventos ao vivo sem carro; caravanas informais não garantem vaga, ingresso nem volta |
| **Segmentos de clientes** | Torcedores de futebol, F1 e MMA da Alta Paulista; primeiros adotantes: grupos de torcida organizados e estudantes universitários |
| **Proposta única de valor** | Caravana com ingresso e transporte num só lugar, vaga garantida e volta combinada |
| **Solução** | Cadastro gratuito, compra de passagem com ingresso, painel de caravanas por evento e data |
| **Canais** | Grupos de torcida no WhatsApp, Instagram local, boca a boca nas primeiras caravanas |
| **Fontes de receita** | Margem da viagem (Free), assinatura Pro via Stripe, patrocínio nos cupons |
| **Estrutura de custos** | Veículos e motoristas, combustível e pedágio, taxas do Stripe, hospedagem (Portainer + MariaDB + MinIO) |
| **Métricas-chave** | Cadastros, passagens vendidas, taxa de ocupação, assinantes Pro, MRR, retenção |
| **Vantagem injusta** | Conhecimento local da Alta Paulista e relacionamento direto com grupos de torcida da região |

---

## Mapa de reaproveitamento da arquitetura

Nada da arquitetura anterior vai pro lixo. Cada peça construída no catálogo de filmes ganha um papel no Caravanas Hub:

| Peça do projeto anterior | O que vira no Caravanas Hub |
|---|---|
| Catálogo de filmes (TMDB) | Catálogo de caravanas: destino, evento, data, horário, vagas disponíveis |
| Microsserviço de login + RBAC | Papéis do negócio: passageiro, organizador (motorista), admin |
| Logs e auditoria (Redis) | Eventos de negócio: "caravana criada", "vaga reservada", "caravana cancelada" |
| Upload e perfil (MinIO) | Arquivos do domínio: foto do ônibus, foto de perfil do passageiro |
| Plano Premium (Stripe) | Plano Pro: acesso antecipado, cupons e brindes |
| Sessões e cookies (MariaDB) | Autenticação e histórico de reservas do passageiro |

---

## Próximas entregas (backlog)

Veja as [issues abertas](../../issues) deste repositório para o roadmap das próximas atividades.