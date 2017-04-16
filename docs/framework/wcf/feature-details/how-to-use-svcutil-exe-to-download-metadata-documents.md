---
title: "Как использовать Svcutil.exe для загрузки документов метаданных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 15524274-3167-4627-b722-d6cedb9fa8c6
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Как использовать Svcutil.exe для загрузки документов метаданных
Средство Svcutil.exe позволяет загружать метаданные из выполняющихся служб и сохранять эти метаданные в локальных файлах.Для URL\-схем HTTP и HTTPS средство Svcutil.exe предпринимает попытку извлечь метаданные с помощью протокола WS\-MetadataExchange и метода [Обнаружения XML\-веб\-служб](http://go.microsoft.com/fwlink/?LinkId=94950).Для всех остальных URL\-схем средство Svcutil.exe использует только протокол WS\-MetadataExchange.  
  
 По умолчанию средство Svcutil.exe использует привязки, определенные в классе <xref:System.ServiceModel.Description.MetadataExchangeBindings>.Чтобы настроить привязку, используемую для протокола WS\-MetadataExchange, необходимо в файле конфигурации Svcutil.exe \(svcutil.exe.config\) настроить конечную точку клиента, которая бы использовала контракт `IMetadataExchange` и имя которой совпадало бы со схемой универсального кода ресурса \(URI\) адреса конечной точки метаданных.  
  
> [!CAUTION]
>  Если программа Svcutil.exe запускается, чтобы получить метаданные для службы, которая предоставляет доступ к двум различным контрактам службы, которые содержат операции с одинаковыми именами, то программа Svcutil.exe выводит ошибку «Не удается получить метаданные из...». Например, так происходит, если служба предоставляет доступ к контракту службы с именем ICarService. который содержит операцию Get\(Car c\), а также к контракту службы с именем IBookService, который содержит операцию Get\(Book b\).Чтобы устранить эту проблему, выполните одно из следующих действий.  
>   
>  -   Переименуйте одну из операций  
> -   Задайте другое имя в свойстве <xref:System.ServiceModel.OperationContractAttribute.Name%2A>.  
> -   Установите другое пространство имен для одной из операций с помощью свойства <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.  
  
### Загрузка метаданных с помощью средства Svcutil.exe  
  
1.  Найдите средство Svcutil.exe в следующей папке:  
  
     C:\\Program Files\\Microsoft SDKs\\Windows\\v1.0.\\bin  
  
2.  Из командной строки запустите средство, используя следующий формат.  
  
    ```  
    svcutil.exe /t:metadata  <url>* | <epr>  
    ```  
  
     Параметр `/t:metadata` необходимо указать, чтобы загружались метаданные.В противном случае будут созданы код и конфигурация клиента.  
  
3.  Аргумент \<`url`\>задает URL\-адрес конечной точки службы, которая предоставляет метаданные, или размещенного в сети документа с метаданными.Аргумент \<`epr`\> задает путь к XML\-файлу, содержащему адрес `EndpointAddress` WS\-Addressing конечной точки службы, поддерживающей протокол WS\-MetadataExchange.  
  
 Сведения о других вариантах использования этого средства для загрузки метаданных см. в разделе [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
## Пример  
 Следующая команда позволяет загрузить документы с метаданными из выполняющейся службы.  
  
```  
svcutil /t:metadata http://service/metadataEndpoint  
```  
  
## См. также  
 [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)