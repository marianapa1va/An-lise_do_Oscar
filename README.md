# Análise do Oscar.

(Banco de dados)

Atividades para trabalhar com o Oscar: 

1- Quantas vezes Natalie Portman foi indicada ao Oscar? 

R: Natalie Portman, foi indicada três vezes ao Oscar. Nas categorias de: "ACTRESS IN A SUPPORTING ROLE", "ACTRESS IN A LEADING ROLE" e "ACTRESS IN A LEADING ROLE".

Comando usado: 

```js

 {nome_do_indicado: "Natalie Portman"}

```

2- Quantos Oscars Natalie Portman ganhou? 

R: Ela ganhou somente um, graças ao filme “Black Swan”. 

Comando usado: 

 ```js

 { nome_do_indicado: "Natalie Portman" }
  
```

3- Amy Adams já ganhou algum Oscar? 

R: Mesmo contendo seis indicações ao Oscar, ela não conseguiu ganhar nenhum. 

 Comando usado: 
 
  ```js

 { nome_do_indicado: "Amy Adams" }
  
```
 
4- A série de filmes Toy Story ganhou um Oscar em quais anos? 

R: Em 2010 a franquia recebeu dois Oscars nas categorias de "ANIMATED FEATURE FILM" e "MUSIC (Original Song)", com o Filme Toy Story 3; e em 2010 na categoria de "ANIMATED FEATURE FILM" com o filme Toy Story 4. 

 Comando usado: 
 
 ```js

{ nome_do_filme: /Toy Story/ }

```

5- A partir de que ano que a categoria "Actress" deixa de existir?  

R: Apartir de 1976.

 Comando usado:
 
 ```js
db.orcar_analise.find({categoria: "ACTRESS"}).sort({cerimonia: -1})

```

6- O primeiro Oscar para melhor Atriz foi para quem? Em que ano? 
 
R: Em 1928, Janet Gaynor foi a primeira ganhadora dessa categoria. 

Comando usado: 

 ```js
{ categoria: "ACTRESS" }

```

 
7- Na campo "Vencedor", altere todos os valores com "Sim" para 1 e todos os valores "Não" para 0. 

 Comandos usados:
 
 ```js

db.oscar_analise.updateMany({vencedor:"true"},{$set:{vencedor:"1"}})
db.oscar_analise.updateMany({vencedor:"false"},{$set:{vencedor:"0"}})


```


8- Em qual edição do Oscar "Crash" concorreu ao Oscar? 

R: Em 2006 “Crash”, recebeu seis indicações, ganhando apenas três delas. 

Comando usado:
 
 ```js

{ nome_do_filme: "Crash" }

```


9- Bom... dê um Oscar para um filme que merece muito, mas não ganhou. 

 ```js


```


10- O filme Central do Brasil aparece no Oscar? 

R: Sim, ele aparece como: Central Station 

Comandos usado:

 ```js

{ nome_do_indicado: "Fernanda Montenegro" }


```
e

 ```js

{ nome_do_filme: "Central Station" }

```

11- Inclua no banco 3 filmes que nunca foram nem nomeados ao Oscar, mas que merecem ser.  

Comando usado:
  
 ```js
db.oscar_analise.insertMany([{
  
   "ano_cerimonia": 2016,
   "categoria": "Music (Original Score)",
   "nome_do_filme": "Your Name",
   "vencedor": "1"
},
{
    "ano_de_cerimonia": 2013,
    "categoria": "BEST PICTURE",
    "nome_do_filme": "Valente",
    "vencedor": "1"
},
{

    "ano_de_cerimonia": 2004,
    "categoria": "FILM EDITING",
    "nome_do_filme": "Olga",
    "vencedor": "1"
}])


```


12 - Pensando no ano em que você nasceu: Qual foi o Oscar de melhor filme, Melhor Atriz e Melhor Diretor? 

R: Melhor Filme: Crash ; Melhor Atriz: Reese Witherspoon ; Melhor Diretor: Ang Lee

Comando usado:
 
 ```js
{ ano_cerimonia: 2006 }

```
