# Projeto: Linkedin Crawler

## Contexto

Este projeto foi desenvolvido durante o meu trabalho em um Fundo de Busca (search fund), um nicho do setor de private equity. Os fundos de busca geralmente não possuem recursos para encontrar empresas disponíveis para a aquisição de forma proprietária. Sendo assim, a busca dos contatos dos "leads" (como proprietários ou diretores de empresas eram chamados) muitas vezes era feita de forma manual e não sistematizada.

Minha ideia foi, então, criar uma forma de sistematizar a busca dos leads usando uma ferramenta de web scraping. Essa ferramenta permitiu: a busca de contatos em uma plataforma centralizada, o LinkedIn, a sistematização e a automação parcial do processo. O resultado foi um ganho absurdo de produtividade, pois consegui mais de 200 leads em poucas semanas, o que normalmente levaria meses se feito manualmente.

## Observações

A ferramenta não possui uma interface de usuário amigável pois a ideia era coloca-la em funcionamento o mais rápido possível e também estava aprendendo a programar em python. No entanto, o objetivo foi alcançado. 

Atualmente creio que o Linkedin colocou filtros de segurança de modo que não é possível, ou é extramamente difícil, fazer scrapping em suas páginas.

Certamente hoje em dia, com mais conhecimentos sobre python e programação, eu faria inúmeras melhorias no código. No entanto, optei por deixar a versão original para demonstrar como agi e utilizei tecnologia no processo de solução de um problema real:

1- Entendimento do problema: precisávamos de mais leads proprietários para aumentar a probabilidade de aquisição.

2- Entendimento dos dos dados: Onde estão os dados, em que formato (não estruturado, páginas da web)

3- Preparação dos dados: dados são preparados para serem colocados em uma planilha de excel

4- Avaliação e aplicação: executar o algoritmo para obter o resultado proposto e criação de documentação/instruções

## Instruções para usar o código

Na época, redigi um conjunto de instruções para que outras pessoas pudessem utilizar o código, uma vez que eu havia deixado de trabalhar no fundo.

1)	Na pasta projects do desktop que você criou, copie e cole o arquivo em excel Linkedin_Crawler.xlsx (que está no driver)
2)	Baixe também o arquivo Linkedin_Crawler.py e coloque na mesma pasta do arquivo em excel.
3)	Abra o IntellijIDEA e abra o código Linkedin_Crawler.py
4)	Edite as partes em verde com seu login e senha do linkedin conforme a imagem abaixo. Atenção, não pode tirar as “”.

![UsuarioSenha](https://raw.githubusercontent.com/hugobaraujo88/linkedincrawler/main/img/UsuarioSenha.png)

5)	Após fazer essas modificações é só rodar o programa.

Atenção:

•	O arquivo em excel deve estar fechado durante a rodagem do programa (se estiver aberto o IntellijIDEA vai indicar um erro);

•	O programa em python irá escrever na primeira aba do arquivo em excel, portanto sugiro sempre deixar configurado como está. Após usar numa primeira busca, copie e cole para outra aba e deixe sempre a aba “Lista” limpa e em primeiro;

![planilha](https://raw.githubusercontent.com/hugobaraujo88/linkedincrawler/main/img/planilha.png)

•	O programa funciona pois testei várias vezes, mas o linkedin pode mudar seus parâmetros internos a qaulquer momento.

•	Se você quiser alterar os critérios de busca para os sócios/proprietários da empresa basta alterar a linha 172. O padrão é CEO OU DIRETOR OU DIRETORA:

![url_emp](https://raw.githubusercontent.com/hugobaraujo88/linkedincrawler/main/img/url_emp.png)

Tem que ser alterado após o “=” e antes to “&origin”
Por exemplo se você quiser, ao invés de CEO, colocar sócio, a linha ficaria

‘&keywords=(sócio)%20OR%20(diretor)%20OR%20(diretora)&origin=GLOBAL_SEARCH_HEADER’

Até pouco tempo atrás o linkedin permitia colocar até 15 itens para busca! Mas recentemente mudou para apenas 3, infelizmente. Ainda, se quiser adicionar mais um critério para busca ficaria assim:

‘&keywords=(sócio) %20OR20%(CEO)%20OR%20(diretor)%20OR%20(diretora)&origin=GLOBAL_SEARCH_HEADER’

(buscando sócio OU CEO OU diretor OU diretora, 4 critérios). Basta colocar o critério entre parenteses e colocar a expressão %20OR%20 em seguida, concatenado os vários critérios (caso o linkedin volte a permitir...)
