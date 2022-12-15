<p align="center">
  <a href="" rel="noopener">
 <img src="https://i.imgur.com/AZ2iWek.png" alt="Project logo"></a>
</p>
<h3 align="center">Hackaton Federal Web3</h3>

<div align="center">

[![Hackathon](https://img.shields.io/badge/hackathon-name-orange.svg)](https://patrimoniodauniaonaweb3.hackerearth.com/pt-br/)
[![Status](https://img.shields.io/badge/status-active-success.svg)]()
[![GitHub Issues](https://img.shields.io/github/issues/kylelobo/The-Documentation-Compendium.svg)](https://github.com/kylelobo/The-Documentation-Compendium/issues)
[![GitHub Pull Requests](https://img.shields.io/github/issues-pr/kylelobo/The-Documentation-Compendium.svg)](https://github.com/kylelobo/The-Documentation-Compendium/pulls)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE.md)

</div>

---

<p align="center"> Few lines describing your project.
    <br> 
</p>

## 📝 Tabela de conteúdos

- [Descrição do problema](#problem_statement)
- [Idea / Solution](#idea)
- [Dependencies / Limitations](#limitations)
- [Future Scope](#future_scope)
- [Setting up a local environment](#getting_started)
- [Technology Stack](#tech_stack)
- [Authors](#authors)
- [Acknowledgments](#acknowledgments)

## 🧐 Descrição do problema <a name = "problem_statement"></a>

Os registros dos imóveis da união ficam dispersos em várias bases de dados pelo país, não necessariamente
atingindo um consenso entre si em como o processo é feito e nem como armazenar essas informações. Idealmente, todos os registros de imóveis da união deveriam ser publicamente disponíveis em uma plataforma de fácil acesso, que também permitisse verificar a quem o uso está destinado, além habilitar
a visualização desses contratos públicos.

Como Não existe uma plataforma do tipo, para conseguir informações desses imóveis é preciso agregar
de diferentes organizações públicas dos estados e municípios que nem sempre etão digitalizados e se estiverem, carecem de dados ou estão desatualizados. Pode acontecer também desses contratos entrarem em conflito entre organizações diferentes, gerando uma dor de cabeça e várias horas de advogados e funcionários públicos para chegar em consenso.




## 💡 Ideia / Solução <a name = "idea"></a>

Para solucionar esse problema, No nosso projeto registramos os imóveis da SPU (disponíveis publicamente pelo site https://www.gov.br/economia/pt-br/assuntos/patrimonio-da-uniao/transparencia/dados-abertos)  no IPFS e "pinamos" esses registros em um contrato padrão de NFT ERC1155. Nisso, criamos um contrato para definir de maneira segura quais endereços podem incorporar esses imóveis representados como NFTs no contrato. À partir daí, o contrato Registry.sol lida com o processo de incorporação, desde o início até o fim, quanto atualizações, mantendo um histórico de atualização por meio de uma lista encadeada.


## ⛓️ Dependências / Limitações <a name = "limitations"></a>

- O padrão ERC1155 apesar de permitir `batchMint` não encaixaria no critério de adicionar
 instâncias únicas de IPFS que requerimos. Para isso, fizemos ele dar `mint` em apenas uma instância de imóvel por vez. Isso pode ser contornado por meio de muitos `mint` ao mesmo tempo, porém.
- No caso da aplicação estar na mainnet, seria preciso do token Celo para fazer qualquer registro.
Isso seria um custo associado a solução.
- Para que funcionários registrem informações no contrato inteligente, um supervisor precisa dar a eles esse acesso. Isso é para garantir que mesmo se essas chaves privadas sejam roubadas, ao menos uma medida de controle de danos pode entrar em ação. 
- 

## 🚀 Escopo Futuro <a name = "future_scope"></a>

Apesar de termos os contratos inteligentes, seus testes e a integração deles com o IPFS, o projeto careceu de uma aplicação front-end para demonstrar como os funcionários e tabeliões fariam o processo
de incorporação. Isso fica para uma demonstração futura desse projeto.

## 🏁 Getting Started <a name = "getting_started"></a>

Temos 4 repositórios principais. O smart-contracts lida com toda a parte de contratos inteligentes. Lá, tem informações de como rodar os testes dos contratos.

O repositório do nest-ipfs é uma aplicação que desenvolvemos para facilitar a construção e inserção doas informações dos imóveis da SPU no IPFS, para posterior inserção no contrato inteligente ERC1155. 

O repositório grt-indexer lida com a indexação de eventos de eventos dos contratos inteligentes, para que seja possível em front-end buscar e filtrar as informações de terrenos. 

O repositório front-end seria a aplicação que consumiria do indexador usando o The Graph, para mostrar e auxiliar os funcionários e supervisores no processo de incorporação de imóveis.



### Pré-requisitos

usamos nodejs versão 16 em todos os projetos relevantes. Instale a versão 16 do nodejs. 
Recomendamos o uso do `nvm` para usar múltiplas versões e escolher a correta.


## ⛏️ Built With <a name = "tech_stack"></a>

- [Solidity](https://docs.soliditylang.org/en/v0.8.17/) - Linguagem de contratos inteligentes
- [Harhdat](https://hardhat.org/) - Smart contract Development Framework
- [Nextjs](https://nextjs.org/) - Web Framework
- [NodeJs](https://nodejs.org/en/) - Server Environment
- [Nestjs](https://nestjs.com) - Backend Framework

- [TheGraph](https://thegraph.com/en/) - Smart Contract Event Indexer

## ✍️ Authors <a name = "authors"></a>

 [Participantes do projeto](https://github.com/orgs/Federel-Web3/people)

## 🎉 Acknowledgments <a name = "acknowledgments"></a>

Agradeço à todos integrantes do nosso grupo!

## Licensa de software

Todo o código dessa organização está sobre licensa MIT:

https://github.com/Federel-Web3/.github/blob/master/profile/License.md
