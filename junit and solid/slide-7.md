# e-invoicing

[prev](./slide-6.md) / [back](./README.md)


## Hide EntityPublisher

Instead of low level EntityPublisher use services with arguments from domain of this program.

Each microservice to use its own services that operate in local domain arguments.

### Instead of

```java
       InvoiceDTO invoiceDto = entityPublisher.registryInvoiceFrtinv(
                frtinvDto.setUuid(incomingInvoice.getMessageUuid())
                        .setStatus(WAIT_PDF)
                        .setProcessType(ProcessType.KNLOBI)
                        .setOutputMethod(convertToDbOutputMethod(outputMethod))
        );
```

### Have this

```java
invoiceService.registerInvoice(invoiceDto);
```