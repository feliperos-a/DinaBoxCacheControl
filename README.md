# DinaBox CACHE CONTROL

Extensão para **SketchUp**, desenvolvida por **Felipe Rosa**, para monitorar e limpar automaticamente arquivos temporários gerados pelo DinaBox.

O objetivo é manter o cache sob acompanhamento enquanto você trabalha, reduzindo a necessidade de acionar manualmente a lixeira e ajudando a evitar problemas relacionados ao acúmulo de arquivos temporários.

Atualmente, o plugin está disponível em **duas versões**, com o mesmo objetivo e funcionalidades principais, mas com diferenças na apresentação das informações e na otimização do processamento.

## Versões disponíveis

### V1.0.1 — Otimizada (Recomendada)

Versão desenvolvida com foco em **desempenho, leveza e menor consumo de recursos do SketchUp**.

**Melhorias:**
- Remoção do gráfico e do histórico detalhado de limpezas.
- Exibição simplificada da quantidade de arquivos removidos na última limpeza.
- Redução de verificações e leituras redundantes.
- Otimização da atualização das informações do painel.
- Eliminação das gravações contínuas do histórico de limpezas.
- Preservação do monitoramento automático e dos intervalos configurados.
- Manutenção da identidade visual, dos controles e das funcionalidades principais.

**Indicada para:** usuários que preferem uma extensão mais leve, com interface simplificada e foco exclusivo no monitoramento e na limpeza automática.

### V1.0.0 — Original (Com gráfico)

Primeira versão oficial, com painel de acompanhamento e histórico das limpezas realizadas.

**Recursos exclusivos:**
- Gráfico interativo com as últimas 24 limpezas registradas.
- Visualização da quantidade de arquivos removidos em cada operação.
- Informações de data e horário ao passar o mouse sobre os registros.
- Histórico local persistente, mantido entre sessões do SketchUp.

**Indicada para:** usuários que desejam acompanhar visualmente a frequência das limpezas e consultar registros anteriores.

> **Importante:** as duas versões realizam o monitoramento e a limpeza automática. A V1.0.1 foi otimizada para reduzir operações desnecessárias, mas isso não garante a eliminação de eventuais travamentos do SketchUp.

## Funcionalidades

Presentes nas duas versões:

- Monitoramento das pastas `DinaBox/componentes` e `DinaBox/materiais`.
- Detecção de arquivos temporários gerados durante o uso do DinaBox.
- Limpeza automática de arquivos que permanecem estáveis pelo período configurado.
- Ajustes de **verificação** e **estabilidade**, em segundos.
- Notificações em dois modos: **Alerta nativo** ou **Silencioso**.
- Botão **Limpar agora**, para executar a limpeza manual com confirmação.
- Contagem de arquivos atualmente presentes no cache.
- Monitoramento em funcionamento mesmo com o painel fechado.
- Interface integrada ao SketchUp.

## Instalação

1. Acesse os arquivos disponíveis neste repositório.
2. Escolha a versão desejada:
   - **V1.0.1:** arquivo `.rbz` identificado como versão otimizada.
   - **V1.0.0:** arquivo `DinaBoxCacheControl-v1.0.0-FelipeRosa.rbz`.
3. Baixe o arquivo `.rbz` da versão escolhida.
4. Abra o SketchUp e acesse **Janela → Gerenciador de Extensões**.
5. Clique em **Instalar extensão** e selecione o arquivo baixado.
6. Reinicie o SketchUp, se necessário.
7. Abra o **DinaBox CACHE CONTROL** pela barra de ferramentas ou pelo menu **Extensões**.

**O arquivo `.rbz` é o instalador completo.** Ele já inclui os ícones da barra de ferramentas, o código Ruby e toda a interface (HTML, CSS e JavaScript).

Não é necessário copiar arquivos ou pastas manualmente.

### Atualização e troca de versões

As duas edições pertencem à mesma extensão. Portanto, **não devem ser instaladas como plugins independentes**.

Para atualizar da V1.0.0 para a V1.0.1, instale o arquivo da versão otimizada e reinicie o SketchUp.

Caso queira retornar à versão com gráfico, reinstale a V1.0.0.

As preferências existentes podem ser preservadas entre as versões.

## Como usar

O monitoramento inicia automaticamente quando está habilitado.

No painel, você pode configurar:

- **Verificação:** frequência de consulta das pastas, de 1 a 60 segundos.
- **Estabilidade:** tempo mínimo de espera antes da exclusão automática, de 3 a 120 segundos.
- **Notificações:** escolha entre avisos nativos do SketchUp e modo silencioso.
- **Monitoramento:** ativar ou pausar a limpeza automática.
- **Limpar agora:** executar uma limpeza manual dos arquivos elegíveis.

Em instalações novas, os valores iniciais previstos são **2 segundos de verificação** e **5 segundos de estabilidade**. Preferências já salvas no SketchUp podem manter valores diferentes.

**O modo Silencioso desativa apenas os avisos, não a limpeza automática.**

## Histórico e informações de limpeza

**Na V1.0.0:**

O painel apresenta as 24 limpezas mais recentes registradas pelo plugin.

Os registros são armazenados localmente no arquivo `DinaBoxCacheControl/cleanup_history.jsonl`, na pasta de dados do SketchUp, fora do diretório da extensão.

O gráfico utiliza apenas registros efetivamente coletados e começa vazio até ocorrerem novas limpezas.

**Na V1.0.1:**

O gráfico foi removido e substituído pela quantidade de arquivos removidos na última limpeza.

O histórico detalhado deixa de ser utilizado, evitando leituras e gravações desnecessárias. Os registros antigos da V1.0.0 não são utilizados pela edição otimizada.

## Cuidados e limitações

O plugin atua apenas sobre arquivos comuns diretamente dentro das duas pastas monitoradas. Não percorre subpastas nem remove links simbólicos.

Antes de apagar um arquivo automaticamente, verifica se suas informações permanecem estáveis pelo período configurado.

Essas verificações **não garantem** que o DinaBox tenha liberado internamente todos os arquivos.

Recomenda-se testar inicialmente com uma cópia do projeto e ajustar o tempo de estabilidade conforme a necessidade.

O desempenho pode variar de acordo com o computador, a quantidade de arquivos temporários e as demais extensões instaladas no SketchUp.

## Desenvolvedor

**Felipe Rosa**  
GitHub: [@feliperos-a](https://github.com/feliperos-a)

**Projeto:** [DinaBoxCacheControl](https://github.com/feliperos-a/DinaBoxCacheControl)

**Versões disponíveis:**
- **V1.0.1 — Otimizada (Recomendada)**
- **V1.0.0 — Original (Com gráfico)**
