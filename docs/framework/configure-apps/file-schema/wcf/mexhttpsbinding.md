---
title: "&lt;mexHttpsBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# &lt;mexHttpsBinding&gt;
Задает параметры для привязки, используемой для обмена сообщениями WS\-MetadataExchange \(WS\-MEX\) посредством HTTPS.  
  
## Синтаксис  
  
```  
  
<mexHttpsBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan">  
   </binding>  
</mexHttpsBinding>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`closeTimeout`|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия.  Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.  Значение по умолчанию \- 00:01:00.|  
|`name`|Строка, содержащая имя конфигурации привязки.  Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки.  Каждая привязка имеет атрибуты `name` и `namespace`, которые совместно однозначно идентифицируют привязку в метаданных службы.  Кроме того, это имя является уникальным среди привязок одного типа.  Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.  Дополнительные сведения о конфигурации по умолчанию и о безымянных привязках и поведениях см. в разделах [Упрощенная конфигурация](../../../../../docs/framework/wcf/simplified-configuration.md) и [Упрощенная конфигурация служб WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
|`openTimeout`|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия.  Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.  Значение по умолчанию \- 00:01:00.|  
|`receiveTimeout`|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения.  Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.  Значение по умолчанию \- 00:10:00.|  
|`sendTimeout`|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки.  Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>.  Значение по умолчанию \- 00:01:00.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<привязки\>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|Этот элемент содержит коллекцию стандартных и пользовательских привязок.|  
  
## Заметки  
 Эта привязка по существу является привязкой `WSHttpBinding`, которая поддерживает безопасность уровня транспорта с помощью сертификатов.  Дополнительные сведения о настройке и использовании такой конечной точки метаданных см. в разделах [Практическое руководство. Настройка пользовательской привязки для обмена WS\-Metadata](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [Как получить метаданные через привязку, не использующую MEX](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), а образец см. в разделе [Пользовательская конечная точка защищенных метаданных](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).  
  
## См. также  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>   
 <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>   
 [Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)   
 [Публикация и получение метаданных через пользовательскую привязку](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)   
 [Практическое руководство. Настройка пользовательской привязки для обмена WS\-Metadata](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)   
 [Как получить метаданные через привязку, не использующую MEX](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)   
 [Пользовательская конечная точка защищенных метаданных](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)   
 [Метаданные](../../../../../docs/framework/wcf/feature-details/metadata.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ru-ru/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<привязка\>](../../../../../docs/framework/misc/binding.md)