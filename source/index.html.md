---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/lord/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Documents
# Facturemosya
## Invoice
> To create a Invoice you must to use this payload

```json
{
  "_meta": {
    "type_code": "invoice",
    "company_id": 1
  },
  "billing_document_id": "198",
  "number": "142",
  "date": "2019-08-01",
  "due_date": "2019-09-01",
  "currency": "MXN",
  "currency_exchange": 1.0,
  "numbering": "001",
  "company": {
    "id": 1,
    "tin": "WLL090422JV9",
    "name": "CMS WOODHOUSE LORENTE LUDLOW",
    "address": "Reforma 115 Int Piso 19, Col. Lomas de Chapultepec, Del. Miguel Hidalgo, México D.F. 11000 ",
    "address_fields": {
        "subpremise": "Int Piso 19",
        "street_number": "115",
        "route": "Paseo de la Reforma",
        "neighborhood": "Lomas - Virreyes",
        "political": "Lomas de Chapultepec V Sección",
        "locality": "Ciudad de México",
        "administrative_area_level_1": "Ciudad de México",
        "country": "Mexico",
        "postal_code": "11300",
        "country_code": "MX",
        "country_id": 157,
        "single_address": "translation missing: es.address.mx.single_address_format"
    },
    "phone": "5526230552",
    "email": "null"
  },
  "billing_entity": {
    "identification_type": "31",
    "identification": "99511620-0",
    "name": "Lemontech SA",
    "business": "Tecnología",
    "address": "Los Militares 4777 of. 1904",
    "district": "Las Condes",
    "city": "Santiago",
    "country": "CL"
  },
  "document_lines": [
    {
      "code": "honorariums",
      "product": "Honorarios legales",
      "description": "Descripción de honorarios escrita por el usuario",
      "price": "100",
      "tax_code": "IVA",
      "tax_amount": 19,
      "quantity": 1,
      "tax_percentage": "19",
      "taxable": true,
      "extra": {
        "product_key": "80121600",
        "unit_key": "E48"
      }
    },
    {
      "code": "taxed_expenses",
      "product": "Gastos",
      "description": "Descripción de gastos escrita por el usuario",
      "price": "100",
      "tax_code": "IVA",
      "tax_amount": 19,
      "quantity": 2,
      "tax_percentage": "19",
      "taxable": true,
      "extra": {
        "product_key": "80121600",
        "unit_key": "E48"
      }
    },
    {
      "code": "expenses",
      "product": "Gastos sin impuesto",
      "description": "Descripción de gastos sin impuesto escrita por el usuario",
      "price": "100",
      "tax_code": "IVA",
      "tax_amount": 0,
      "quantity": 2,
      "tax_percentage": "0",
      "taxable": true,
      "extra": {
        "product_key": "80121600",
        "unit_key": "E48"
      }
    }
  ],
  "notes": "Esto es una observación",
  "payment_terms": "CC 15 días",
  "extra": {
    "payment_method_code": "03",
    "installment_plan_code": "PUE",
    "receipt_type": "I",
    "order_number": "Número de orden",
    "branch_name": "Nombre de sucursal",
    "cfdi_use_code": "P00",
    "cfdi_related_type_code": "04",
    "external_id": "d1d069f7-962c-4c04-9274-43bafb27d3f9",
    "execution_address": {
      "street": "Floridablanca",
      "number": "10",
      "floor": "3",
      "district": "Sant Antoni",
      "city": "Barcelona",
      "county": "Barcelona",
      "state": "Catalunya",
      "country": "ESP",
      "zip_code": "08013"
    }
  },
  "references": [
    {
      "id": 464,
      "billing_document_id": 395,
      "reason_id": null,
      "description": "Esto es una descripción del primer doc. de referencia",
      "external": {
        "referred_document_external_id": "d1d069f7-962c-4c04-9274-43bafb27d3f9",
        "referred_document_type_external_code": "802",
        "referred_document_number": "34324",
        "referred_document_date": "2019-10-25"
      },
      "created_at": "2019-10-02T14:31:35.000Z",
      "updated_at": "2019-10-02T14:31:35.000Z"
    }
  ]
}
```
> this is needed from product

