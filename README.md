## Objetivo
Repositório contendo roteiro passo-a-passo para criar um Modelo de previsão usando o Azure Machine Learning Studio.

## Resumo

Neste passo-a-passo será demonstrado como se utilizar do serviço do Microsoft Machine Learning, para podermos criar e treinar um modelo de estudo de regressão para obtermos a informação do número de alugueis previsto em um data momento do ano.

## Pré-requisito

Como pré-requisito é necessário possuir uma conta criada e funcional na [Azure](https://portal.azure.com/?quickstart=True#home).

  01 - Acesse a [página](https://azure.microsoft.com/pt-br/free/search/?ef_id=_k_CjwKCAiA8YyuBhBSEiwA5R3-EyxckFGkfk85I8455z8A8V9SEQ4rDamiBh29pzPeSy5ADC1geYuP7hoCVIAQAvD_BwE_k_&OCID=AIDcmmzmnb0182_SEM__k_CjwKCAiA8YyuBhBSEiwA5R3-EyxckFGkfk85I8455z8A8V9SEQ4rDamiBh29pzPeSy5ADC1geYuP7hoCVIAQAvD_BwE_k_&gad_source=1&gclid=CjwKCAiA8YyuBhBSEiwA5R3-EyxckFGkfk85I8455z8A8V9SEQ4rDamiBh29pzPeSy5ADC1geYuP7hoCVIAQAvD_BwE)

  02 - Clique em **Experimente gratuitamente**

  03 - Você será redirecionado para [página\(abaixo\)](https://login.microsoftonline.com/organizations/oauth2/v2.0/authorize?client_id=8e0e8db5-b713-4e91-98e6-470fed0aa4c2&response_type=code%20id_token&scope=openid%20profile&state=OpenIdConnect.AuthenticationProperties%3DtgIM8fUAqWeFNuvBd5GgL10awhlqhovrf_LeaF_V98VPjWvVVvh2l9wKa-TrmbYJkc5Qc0FyajfyI5oeDXhqUK3jq3J9KPIMVyBIqbDpKgLZ9OiladetOb9xfipP-LuLXa1ZvHmnx5VVmbWufDcTnUHnKZi842K2G2KMO3NoPmdYptG07X_VQuMEe0PBVLCv4wCg2402VAfBdrlkj4Zmj4XlXttNbbzLpEVUazwaUiF7pyLsphYwL6yukZglxfwmOrsLM143q55SR8rcde7Bl7onUiPYDMnODPWXibG8KhX8es6YLk-ETzUhQevJ4iSOmkpXRr9eC6r05WWRMe79zP-7qtfuuNcjcRQ3gBoehTjy92nVEImQBeFUueuTwuRBzIcwmLamlq0q7rlaNfYxhlR3HdRkTLu9J5kIWVxLi_7cuo9jG0sZgxJkSU9E3l67t7eI-HwiwGcLqkgFyNeKzGFYJ8SOC6luw27lLZ9KJ2XOWWWsZCsMpHJNaRPZna-kscK7tQRLAbJF-TH2OAOJoeypVbeWkvvS9yDOz6lORRrTvjTiBDC61jAZN0ZVXBhgw0sA61h8CO4ikIG_dMASZfC73qW12-u6QuLOoIHODOgmBxPsbzLT2cwTagbMufnr14hY4Dw2J1YomUKAE400RYrUxloEbh5xwZ5ifFSUuVLeixYtnON7bckL9eDqJ9CDc60xdnRF6HvFSWA_FxoK3zWCAxkF6z6FT8XJ068z8RWK0EpCZhKvhB-nKPsitDminmf5nwgdkY6m01Mnv7EAvZD4-OMzAND_14gNhN8B--nZrqKE1GEqiKfupkUtQWf94y7tXzlmBSEGe2uCBdmZkVe2UN9jxLR7ZRMzWGsVyKU5K3Ibw-HGcYaZDctMXRFrDaJF5N6OaN9tiTQ279Qb5PdNsb6nK0W2JrAgZkMo6txZIXhjQ1Z3r57W-vwU7AvpYNB4p9E3b17v-7LPZ_5QJILZaJZ_s_sf1mHh62hAINGfEpsuZKDrQ9-9rILdKX1JQiQlYietTOmKzF3bHk747LYWqtRy5sOayt1fyQgF5IvfiDVMz2KOsnOZGBH1R1FNTBKKZLt8fPDXw01sWsnsByhbmSuWTAQoRSWPJOy_gLx-tFBCI0DrTx2mFp_JuopusiE0J6bBm-coigEQBfUa57k-3endmqockVvi1892dPxvUHSS3pE4Bv8aB0nhq5s1pMjaCTVRosZncZfwkpapUg-joaWGaJ1xoO_rxXXocrjdaMKC3ko0l7YGhuCSmbr2-5pjITW6MmUBOdX0kymnpGNVWiTXC75a3d9UlKQOBe_z3Z9gPhHayCZDlMqzttja8ehvRid36s08fAf9er5Wz4As6NZgXBYfY1YXe4mWEn9PBcf7Tzya1c76qNIPlgj5LwqMqwOZDUUrbjooTRbrKg&response_mode=form_post&nonce=638429565329591794.NjVhYzg0ZjItM2U0My00MDY1LWEyODAtMzI3ZjZkNzQ5YmI4ZDgxNzA2NWYtODhmZS00MGQ2LTkxZWQtNGQ4ZDJmOTY1NTgy&redirect_uri=https%3A%2F%2Fsignup.azure.com%2Fapi%2Fuser%2Flogin&max_age=86400&post_logout_redirect_uri=https%3A%2F%2Fsignup.azure.com%2Fsignup%3Foffer%3Dms-azr-0044p%26appId%3D102%26ref%3D%26redirectURL%3Dhttps%3A%2F%2Fazure.microsoft.com%2Fget-started%2Fwelcome-to-azure%2F%26l%3Dpt-br%26srcurl%3Dhttps%3A%2F%2Fazure.microsoft.com%2Ffree%2Fsearch%2F%3Fef_id%3D_k_cjwkcaia8yyubhbseiwa5r3-eyxckfgkfk85i8455z8a8v9seq4rdamibh29pzpesy5adc1geyup7hocviaqavd_bwe_k_%26ocid%3Daidcmmzmnb0182_sem__k_cjwkcaia8yyubhbseiwa5r3-eyxckfgkfk85i8455z8a8v9seq4rdamibh29pzpesy5adc1geyup7hocviaqavd_bwe_k_%26gad_source%3D1%26gclid%3Dcjwkcaia8yyubhbseiwa5r3-eyxckfgkfk85i8455z8a8v9seq4rdamibh29pzpesy5adc1geyup7hocviaqavd_bwe&x-client-SKU=ID_NET472&x-client-ver=6.34.0.0), onde você vai ter as opções de loggin utilizando:

  - Sua conta de e-mail microsoft/outlook
  - Sua conta github

  04 - Logo após a autenticaçào, você vai visualizar duas opções, onde a primeira pede sua confirmação (marcando o checkbox) para o termos de planos do Azure e o segundo pede sua confirmação se deseja permitir à Microsoft compartilhar seu e-mail com parceiros comerciais e que provem produtos via plataforma da Azure, este segundo não é um item obrigatório, assim, fica a seu critério de como deseja seguir;

  05 - Mais abaixo dos dois checkbox citados no passo anterior, você irá visualizar o campo para selecionar ou cadastrar um cartão de crédito, no qual será feito a cobrança\*<br>
  Clique em "Criar Conta" e prossiga.
_\***Cobrança**: Com a conta gratuita você irá receber um bonus da Microsoft Azure +/- no valor de $ 200,00 e caso este saldo seja totalmente consumido pelos seus recursos criados o valor sobressalente será debitado no cartão cadastrado e selecionado._

  
## Passo-a-Passo

  01 - Abaixo de **Azure Services**, clique em [Create Resource/Criar Recurso] e será redirecionado para a tela abaixo

  
  02 - Digite na caixa de pesquisa {Azure Machine Learning} e aperte [ENTER] no seu teclado

  
  03 - Selecione a primeira opção/serviço [Azure Machine Learning] e depois clique em [Create]
 
  
  04 - Na tela exibida preencha os campos **Resource Group**, **Name** e **Region**
  **Resource Group**: Nome do Resource group sob o qual será criado o serviço que estamos configurando
  **Name**: O nome do recurso própriamente dito
  **Region**: Região onde será criado o recurso. Aqui utilizado uma região nos estados unidos visando deixar o custo um pouco mais em conta

  Caso deseje, dicas de como nomear cada recurso, vide este [doc da própia microsoft](https://learn.microsoft.com/pt-br/azure/cloud-adoption-framework/ready/azure-best-practices/resource-naming-and-tagging-decision-guide)

  05 - Clique em [Review + Create] e depoisem [Create]
  
  06 - Aguarde alguns minutos e ao receber a notificação em tela de que todos os recursos foram criados, você Clica em [Go to Resource]

  07 - Clique em [Launch Studio] para abrir o Azure Micrososft Learning
  08 - Com o **Azure Micrososft Learning** aberto, do seu lado esquerdo clique em [Automated ML]
  ![image](https://github.com/philipp-moreira/dio-ms-ai900-ml-desafio-pratico/assets/17642499/ee19e31b-2116-49c7-8eea-22c3067e5861)

  09 - Clique em [+ New Automated ML job]
  ![image](https://github.com/philipp-moreira/dio-ms-ai900-ml-desafio-pratico/assets/17642499/9a558da4-f610-45b8-a40c-e2ee5e4da5cf)

  10 - Preencha os campos Job Name, New Experiment name e Description, clicando em [Next]
  ![image](https://github.com/philipp-moreira/dio-ms-ai900-ml-desafio-pratico/assets/17642499/6619621b-9f14-44dc-8938-1a51dabf3261)

  11 - Selecione o tipo de task de Regression
  ![image](https://github.com/philipp-moreira/dio-ms-ai900-ml-desafio-pratico/assets/17642499/5690055e-a2f4-4d20-8596-fdb90e1394e6)

  12 - Clique em [Create], para selecionarmos a origem dos dados a serem utilizados no treino do Modelo

  13 - Na nova tela preencha os campos e clique em [Next]
  ![image](https://github.com/philipp-moreira/dio-ms-ai900-ml-desafio-pratico/assets/17642499/6bc165a4-6ad8-4406-ab41-bd4a8f8d312e)

  14 -  Selecione [From Web Files] e clique em [Next]
  ![image](https://github.com/philipp-moreira/dio-ms-ai900-ml-desafio-pratico/assets/17642499/a1683396-5e61-49ca-8227-ba3ea0f2c8eb)

  15 - Defina a URL de origem de onde será obtidos os dados e clique em [Next]
  ![image](https://github.com/philipp-moreira/dio-ms-ai900-ml-desafio-pratico/assets/17642499/fc99ce70-51d0-4c80-a671-6c2bb16d523e)

  16 - Altere o campo {Column headers} para **Only first file has headers** er desmarque a opção **Dataset contains multi-line data** e clique em [Next]
  ![image](https://github.com/philipp-moreira/dio-ms-ai900-ml-desafio-pratico/assets/17642499/50dad8c8-2aff-4b8d-87d5-6b21871d3afe)

  17 - Clique em [Next]
  ![image](https://github.com/philipp-moreira/dio-ms-ai900-ml-desafio-pratico/assets/17642499/f9350519-e4f0-4836-a79d-1427ab72c33b)

  18 - Reveja as informações e Clique em [Create]
  ![image](https://github.com/philipp-moreira/dio-ms-ai900-ml-desafio-pratico/assets/17642499/aa27683d-4871-4686-b7ba-6439693c5f50)

  19 - Selecione o Data Set criado {bike-rentals} e clique em [Next]
  ![image](https://github.com/philipp-moreira/dio-ms-ai900-ml-desafio-pratico/assets/17642499/cf35570d-edce-4ce3-96ae-b5d6a535a464)

  20 - No campo {Target Column}, selecione a opção rentals(Integer)
  ![image](https://github.com/philipp-moreira/dio-ms-ai900-ml-desafio-pratico/assets/17642499/036416de-9e3a-49b8-bd81-994cd0776a48)

  21 - Clique em [View Additional Configuration Settings]
  ![image](https://github.com/philipp-moreira/dio-ms-ai900-ml-desafio-pratico/assets/17642499/a5635043-bc6c-49f8-9207-27ab32b043dc)
  
  22 - Preencha os campos conforme abaixo e clique em [Save]
  ![image](https://github.com/philipp-moreira/dio-ms-ai900-ml-desafio-pratico/assets/17642499/c49a5b4f-3e98-4151-9e4e-c00d6546cb29)

  23 - Expanda a opção [Limits] e preencha os campos conforme abaixo e clique em [Next]
  ![image](https://github.com/philipp-moreira/dio-ms-ai900-ml-desafio-pratico/assets/17642499/ed11cbf8-62ea-4b54-aaa2-4de01f5779ac)

  24 - Mantenha as opções selecionadas e clique em [Next]
  ![image](https://github.com/philipp-moreira/dio-ms-ai900-ml-desafio-pratico/assets/17642499/9dbc8313-77f9-4570-ae1e-05a81c4ef4db)

  25 - Revise as informações e clique em [Submit Training Job]
  ![image](https://github.com/philipp-moreira/dio-ms-ai900-ml-desafio-pratico/assets/17642499/54caf3f8-d5a4-4276-b956-5d26c0c0e824)

  26 - O treino/job vai ter inicio no seu processamento; Aguarde sua conclusão
  ![image](https://github.com/philipp-moreira/dio-ms-ai900-ml-desafio-pratico/assets/17642499/801430c4-aa54-46f0-8b22-a76c964e9712)

  27 - Quando concluido, podemos verificar no campo Status o status de Completed.<br>
  Do lado direito na seção {Best model summary}, pode-se obter do serviço do Azure Machine Learning a indicação do melhor algoritmo, durante a etapa de treino
  do modelo.
  ![image](https://github.com/philipp-moreira/dio-ms-ai900-ml-desafio-pratico/assets/17642499/267ea9d8-1aac-4953-bc2d-46364068f90f)

  28 - Ao clicar em cima do nome do modelo com melhor performance, somos direcionados a uma tela que podem demonstrar mais detalhes do motivo pelo qual este foi o modelo com melhor performance
  ![image](https://github.com/philipp-moreira/dio-ms-ai900-ml-desafio-pratico/assets/17642499/892df195-61c2-47ab-9c87-59959159035b)

  29 - Ao clicar em [Metrics], vemos o resultado das métricas/dimensões de avaliação obtidas utilizando um treino baseado em uma tarefa de regressão.
  ![image](https://github.com/philipp-moreira/dio-ms-ai900-ml-desafio-pratico/assets/17642499/924705f8-e0ad-4ff8-ae0a-7e6f9ace02ca)

  30 - O próximo passo que se faz necessário, é a publicação do modelo para que possamos testar o modelo treinado.
  ![image](https://github.com/philipp-moreira/dio-ms-ai900-ml-desafio-pratico/assets/17642499/e57014a8-a128-41cc-a83e-c513676cb310)

  31 - Uma vez iniciado o Deploy, observe no campo status Deploy que é indicado que o processo está "Rodando"(Running)
  ![image](https://github.com/philipp-moreira/dio-ms-ai900-ml-desafio-pratico/assets/17642499/9f6d22bf-5e18-468a-a077-55be5586935d)

  32 - Ao final da conclusão do passo de Deplou pode se notar que o status mudou para Sucesso (Succeeded)
  ![image](https://github.com/philipp-moreira/dio-ms-ai900-ml-desafio-pratico/assets/17642499/6db91d98-3653-479f-9b22-54a1ee2ed5fc)

  33 - Neste passo podemos avaliar nosso modelo; Do lado esquerdo clicando em [Endpoints], o constatando a criação do nosso Endpoint
  ![image](https://github.com/philipp-moreira/dio-ms-ai900-ml-desafio-pratico/assets/17642499/2b8efc8d-2441-43ab-83e9-9fdbf39acfec)

  34 - Ao clicar no nome do Endpoint criado, seremos redirecionados para a pagina 
  ![image](https://github.com/philipp-moreira/dio-ms-ai900-ml-desafio-pratico/assets/17642499/ba7489ac-0106-4e5b-8d76-56d232af39e0)

  35 - Ao clicarmos na aba test, podemos testar no modelo e obter a informação desejada, ou seja, o número previsto de aluguel de bicicletas em uma data e baseado em dados de estação do ano e recursos metereológicos.
  ![image](https://github.com/philipp-moreira/dio-ms-ai900-ml-desafio-pratico/assets/17642499/9b7fed09-a53c-4ba9-97eb-1aaaa28cfe1d)


## Resultados

### Arquivo(s): vide o arquivo endpoint-predict-rentals.json
