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
        +setModelo()
        +setPlaca()
        +setAnoFabricacao()
        +setQuilometragem()
        +setTipoCombustivel()
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
        +setNome()
        +setCpf()
        +setNumeroCNH()
        +setTelefone()
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
        +setTipo()
        +setData()
        +setDetalhes()
        +setConcluida()
        +agendarManutencao()
        +registrarConcluida()
    }

    class Abastecimento {
        -data : Date
        -valor : float
        -quantidade : float
        +setData()
        +setValor()
        +setQuantidade()
        +registrarAbastecimento()
    }

    class Infracao {
        -descricao : String
        -data : Date
        +setDescricao()
        +setData()
    }

    class Rota {
        -destino : String
        -pontosParada : List<String>
        +setDestino()
        +setPontosParada()
        +criarRota()
    }

    class Documento {
        -tipo : String
        -dataVencimento : Date
        +setTipo()
        +setDataVencimento()
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
