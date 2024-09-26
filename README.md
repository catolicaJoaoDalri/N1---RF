```mermaid
classDiagram
    class Veiculo {
        +modelo: String
        +placa: String
        +anoFabricacao: Int
        +quilometragem: Double
        +tipoCombustivel: String
        +cadastrar()
        +atualizar()
        +consultar()
        +baixar()
    }

    class Rota {
        +origem: String
    }

    Rota -->  Veiculo 
