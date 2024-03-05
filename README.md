# Fund._Ci-n._Dados
Códigos da disciplina da ciência de dados





# -*- coding: utf-8 -*-
"""
Spyder Editor

This is a temporary script file.
"""


# Pacotes

import pandas as pd

#Carregamento dos dados

pokemon = pd.read_csv("C:/Users/20201enpro0230/Downloads/pokemon_data (1).csv")

#Descrição dos dados

pokemon.describe()

#Selecionar colunas específicas

pokemon_2 = pokemon[['Name', 'Type 1', 'Type 2']]

#Filtrar por tipo do pokemon

pokemon_fogo = pokemon.loc[pokemon['Type 1'] == 'Fire']

#Usando indice numérico

pokemon_fogo2 = pokemon[pokemon.iloc[:,2] == 'Fire']

# Filtrar por tipo do pokemon

pokemon_fogo = pokemon.loc[(pokemon['Type 1'] == 'Fire') | (pokemon['Type 2'] == 'Fire')]

# Ordenação

pokemon_ataque = pokemon.sort_values('Attack', ascending = False)

# Estatísticas de agregação

pokemon_agrupado = pokemon.groupby(['Type 1'])

pokemon_agrupado['Attack'].mean()
pokemon_agrupado['Attack'].std()
pokemon_agrupado['Attack'].median()