|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|[_meta](#Facturemosya_invoice__meta)|Entities::Meta||false|||
|billing_document_id|String||true|||
|number|Fixnum||true|||
|date|DateTime||true|||
|due_date|DateTime||false|||
|currency|String||true|||
|currency_exchange|Float||false|||
|numbering|String||true|||
|[company](#Facturemosya_invoice_company)|Entities::Company||false|||
|[billing_entity](#Facturemosya_invoice_billing_entity)|Entities::BillingEntity||true|||
|[document_lines](#Facturemosya_invoice_document_lines)|Array||true|[]||
|notes|String||false|||
|payment_terms|String||false|||
|[extra](#Facturemosya_invoice_extra)|Facturemosya::Entities::InvoiceExtra||false|||
|[references](#Facturemosya_invoice_references)|Array||false|[]||
|regime|String||false|601||

### <a name='Facturemosya_invoice__meta'></a>_meta
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|type_code|String||true|||
|company_id|Fixnum||true|||

### <a name='Facturemosya_invoice_company'></a>company
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|id|Fixnum||false|||
|tin|String||false|||
|name|String||false|||
|address|String||false|||
|address_fields|Hash||false|||
|phone|String||false|||
|email|String||false|||

### <a name='Facturemosya_invoice_billing_entity'></a>billing_entity
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|identification_type|String||true|||
|identification|String||true|||
|name|String||true|||
|business|String||false|||
|address|String||true|||
|district|String||false|||
|city|String||true|||
|country|String||true|||

### <a name='Facturemosya_invoice_document_lines'></a>document_lines
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|code|String||false|||
|product|String||true|||
|description|String||true|||
|price|Float||true|||
|tax_code|String||true|||
|tax_amount|Float||true|||
|quantity|Fixnum||true|||
|tax_percentage|Float||true|||
|taxable|TrueClass||true|||
|extra|Hash||false|||

### <a name='Facturemosya_invoice_extra'></a>extra
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|cfdi_related_type_code|String||false|||
|payment_method_code|String||true|||
|installment_plan_code|String||true|||
|receipt_type|String||false|||
|order_number|String||false|||
|branch_name|String||false|||
|cfdi_use_code|String||false|||
|external_id|String||true|||
|[execution_address](#Facturemosya_invoice_execution_address)|Facturemosya::Entities::InvoiceExtraExecutionAddress||false|||

### execution_address
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|street|String||true|||
|number|String||true|||
|floor|String||false|||
|district|String||false|||
|city|String||false|||
|county|String||false|||
|state|String||false|||
|country|String||false|||
|zip_code|String||true|||

### <a name='Facturemosya_invoice_references'></a>references
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|id|String||false|||
|billing_document_id|String||false|||
|reason_id|String||false|||
|description|String||false|||
|external|Hash||false|||
|created_at|String||false|||
|updated_at|String||false|||

## PaymentReceipt
> To create a PaymentReceipt you must to use this payload

```json
{
  "_meta": {
    "company_id": 1,
    "type_code": "payment_receipt"
  },
  "payment_id": 1,
  "series_code": "AV",
  "number": 407,
  "date": "2019-11-26",
  "total": 100.00,
  "currency": {
    "code": "USD",
    "exchange": 19.396
  },
  "billing_entity": {
    "identification_type": "tin",
    "identification": "SAR160314MN3",
    "name": "Skidata Access and Revenue Management Solutions México S.A.P.I. de C.V. ",
    "business": null,
    "address": "Avenida Lázaro Cárdenas 2224",
    "street": "Avenida Lázaro Cárdenas",
    "number": "2224",
    "subpremise": "oficina 23, piso 2",
    "district": "Monterrey",
    "city": "Monterrey",
    "country": "MX",
    "extra": {}
  },
  "references": [
    {
      "id": 464,
      "billing_document_id": 395,
      "reason_id": null,
      "description": "Esto es una descripción del primer doc. de referencia",
      "external": {
        "referred_document_external_id": "d1d069f7-962c-4c04-9274-43bafb27d3f9",
        "referred_document_type_external_code": "802",
        "referred_document_number": "34324",
        "referred_document_date": "2019-10-25"
      },
      "created_at": "2019-10-02T14:31:35.000Z",
      "updated_at": "2019-10-02T14:31:35.000Z"
    }
  ],
  "paid_documents": [
    {
      "id": 1,
      "number": 1,
      "external_id": "d1d069f7-962c-4c04-9274-43bafb27d3f9",
      "series_code": "1",
      "balance": 110.00,
      "paid_amount": 100.00,
      "currency": {
        "code": "USD",
        "exchange": 19.396
      },
      "extra": {
        "installment_plan_code": "PUE"
      }
    }
  ],
  "extra": {
    "payment_method_code": "02",
    "sender_bank_code": "XEXX010101000",
    "sender_bank_name": "Banco",
    "sender_bank_account": "123456789101112131",
    "beneficiary_bank_code": "AAA010101AAA",
    "beneficiary_bank_account": "123456789101114558"
  }
}
```
> this is needed from product

|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|_meta|Hash||true|||
|payment_id|String||true|||
|series_code|String||false|||
|number|Fixnum||false|||
|date|DateTime||true|||
|total|Float||true|||
|[currency](#Facturemosya_payment_receipt_currency)|Entities::Currency||true|||
|[billing_entity](#Facturemosya_payment_receipt_billing_entity)|Entities::BillingEntity||false|||
|[references](#Facturemosya_payment_receipt_references)|Array||false|[]||
|[paid_documents](#Facturemosya_payment_receipt_paid_documents)|Array||true|[]||
|[extra](#Facturemosya_payment_receipt_extra)|Facturemosya::Entities::PaymentExtra||true|||

### <a name='Facturemosya_payment_receipt_currency'></a>currency
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|code|String||true|||
|exchange|Float||true|||

### <a name='Facturemosya_payment_receipt_billing_entity'></a>billing_entity
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|identification_type|String||true|||
|identification|String||true|||
|name|String||true|||
|business|NilClass||false|||
|address|String||true|||
|street|String||false|||
|number|String||false|||
|subpremise|String||false|||
|district|String||false|||
|city|String||true|||
|country|String||true|||
|extra|Hash||false|||

### <a name='Facturemosya_payment_receipt_references'></a>references
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|id|String||false|||
|billing_document_id|String||false|||
|reason_id|String||false|||
|description|String||false|||
|external|Hash||false|||
|created_at|String||false|||
|updated_at|String||false|||

### <a name='Facturemosya_payment_receipt_paid_documents'></a>paid_documents
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|id|String||true|||
|number|Fixnum||true|||
|external_id|String||false|||
|series_code|String||true|||
|balance|Float||true|||
|paid_amount|Float||true|||
|[currency](#Facturemosya_payment_receipt_currency)|Entities::Currency||false|||
|[extra](#Facturemosya_payment_receipt_extra)|Facturemosya::Entities::Payments::InvoiceExtra||false|||

### currency
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|code|String||true|||
|exchange|Float||true|||

### extra
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|installment_plan_code|String||true|||

### <a name='Facturemosya_payment_receipt_extra'></a>extra
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|payment_method_code|String||true|||
|sender_bank_code|String||false|||
|sender_bank_name|String||false|||
|sender_bank_account|String||false|||
|beneficiary_bank_code|String||false|||
|beneficiary_bank_account|String||false|||

## CredNote
> To create a CredNote you must to use this payload

```json
{
  "_meta": {
    "type_code": "cred_note",
    "company_id": 1
  },
  "billing_document_id": "198",
  "number": "142",
  "date": "2019-08-01",
  "due_date": "2019-09-01",
  "currency": "MXN",
  "currency_exchange": 1.0,
  "numbering": "001",
  "payment_terms": "CC 15 días",
  "company": {
    "id": 1,
    "tin": "WLL090422JV9",
    "name": "CMS WOODHOUSE LORENTE LUDLOW",
    "address": "Reforma 115 Int Piso 19, Col. Lomas de Chapultepec, Del. Miguel Hidalgo, México D.F. 11000 ",
    "address_fields": {
       "subpremise": "Int Piso 19",
       "street_number": "115",
       "route": "Paseo de la Reforma",
       "neighborhood": "Lomas - Virreyes",
       "political": "Lomas de Chapultepec V Sección",
       "locality": "Ciudad de México",
       "administrative_area_level_1": "Ciudad de México",
       "country": "Mexico",
       "postal_code": "11300",
       "country_code": "MX",
       "country_id": 157,
       "single_address": "translation missing: es.address.mx.single_address_format"
    },
    "phone": "5526230552",
    "email": "null"
  },
  "billing_entity": {
    "identification_type": "31",
    "identification": "99511620-0",
    "name": "Lemontech SA",
    "business": "Tecnología",
    "address": "Los Militares 4777 of. 1904",
    "district": "Las Condes",
    "city": "Santiago",
    "country": "CL"
  },
  "document_lines": [
    {
      "code": "honorariums",
      "product": "Honorarios legales",
      "description": "Descripción de honorarios escrita por el usuario",
      "price": "100",
      "tax_code": "IVA",
      "tax_amount": 19,
      "quantity": 1,
      "tax_percentage": "19",
      "taxable": true,
      "extra": {
        "product_key": "80121600",
        "unit_key": "E48"
      }
    }
  ],
  "notes": "Esto es una observación",
  "extra": {
    "payment_method_code": "03",
    "installment_plan_code": "PUE",
    "receipt_type": "I",
    "order_number": "Número de orden",
    "branch_name": "Nombre de sucursal",
    "cfdi_use_code": "P00",
    "cfdi_related_type_code": "04",
    "external_id": "d1d069f7-962c-4c04-9274-43bafb27d3f9"
  },
  "references": [
    {
      "id": 464,
      "billing_document_id": 395,
      "reason_id": null,
      "description": "Esto es una descripción del primer doc. de referencia",
      "external": {
        "referred_document_external_id": "d1d069f7-962c-4c04-9274-43bafb27d3f9",
        "referred_document_type_external_code": "802",
        "referred_document_number": "34324",
        "referred_document_date": "2019-10-25"
      },
      "created_at": "2019-10-02T14:31:35.000Z",
      "updated_at": "2019-10-02T14:31:35.000Z"
    }
  ]
}
```
> this is needed from product

|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|[_meta](#Facturemosya_cred_note__meta)|Entities::Meta||false|||
|billing_document_id|String||true|||
|number|Fixnum||true|||
|date|DateTime||true|||
|due_date|DateTime||false|||
|currency|String||true|||
|currency_exchange|Float||false|||
|numbering|String||true|||
|payment_terms|String||false|||
|[company](#Facturemosya_cred_note_company)|Entities::Company||false|||
|[billing_entity](#Facturemosya_cred_note_billing_entity)|Entities::BillingEntity||true|||
|[document_lines](#Facturemosya_cred_note_document_lines)|Array||true|[]||
|notes|String||false|||
|[extra](#Facturemosya_cred_note_extra)|Facturemosya::Entities::InvoiceExtra||false|||
|[references](#Facturemosya_cred_note_references)|Array||false|[]||
|regime|String||false|601||

### <a name='Facturemosya_cred_note__meta'></a>_meta
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|type_code|String||true|||
|company_id|Fixnum||true|||

### <a name='Facturemosya_cred_note_company'></a>company
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|id|Fixnum||false|||
|tin|String||false|||
|name|String||false|||
|address|String||false|||
|address_fields|Hash||false|||
|phone|String||false|||
|email|String||false|||

### <a name='Facturemosya_cred_note_billing_entity'></a>billing_entity
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|identification_type|String||true|||
|identification|String||true|||
|name|String||true|||
|business|String||false|||
|address|String||true|||
|district|String||false|||
|city|String||true|||
|country|String||true|||

### <a name='Facturemosya_cred_note_document_lines'></a>document_lines
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|code|String||false|||
|product|String||true|||
|description|String||true|||
|price|Float||true|||
|tax_code|String||true|||
|tax_amount|Float||true|||
|quantity|Fixnum||true|||
|tax_percentage|Float||true|||
|taxable|TrueClass||true|||
|extra|Hash||false|||

### <a name='Facturemosya_cred_note_extra'></a>extra
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|cfdi_related_type_code|String||false|||
|payment_method_code|String||true|||
|installment_plan_code|String||true|||
|receipt_type|String||false|||
|order_number|String||false|||
|branch_name|String||false|||
|cfdi_use_code|String||false|||
|external_id|String||true|||

### <a name='Facturemosya_cred_note_references'></a>references
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|id|String||false|||
|billing_document_id|String||false|||
|reason_id|String||false|||
|description|String||false|||
|external|Hash||false|||
|created_at|String||false|||
|updated_at|String||false|||

# Datil
## Invoice
> To create a Invoice you must to use this payload

```json
{
  "_meta": {
    "type_code": "invoice",
    "company_id": 1
  },
  "company": {
    "id": 1,
    "tin": "0910000000001",
    "name": "CMS WOODHOUSE LORENTE LUDLOW",
    "address": "Reforma 115 Int Piso 19, Col. Lomas de Chapultepec, Del. Miguel Hidalgo, México D.F. 11000 ",
    "address_fields": {
      "subpremise": "Int Piso 19",
      "street_number": "115",
      "route": "Paseo de la Reforma",
      "neighborhood": "Lomas - Virreyes",
      "political": "Lomas de Chapultepec V Sección",
      "locality": "Ciudad de México",
      "administrative_area_level_1": "Ciudad de México",
      "country": "Mexico",
      "postal_code": "11300",
      "country_code": "MX",
      "country_id": 157
    },
    "phone": "5526230552",
    "email": null,
    "extra": {
      "branch_code": "004"
    }
  },
  "billing_document_id": "198",
  "number": "142",
  "numbering": "001",
  "date": "2019-11-21",
  "due_date": "2019-12-21",
  "currency": "USD",
  "billing_entity": {
    "identification_type": "05",
    "identification": "0987654321",
    "name": "Lemontech SA",
    "business": "Tecnología",
    "address": "Los Militares 4777 of. 1904",
    "district": "Las Condes",
    "city": "Santiago",
    "country": "CL",
    "extra": {
      "email": "hola@datil.com"
    }
  },
  "document_lines": [
    {
      "code": "honorariums",
      "product": "Honorarios legales",
      "description": "Descripción de honorarios escrita por el usuario",
      "price": "100",
      "tax_code": "2",
      "tax_amount": 14,
      "quantity": 1,
      "tax_percentage": "14",
      "taxable": true,
      "extra": {
        "tax_percentage_code": "2"
      }
    }
  ],
  "notes": "Esto es una observación",
  "extra": {
    "payment_method_code": "efectivo"
  },
  "references": [
    {
      "id": 464,
      "billing_document_id": 395,
      "description": "Esto es una descripción del primer doc. de referencia",
      "external": {
        "referred_document_external_id": "d1d069f7-962c-4c04-9274-43bafb27d3f9",
        "referred_document_type_external_code": "802",
        "referred_document_number": "34324",
        "referred_document_date": "2019-10-25"
      }
    }
  ]
}
```
> this is needed from product

|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|[_meta](#Datil_invoice__meta)|Entities::Meta||false|||
|[company](#Datil_invoice_company)|Entities::Company||false|||
|billing_document_id|String||true|||
|number|String||true|||
|numbering|String||true|||
|date|DateTime||true|||
|due_date|DateTime||true|||
|currency|String||true|||
|[billing_entity](#Datil_invoice_billing_entity)|Datil::Entities::BillingEntity||true|||
|[document_lines](#Datil_invoice_document_lines)|Array||true|[]||
|notes|String||false|||
|[extra](#Datil_invoice_extra)|Datil::Entities::InvoiceExtra||false|||
|[references](#Datil_invoice_references)|Array||false|[]||

### <a name='Datil_invoice__meta'></a>_meta
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|type_code|String||true|||
|company_id|Fixnum||true|||

### <a name='Datil_invoice_company'></a>company
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|id|Fixnum||false|||
|tin|String||false|||
|name|String||false|||
|address|String||false|||
|address_fields|Hash||false|||
|phone|String||false|||
|email|String||false|||
|extra|Hash||false|||

### <a name='Datil_invoice_billing_entity'></a>billing_entity
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|identification_type|String||true|||
|identification|String||true|||
|name|String||true|||
|business|String||false|||
|address|String||true|||
|district|String||false|||
|city|String||true|||
|country|String||true|||
|[extra](#Datil_invoice_extra)|Datil::Entities::BillingEntityExtra||true|||

### extra
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|email|String||true|||

### <a name='Datil_invoice_document_lines'></a>document_lines
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|code|String||false|||
|product|String||true|||
|description|String||true|||
|price|Float||true|||
|tax_code|String||true|||
|tax_amount|Float||true|||
|quantity|Fixnum||true|||
|tax_percentage|Float||true|||
|taxable|TrueClass||true|||
|[extra](#Datil_invoice_extra)|Datil::Entities::InvoiceLineExtra||false|||

### extra
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|tax_percentage_code|String||true|||

### <a name='Datil_invoice_extra'></a>extra
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|payment_method_code|String||true|||

### <a name='Datil_invoice_references'></a>references
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|id|String||false|||
|billing_document_id|String||false|||
|description|String||false|||
|external|Hash||false|||

## CredNote
> To create a CredNote you must to use this payload

```json
{
  "_meta": {
    "type_code": "invoice",
    "company_id": 1
  },
  "company": {
    "id": 1,
    "tin": "0910000000001",
    "name": "CMS WOODHOUSE LORENTE LUDLOW",
    "address": "Reforma 115 Int Piso 19, Col. Lomas de Chapultepec, Del. Miguel Hidalgo, México D.F. 11000 ",
    "address_fields": {
      "subpremise": "Int Piso 19",
      "street_number": "115",
      "route": "Paseo de la Reforma",
      "neighborhood": "Lomas - Virreyes",
      "political": "Lomas de Chapultepec V Sección",
      "locality": "Ciudad de México",
      "administrative_area_level_1": "Ciudad de México",
      "country": "Mexico",
      "postal_code": "11300",
      "country_code": "MX",
      "country_id": 157
    },
    "phone": "5526230552",
    "email": null,
    "extra": {
      "branch_code": "004"
    }
  },
  "billing_document_id": "198",
  "number": "142",
  "numbering": "001",
  "date": "2019-11-21",
  "due_date": "2019-12-21",
  "currency": "USD",
  "billing_entity": {
    "identification_type": "05",
    "identification": "0987654321",
    "name": "Lemontech SA",
    "business": "Tecnología",
    "address": "Los Militares 4777 of. 1904",
    "district": "Las Condes",
    "city": "Santiago",
    "country": "CL",
    "extra": {
      "email": "hola@datil.com"
    }
  },
  "document_lines": [
    {
      "code": "honorariums",
      "product": "Honorarios legales",
      "description": "Descripción de honorarios escrita por el usuario",
      "price": "100",
      "tax_code": "2",
      "tax_amount": 14,
      "quantity": 1,
      "tax_percentage": "14",
      "taxable": true,
      "extra": {
        "tax_percentage_code": "2"
      }
    }
  ],
  "notes": "Esto es una observación",
  "extra": {
    "payment_method_code": "efectivo"
  },
  "references": [
    {
      "id": 464,
      "billing_document_id": 395,
      "description": "Esto es una descripción del primer doc. de referencia",
      "external": {
        "referred_document_external_id": "d1d069f7-962c-4c04-9274-43bafb27d3f9",
        "referred_document_type_external_code": "802",
        "referred_document_number": "34324",
        "referred_document_date": "2019-10-25"
      }
    }
  ]
}
```
> this is needed from product

|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|[_meta](#Datil_cred_note__meta)|Entities::Meta||false|||
|[company](#Datil_cred_note_company)|Entities::Company||false|||
|billing_document_id|String||true|||
|number|String||true|||
|numbering|String||true|||
|date|DateTime||true|||
|due_date|DateTime||false|||
|currency|String||true|||
|[billing_entity](#Datil_cred_note_billing_entity)|Datil::Entities::BillingEntity||true|||
|[document_lines](#Datil_cred_note_document_lines)|Array||true|[]||
|notes|String||false|||
|[extra](#Datil_cred_note_extra)|Datil::Entities::CreditNoteExtra||false|||
|[references](#Datil_cred_note_references)|Array||false|[]||

### <a name='Datil_cred_note__meta'></a>_meta
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|type_code|String||true|||
|company_id|Fixnum||true|||

### <a name='Datil_cred_note_company'></a>company
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|id|Fixnum||false|||
|tin|String||false|||
|name|String||false|||
|address|String||false|||
|address_fields|Hash||false|||
|phone|String||false|||
|email|String||false|||
|extra|Hash||false|||

### <a name='Datil_cred_note_billing_entity'></a>billing_entity
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|identification_type|String||true|||
|identification|String||true|||
|name|String||true|||
|business|String||false|||
|address|String||true|||
|district|String||false|||
|city|String||true|||
|country|String||true|||
|[extra](#Datil_cred_note_extra)|Datil::Entities::BillingEntityExtra||true|||

### extra
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|email|String||true|||

### <a name='Datil_cred_note_document_lines'></a>document_lines
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|code|String||false|||
|product|String||true|||
|description|String||true|||
|price|Float||true|||
|tax_code|String||true|||
|tax_amount|Float||true|||
|quantity|Fixnum||true|||
|tax_percentage|Float||true|||
|taxable|TrueClass||true|||
|[extra](#Datil_cred_note_extra)|Datil::Entities::InvoiceLineExtra||false|||

### extra
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|tax_percentage_code|String||true|||

### <a name='Datil_cred_note_extra'></a>extra
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|payment_method_code|String||true|||

### <a name='Datil_cred_note_references'></a>references
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|id|String||false|||
|billing_document_id|String||false|||
|description|String||false|||
|external|Hash||false|||

# Siigo
## Invoice
> To create a Invoice you must to use this payload

```json
{
  "billing_document_id": 346,
  "company_id": 1,
  "number": 2,
  "type": "34",
  "type_code": "bill",
  "date": "2019-10-29",
  "due_date": null,
  "currency": "CLP",
  "currency_exchange": 1.0,
  "numbering": null,
  "billing_entity":{
     "identification_type": "tin",
     "identification": "96.509.660-4",
     "name": "Banco Falabella",
     "business": "Actividades Bancarias",
     "address": "Moneda 970, piso 7",
     "district": "Santiago",
     "city": "Santiago",
     "country": "CL",
     "phone": 0
  },
  "user":{
     "external_code": 123
  },
  "requester":{
     "email": "glara@lemontech.com",
     "phone": "912345678",
     "name": "Ignacio Canals"
  },
  "document_lines":[
     {
        "code": "honorariums",
        "product": "Honorarios",
        "description": "Honorarios",
        "price": 2239.0,
        "tax_code": "IVA",
        "tax_amount": 403.02,
        "quantity": 1,
        "tax_percentage": 18.0,
        "taxable": true
     }
  ],
  "notes": "Esto es una observación en la factura",
  "reference": {

  },
  "extra": {

  },
  "references": [
  ]
}
```
> this is needed from product

|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|billing_document_id|String||true|||
|company_id|Fixnum||false|||
|number|Fixnum||true|||
|type|String||false|||
|date|DateTime||true|||
|due_date|NilClass||false|||
|currency|String||true|||
|currency_exchange|Float||false|||
|numbering|String||true|||
|[billing_entity](#Siigo_invoice_billing_entity)|Siigo::Entities::BillingEntity||true|||
|user|Hash||false|||
|requester|Hash||false|||
|[document_lines](#Siigo_invoice_document_lines)|Array||true|[]||
|notes|String||false|||
|extra|Hash||false|||
|[references](#Siigo_invoice_references)|Array||false|[]||

### <a name='Siigo_invoice_billing_entity'></a>billing_entity
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|identification_type|String||true|||
|identification|String||true|||
|name|String||true|||
|business|String||false|||
|address|String||true|||
|district|String||false|||
|city|String||true|||
|country|String||true|||
|phone|String||false|||

### <a name='Siigo_invoice_document_lines'></a>document_lines
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|
|code|String||false|||
|product|String||true|||
|description|String||true|||
|price|Float||true|||
|tax_code|String||true|||
|tax_amount|Float||true|||
|quantity|Fixnum||true|||
|tax_percentage|Float||true|||
|taxable|TrueClass||true|||

### <a name='Siigo_invoice_references'></a>references
|Attribute|Type|Format|Required|Default|Description|
|---------|----|------|--------|-------|-----------|




# Kittens

## Get All Kittens

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```


```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```


```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

