# hierarchy_update

A gestão de visualização e acesso das regionais é determinado por um conjunto de verificações. 

Para que o colaborador consiga visualizar informações de desempenho de outros pontos de atendimento além do próprio, é necessário cumprir com certas exigências de centro de custo, cargo. 

A gestão de acesso ao rollout nos dashboards é determinada pela tabela dinamica TC_ACESSOS_ROLLOUT, que por sua vez, tem como base as tabelas SDX_EXCELENCIA_COMERCIAL.HIERARQUIA_GESTAO.MRT_GESTAO_ACESSOS_ROLLOUT_BEMAQUI e SDX_EXCELENCIA_COMERCIAL.HIERARQUIA_GESTAO.MRT_GESTAO_ACESSOS_ROLLOUT.

Outra tabela base é a hierarquia do DEP onde o centro de custo é crucial:

``SELECT * FROM SILVER.ADMINISTRATIVO_SUPORTE_INFRAESTRUTURA.HST_HIERARQUIA_DIA WHERE NOM_SUP_CMC LIKE '%SP 4%' ORDER BY DTA_RFC``

Essa tabela é a hierarquia oficial do banco, na qual, os campos NUM_MAT_CMC e NOM_EPG_CMC são, respectivamente, matricula e nome do regional.

Para o caso onde o novo colaborador não esteja visualizando as informações, indica que nesta tabela o regional responsável do ponto de atendimento em questão está incorreto ou não possui um cadastrado como na imagem a seguir:

![image](https://github.com/Banco-Mercantil/hierarchy_update/assets/88452990/873799d2-ab96-4d55-bcac-39dff650d505)

Uma das possiveis causas para que os dados desta tabela esteja incorreto, é a inconsistencia das informações das tabelas bases do RH.
Para averiguar, basta acessar o a plataforma do notes, ir no site RH cadastro, ir para centro de custo e digitar o número do centro de custo que esta infomando no cadastro do colaborador.

Essa busca exibe todos os centros de custos subordinados a ele: 

![image](https://github.com/Banco-Mercantil/hierarchy_update/assets/88452990/ead5d83d-a85b-4ea8-8780-9d34b3bec36f)


Selecione qualquer um deles para verificar o subordinador:

![image](https://github.com/Banco-Mercantil/hierarchy_update/assets/88452990/acd194a8-4490-46ff-a6e0-9d08ebdd3dd3)

Neste parametro você deve identificar o nome do colaborador que esta indicado como responsável. Este é o usuário que possuirá a visualização dos demais pontos de atendimento nos dashboards.  








