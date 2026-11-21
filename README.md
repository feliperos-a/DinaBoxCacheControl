# DinaBox CACHE CONTROL

Extensão para **SketchUp** desenvolvida por **Felipe Rosa** para monitorar e limpar automaticamente arquivos temporários gerados pelo DinaBox.

O objetivo é manter o cache sob acompanhamento enquanto você trabalha, sem precisar acionar manualmente a lixeira a cada operação.

## Funcionalidades

- Monitoramento das pastas `DinaBox/componentes` e `DinaBox/materiais`.
- Limpeza automática de arquivos que permanecem estáveis pelo período configurado.
- Ajustes de **verificação** e **estabilidade**, em segundos.
- Notificações em dois modos: **Alerta nativo** ou **Silencioso**.
- Botão **Limpar agora** para iniciar uma limpeza manual com confirmação.
- Contagem de arquivos atualmente presentes no cache.
- Gráfico com as últimas limpezas registradas, incluindo data, horário e quantidade removida ao passar o mouse.
- Histórico local persistente, mantido entre sessões do SketchUp.

## Instalação

1. Baixe o arquivo **`DinaBoxCacheControl-v1.0.0-FelipeRosa.rbz`**.
2. Abra o SketchUp e acesse **Janela → Gerenciador de Extensões**.
3. Clique em **Instalar extensão** e selecione o arquivo `.rbz` baixado.
4. Reinicie o SketchUp, se necessário.
5. Abra o **DinaBox CACHE CONTROL** pela barra de ferramentas ou pelo menu **Extensões**.

**O `.rbz` é o instalador completo.** Ele já inclui os ícones da barra de ferramentas, o código Ruby e toda a interface (HTML, CSS e JavaScript). Não é necessário copiar arquivos ou pastas manualmente.

## Como usar

O monitor inicia automaticamente quando está habilitado. No painel, você pode:

- **Verificação:** escolher a frequência de consulta das pastas (de 1 a 60 segundos).
- **Estabilidade:** definir a espera mínima antes de uma exclusão automática (de 3 a 120 segundos).
- **Notificações:** escolher entre avisos nativos do SketchUp e modo silencioso.
- **Monitoramento:** ativar ou pausar a limpeza automática.
- **Limpar agora:** executar uma limpeza manual dos arquivos elegíveis.

Em instalações novas, os valores iniciais previstos são **2 segundos de verificação** e **5 segundos de estabilidade**. Preferências já gravadas no SketchUp podem manter valores diferentes.

O modo **Silencioso** desativa os avisos; **não desativa a limpeza automática**.

## Histórico de limpezas

O painel mostra as **24 limpezas mais recentes** registradas pelo plugin. Os registros são salvos localmente no arquivo `DinaBoxCacheControl/cleanup_history.jsonl`, na pasta de dados do SketchUp, fora do diretório da extensão.

O gráfico utiliza somente os registros efetivamente coletados. Ele começa vazio até ocorrerem novas limpezas; não inventa dados anteriores à instalação desta edição.

## Cuidados e limitações

O plugin atua apenas sobre arquivos comuns diretamente dentro das duas pastas monitoradas. Não percorre subpastas nem remove links simbólicos. Antes de apagar um arquivo, verifica se suas informações permanecem estáveis pelo período configurado.

Essas verificações **não garantem** que o DinaBox tenha liberado internamente todo arquivo. Em caso de dúvidas, teste primeiro com uma cópia do projeto e ajuste o tempo de estabilidade conforme a necessidade.

## Desenvolvedor

**Felipe Rosa**  
GitHub: [@feliperos-a](https://github.com/feliperos-a)

**Versão:** 1.0.0
