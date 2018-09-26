---
title: Практическое руководство. Использование Svcutil.exe для загрузки документов метаданных
ms.date: 03/30/2017
ms.assetid: 15524274-3167-4627-b722-d6cedb9fa8c6
ms.openlocfilehash: 6643f0a5dba98afcef38870cf24d91e7d69a1440
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47080848"
---
# <a name="how-to-use-svcutilexe-to-download-metadata-documents"></a>Практическое руководство. Использование Svcutil.exe для загрузки документов метаданных
Средство Svcutil.exe позволяет загружать метаданные из выполняющихся служб и сохранять эти метаданные в локальных файлах. Для схем HTTP и HTTPS URL-адрес Svcutil.exe предпринимает попытку извлечь метаданные с помощью WS-MetadataExchange и [обнаружение веб-служб XML](https://go.microsoft.com/fwlink/?LinkId=94950). Для всех остальных URL-схем средство Svcutil.exe использует только протокол WS-MetadataExchange.  
  
 По умолчанию средство Svcutil.exe использует привязки, определенные в классе <xref:System.ServiceModel.Description.MetadataExchangeBindings>. Чтобы настроить привязку, используемую для протокола WS-MetadataExchange, необходимо в файле конфигурации Svcutil.exe (svcutil.exe.config) настроить конечную точку клиента, которая бы использовала контракт `IMetadataExchange` и имя которой совпадало бы со схемой универсального кода ресурса (URI) адреса конечной точки метаданных.  
  
> [!CAUTION]
> При запуске Svcutil.exe получить метаданные для службы, которая предоставляет две разные службы контрактов, что каждый содержат операции с тем же именем, Svcutil.exe выводит сообщение об ошибке говорит: «Не удается получить метаданные из...» Например, если у вас есть службы, которая предоставляет контракт службы с именем `ICarService` , содержащий операцию `Get(Car c)` и той же службы предоставляет доступ к контракту службы с именем `IBookService` , содержащий операцию `Get(Book b)`. Чтобы устранить эту проблему, выполните одно из следующих действий.
>
> - Переименуйте одну из операций.
> - Задайте другое имя в свойстве <xref:System.ServiceModel.OperationContractAttribute.Name%2A>.
> - Установите другое пространство имен для одной из операций с помощью свойства <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.
  
## <a name="to-download-metadata-using-svcutilexe"></a>Загрузка метаданных с помощью средства Svcutil.exe  
  
1.  Найдите средство Svcutil.exe в следующей папке:  
  
     C:\Program Files\Microsoft SDKs\Windows\v1.0.\bin  
  
2.  Из командной строки запустите средство, используя следующий формат.  
  
    ```  
    svcutil.exe /t:metadata  <url>* | <epr>  
    ```  
  
     Параметр `/t:metadata` необходимо указать, чтобы загружались метаданные. В противном случае будут созданы код и конфигурация клиента.  
  
3.  <`url`> Аргумент задает URL-адрес конечной точки службы, которая предоставляет метаданные или документ метаданных, размещенного в сети. <`epr`> Аргумент задает путь к XML-файл, содержащий WS-Addressing `EndpointAddress` для конечной точки службы, поддерживающей протокол WS-MetadataExchange.  
  
 Дополнительные сведения об использовании этого средства для загрузки метаданных, см. в разделе [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
## <a name="example"></a>Пример  
 Следующая команда позволяет загрузить документы с метаданными из выполняющейся службы.  
  
```  
svcutil /t:metadata http://service/metadataEndpoint  
```  
  
## <a name="see-also"></a>См. также  
 [Служебная программа для метаданных ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
