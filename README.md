```mermaid
classDiagram
    class Veiculo {
        -modelo : String
        -placa : String
        -anoFabricacao : int
        -quilometragem : float
        -tipoCombustivel : String
        -manutencoes : List<Manutencao>
        -abastecimentos : List<Abastecimento>
        -motorista : Motorista
        +setModelo(modelo : String)
        +setPlaca(placa : String)
        +setAnoFabricacao(ano : int)
        +setQuilometragem(quilometragem : float)
        +setTipoCombustivel(tipo : String)
        +cadastrarVeiculo()
        +atualizarVeiculo()
        +baixarVeiculo()
        +gerarRelatorioConsumo()
        +calcularConsumoMedio()
    }

    class Caminhao {
        -modelo : String
        -placa : String
        -anoFabricacao : int
        -quilometragem : float
        -tipoCombustivel : String
        -tipoHabilitacao : String
    }

    class Carro {
        -modelo : String
        -placa : String
        -anoFabricacao : int
        -quilometragem : float
        -tipoCombustivel : String
        -tipoHabilitacao : String
    }

    class Moto {
        -modelo : String
        -placa : String
        -anoFabricacao : int
        -quilometragem : float
        -tipoCombustivel : String
        -tipoHabilitacao : String
    }

    class Motorista {
        -nome : String
        -cpf : String
        -numeroCNH : String
        -telefone : String
        -veiculos : List<Veiculo>
        -infrações : List<Infracao>
        -rotas : List<Rota>
        +setNome(nome : String)
        +setCpf(cpf : String)
        +setNumeroCNH(cnh : String)
        +setTelefone(telefone : String)
        +cadastrarMotorista()
        +editarMotorista()
        +consultarHistorico()
        +gerarRelatorioRotas()
    }

    class Manutencao {
        -tipo : String
        -data : Date
        -detalhes : String
        -concluida : boolean
        +setTipo(tipo : String)
        +setData(data : Date)
        +setDetalhes(detalhes : String)
        +setConcluida(concluida : boolean)
        +agendarManutencao()
        +registrarConcluida()
    }

    class Abastecimento {
        -data : Date
        -valor : float
        -quantidade : float
        +setData(data : Date)
        +setValor(valor : float)
        +setQuantidade(quantidade : float)
        +registrarAbastecimento()
    }

    class Infracao {
        -descricao : String
        -data : Date
        +setDescricao(descricao : String)
        +setData(data : Date)
    }

    class Rota {
        -destino : String
        -pontosParada : List<String>
        +setDestino(destino : String)
        +setPontosParada(pontos : List<String>)
        +criarRota()
    }

    class Documento {
        -tipo : String
        -dataVencimento : Date
        +setTipo(tipo : String)
        +setDataVencimento(data : Date)
        +uploadDocumento()
    }

    Veiculo *--|> Caminhao
    Veiculo *--|> Carro
    Veiculo *--|> Moto


    Veiculo --> Motorista
    Veiculo --> Manutencao
    Veiculo --> Abastecimento
    Motorista --> Rota
    Motorista --> Infracao
    Motorista --> Documento



```mermaid
