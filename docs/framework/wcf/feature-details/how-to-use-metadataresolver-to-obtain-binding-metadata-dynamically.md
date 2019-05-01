---
title: Практическое руководство. Использование MetadataResolver для динамического получения метаданных привязки
ms.date: 03/30/2017
ms.assetid: 56ffcb99-fff0-4479-aca0-e3909009f605
ms.openlocfilehash: 3fe09699304de42ed00312f50f3b9e0edb20615d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62047559"
---
# <a name="how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically"></a>Практическое руководство. Использование MetadataResolver для динамического получения метаданных привязки
В этом разделе показано, как использовать класс <xref:System.ServiceModel.Description.MetadataResolver> для динамического получения метаданных привязки.  
  
### <a name="to-dynamically-obtain-binding-metadata"></a>Динамическое получение метаданных привязки  
  
1. Создайте объект <xref:System.ServiceModel.EndpointAddress> с адресом конечной точки метаданных.  
  
    ```  
    EndpointAddress metaAddress  
      = new EndpointAddress(new   Uri("http://localhost:8080/SampleService/mex"));  
    ```  
  
2. Вызовите метод <xref:System.ServiceModel.Description.MetadataResolver.Resolve%28System.Type%2CSystem.ServiceModel.EndpointAddress%29>, передающий тип службы и адрес конечной точки метаданных. Возвращается коллекция конечных точек, реализующих указанный контракт. Из метаданных импортируются только сведения о привязке; сведения о контракте не импортируются. Вместо этого используется предоставленный контракт.  
  
    ```  
    ServiceEndpointCollection endpoints = MetadataResolver.Resolve(typeof(SampleServiceClient),metaAddress);  
    ```  
  
3. Затем можно последовательно просмотреть коллекцию конечных точек службы, чтобы извлечь требуемые сведения о привязке. Приведенный ниже код просматривает конечные точки, создает объект клиента службы, который передает привязку и адрес, связанный с текущей конечной точкой, а затем вызывает метод службы.  
  
    ```  
    foreach (ServiceEndpoint point in endpoints)  
    {  
       if (point != null)  
       {  
          // Create a new wcfClient using retrieved endpoints.  
          using (wcfClient = new SampleServiceClient(point.Binding, point.Address))  
          {  
             Console.WriteLine(  
               wcfClient.SampleMethod("Client used the "  
               + point.Address.ToString() + " address."));  
          }  
      }  
    }  
    ```  
  
## <a name="see-also"></a>См. также

- [Метаданные](../../../../docs/framework/wcf/feature-details/metadata.md)
