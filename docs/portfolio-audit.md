# Auditoria do portfólio — 26/10/2026

Escopo: os dez repositórios públicos retornados pela API pública e pela integração autenticada Pedronsjaja. Sem auditoria de repositórios privados. Classificação editorial, não certificação. A = destaque; B = apoio; C = aprendizado; D = legado. Nenhum projeto foi classificado D apenas por idade; nenhum foi arquivado ou excluído.

Método: leitura dos dez READMEs e AGENTS.md, inventário de arquivos, documentação de engenharia, código de entrada e caminhos centrais, testes/workflows, três execuções recentes disponíveis e Issues/PRs abertos. Auditoria por amostragem de implementação; binários CAD não foram abertos em CAD. Inspeção estática não prova funcionamento. Não se executou hardware ou serviços de produção.

| Repositório | Classe | Estado | Evidência inspecionada | Limite |
|---|---|---|---|---|
| [gaia-humanoid-simulation](https://github.com/Pedronsjaja/gaia-humanoid-simulation) | A | Implemented / experimental | ros2/gaia_op3_sim: adaptador OP3, launch, controladores de posição, câmera e IMU; modelo externo fixado em simulation/op3.repos. | Base presa; não valida marcha, modelo GAIA ou LX-225 físico. |
| [gaia-lx225-buslinker](https://github.com/Pedronsjaja/gaia-lx225-buslinker) | A | Implemented / experimental | servo_testbench.py: protocolo, leituras, limites e comandos; bench_tools.py: CSV/gráficos; seis módulos de testes com serial simulada. | Sem ponte ROS 2; velocidade estimada; timestamp após leitura no host, não aquisição no servo; sem medição de torque/corrente. |
| [gaia-humanoid-structure](https://github.com/Pedronsjaja/gaia-humanoid-structure) | A | Documented / assets | hardware/manifest.json, CAD nativo, STEP/STL, docs/modelo-gaia.md; firmware auxiliar de diagnóstico. | Não é montagem cinemática completa; massa/inércia/limites pendentes; licenças de CAD de terceiros não identificadas. Flagship mecânico em construção. |
| [gaia-ros2-ubuntu24](https://github.com/Pedronsjaja/gaia-ros2-ubuntu24) | B | Documented | Guias Ubuntu 24.04/Jazzy, dual boot/VM e ficha talker/listener. | Infraestrutura de apoio; instalação por máquina ainda precisa de evidência. |
| [geekmagic_pc_monitor](https://github.com/Pedronsjaja/geekmagic_pc_monitor) | B | Implemented / experimental | src/pc_monitor.py: aquisição, Pillow, HTTP e máquina de estados; tests/test_cache.py cobre falhas com mocks. | Telemetria útil ao posicionamento; firmware stock grava imagens em flash; testes não comprovam dispositivo. |
| [Hacking-tico-com-Esp32-s3](https://github.com/Pedronsjaja/Hacking-tico-com-Esp32-s3) | C | Implemented / learning | Firmware Arduino modular, OLED/joystick e diagnóstico Wi-Fi/BLE; PlatformIO e build CI. | Aprendizado embarcado relevante; configuração Flash/PSRAM requer conferência da placa. Não é controlador robótico. |
| [Leve11](https://github.com/Pedronsjaja/Leve11) | B | Implemented | Motor PowerShell, histórico/restauração e testes isolados; CI Windows. | Bom suporte de engenharia de software, fora do foco robótica; não há benchmark de economia de RAM. |
| [portal-gaia](https://github.com/Pedronsjaja/portal-gaia) | B | Implemented | Fork GaiaRobotca: HTML/Firebase/EmailJS, fila de envio, regressões offline. | Contribuição de manutenção, não autoria exclusiva. Backend compartilhado; regras de acesso não auditadas. |
| [gaiarobotica-new.github.io](https://github.com/Pedronsjaja/gaiarobotica-new.github.io) | B | Implemented / content | Fork institucional: HTML/CSS/JS, dados, gerador e validador Python; histórico de Pages. | Demonstra comunicação técnica e colaboração; não comprova resultados físicos dos projetos apresentados. |
| [Pedronsjaja](https://github.com/Pedronsjaja/Pedronsjaja) | B | Documented | README do perfil e AGENTS.md com papéis de equipe. | Índice do portfólio, não evidência técnica independente. |

## Evidências de CI e colaboração

Execuções históricas abaixo não são testes executados nesta auditoria, nem necessariamente da ponta atual de main. Run em outra branch não certifica main. Os workflows foram lidos para delimitar cobertura.

- **Hacking-tico-com-Esp32-s3**: [Firmware compile: success](https://github.com/Pedronsjaja/Hacking-tico-com-Esp32-s3/actions/runs/38266538270), SHA `65db3d39c32fbd79fc9c77e7d0cd639c40b03124`.
- **gaia-ros2-ubuntu24**: nenhuma execução retornada.
  - [docs: conecta o repositório à aula ilustrada de Python e ROS 2](https://github.com/Pedronsjaja/gaia-ros2-ubuntu24/pull/1): aberto; preservado, sem merge automático.
- **geekmagic_pc_monitor**: [Offline Python tests: success](https://github.com/Pedronsjaja/geekmagic_pc_monitor/actions/runs/38266528174), SHA `148d805fcf62819c6511395b22fc4f908279ae3b`.
- **gaia-humanoid-simulation**: [ROS 2 simulation checks: success](https://github.com/Pedronsjaja/gaia-humanoid-simulation/actions/runs/38266538136), SHA `e1b648dea6a187e726df3c955774e3ffc6ada916`; [ROS 2 simulation checks: success](https://github.com/Pedronsjaja/gaia-humanoid-simulation/actions/runs/35541627511), SHA `c6a4252a25a0ecddf02150724782bd275e52b35f`.
- **Leve11**: [Isolated Windows tests: success](https://github.com/Pedronsjaja/Leve11/actions/runs/38267977645), SHA `bf411406f784a506897b1727bb18659913a20136`; [Isolated Windows tests: failure](https://github.com/Pedronsjaja/Leve11/actions/runs/38267563409), SHA `b7c31a270c9173ffff115f68580e33a36dd5742c`; [Isolated Windows tests: failure](https://github.com/Pedronsjaja/Leve11/actions/runs/38266532046), SHA `13b521cdef2229f0db5410307130e2027d05f83e`.
- **portal-gaia**: [Offline JavaScript tests: success](https://github.com/Pedronsjaja/portal-gaia/actions/runs/38918478280), SHA `bbac6ec8485d82b32b7677103eb2c0eceee2969b`; [Offline JavaScript tests: success](https://github.com/Pedronsjaja/portal-gaia/actions/runs/38305203910), SHA `f281f6a40e682775b684750cd5594a69fbdfd428`; [Offline JavaScript tests: success](https://github.com/Pedronsjaja/portal-gaia/actions/runs/38267796825), SHA `a56ce0f90b5833a7994c039401dbf9ca6316bc7a`.
- **Pedronsjaja**: nenhuma execução retornada.
- **gaia-lx225-buslinker**: [Bancada sem hardware: success](https://github.com/Pedronsjaja/gaia-lx225-buslinker/actions/runs/40098749095), SHA `26386219e11fe6b6568e0b40903f397e012736a9`; [Bancada sem hardware: success](https://github.com/Pedronsjaja/gaia-lx225-buslinker/actions/runs/40098747132), SHA `26386219e11fe6b6568e0b40903f397e012736a9`; [Bancada sem hardware: success](https://github.com/Pedronsjaja/gaia-lx225-buslinker/actions/runs/38668992137), SHA `ecc1daac2fdf2b496e05f08c8777909a0ac87e0e`.
  - [docs: conecta o repositório à aula ilustrada de Python e ROS 2](https://github.com/Pedronsjaja/gaia-lx225-buslinker/pull/1): aberto; preservado, sem merge automático.
- **gaiarobotica-new.github.io**: [pages build and deployment: success](https://github.com/Pedronsjaja/gaiarobotica-new.github.io/actions/runs/38266559513), SHA `552755fdecd0dd1b049e4c7fd683e01fcc895caf`; [pages build and deployment: success](https://github.com/Pedronsjaja/gaiarobotica-new.github.io/actions/runs/38184737474), SHA `c0d8ed925f5a49b5c12954c85ed2b211ce770597`; [pages build and deployment: success](https://github.com/Pedronsjaja/gaiarobotica-new.github.io/actions/runs/36881006620), SHA `2797cbee86fa019ab91a358b58df1a8aa1e86d88`.
- **gaia-humanoid-structure**: [Integridade do acervo: success](https://github.com/Pedronsjaja/gaia-humanoid-structure/actions/runs/35590197866), SHA `52ee164d45dcc0087ed352dd7a849bb8903f419d`; [Integridade do acervo: success](https://github.com/Pedronsjaja/gaia-humanoid-structure/actions/runs/35590008889), SHA `a26f8e3838212152565966a30a85dac403a4ca82`.
  - [docs: conecta o repositório à aula ilustrada de Python e ROS 2](https://github.com/Pedronsjaja/gaia-humanoid-structure/pull/1): aberto; preservado, sem merge automático.

## Diagnóstico e prioridade

- CRÍTICO antes de ensaio físico: confirmar variante LX-225/BusLinker, alimentação, montagem, limites mecânicos, operador e parada independente. Nenhum acionamento autorizado por esta auditoria.
- ALTO: uma interface rastreável entre estado físico e virtual, com unidades, origem, validade e relógios explícitos; começar virtualmente.
- ALTO: registrar licenças/proveniência e identificar massa/inércia/zero da junta antes de reutilizar CAD no laboratório.
- MÉDIO: comparar RMW/QoS somente com metodologia e instrumentação controladas. Lacunas de sequência na aplicação não equivalem automaticamente a perda de pacotes na rede.
- MÉDIO: apresentar os quatro repositórios GAIA como componentes complementares e manter papéis/autorias de equipe.
- BAIXO: estética, novos badges e adição de tecnologias sem pergunta experimental.

## Plano aprovado pelo pedido

1. Atualizar perfil majoritariamente em inglês com foco e estados claros.
2. Melhorar a entrada dos quatro READMEs GAIA preservando guias e código.
3. Acrescentar roteiro LX-225 → ROS 2 → ros2_control → comparação virtual, sem implementar a ponte.
4. Preparar laboratório com arquitetura, v0.1–v1.0, protocolo experimental, alvos open source e oito Issues redigidas.
5. Validar documentação e registrar commits separados.

Na auditoria inicial, o laboratório não foi encontrado na listagem pública e a consulta autenticada retornou 404. Depois da preparação local, a gravação pelo conector retornou 403. A autenticação Git local funcionou e a conta Pedronsjaja foi verificada pela API antes de criar o novo repositório. Resultado: documentação publicada em physical-ai-digital-twin-lab, com oito Issues e labels. Código funcional dos projetos existentes permaneceu inalterado.

## Trilha de estudo

1. Radianos, referenciais, zero mecânico e conversão graus/radianos.
2. Nós/tópicos/TF/JointState e relógios ROS versus monotonic do host.
3. Gazebo, SDF/URDF e distinção entre estado comandado e observado.
4. QoS, idade da amostra, latência e sincronização de relógios.
5. Incerteza, RMSE e comparação entre modelo e experimento.

Próximo incremento único: atuador virtual de uma junta em ROS 2 Jazzy + Gazebo Harmonic, com estado observado e teste de comando, antes de conectar hardware.
