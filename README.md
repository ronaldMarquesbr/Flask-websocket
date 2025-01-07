# 💳 API de Pagamento com QR Code - Simulação
Este projeto é uma simulação de uma API de pagamentos utilizando QR Code e a funcionalidade de "cópia e cola". Desenvolvido com Flask, o projeto faz parte do módulo de Flask do curso de Python da Rocketseat. Ele demonstra como criar endpoints para gerenciar pagamentos de forma prática e funcional.

## 🚀 Funcionalidades
- Geração de QR Code para pagamentos.
- Endpoint para "cópia e cola" do código de pagamento.
- Consulta de status do pagamento.
## 🛠️ Tecnologias utilizadas
- Framework: Flask
- Banco de Dados: SQLite
- **Bibliotecas adicionais:**
    - qrcode (para geração de códigos QR)
    - Flask-SQLAlchemy (ORM)
    - Datetime (manipulação de datas e horários)

## 🔗 Endpoints principais

### Criar pagamento

```
  POST /payments/pix
```

Corpo da requisição
```json
{
    "value": <float>
}

```

Respostas
| Código    |  Descrição                       |
| :-------- |:-------------------------------- |
| 200    | Pagamento criado com sucesso |
| 400    | Dados enviados incorretamente|

### Confirmar pagamento

Essa rota simula a confirmação do pagamento por uma instituição financeira verdadeira

```
  POST /payments/pix/confirmation   
```

Corpo da requisição
```json
{
    "bank_payment_id": "<string>",
    "value": <float>
}

```

Respostas
| Código    |  Descrição                       |
| :-------- |:-------------------------------- |
| 200    | Pagamento confirmado com sucesso |
| 400    | Informações de pagamento inválidas |
| 404    | Pagamento não encontrado |

### Obter qrcode de pagamento

```
  GET /payments/pix/qr_code/<file_name> 
```

| Parâmetro | Tipo     | Descrição                       |
| :-------- | :------- | :-------------------------------- |
| `file_name`      | `String` | **Obrigatório**. Qrcode de pagamento a ser obtido|

Respostas
| Código    |  Descrição                       | 
| :-------- |:-------------------------------- |
| 200    | Imagem encontrada com sucesso|
| 404    | Imagem não encontrado|

