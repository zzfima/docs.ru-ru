---
title: Практическое руководство. Использование MetadataExchangeClient для получения метаданных
ms.date: 03/30/2017
ms.assetid: 0754e9dc-13c5-45c2-81b5-f3da466e5a87
ms.openlocfilehash: c9558e1943c3886a61c3b19801e22d57732e459a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968749"
---
# <a name="how-to-use-metadataexchangeclient-to-retrieve-metadata"></a>Практическое руководство. Использование MetadataExchangeClient для получения метаданных
Используйте класс <xref:System.ServiceModel.Description.MetadataExchangeClient> для загрузки метаданных по протоколу WS-MetadataExchange (MEX). Извлеченные файлы метаданных возвращаются в виде объекта <xref:System.ServiceModel.Description.MetadataSet>. Возвращенный объект <xref:System.ServiceModel.Description.MetadataSet> содержит коллекцию объектов <xref:System.ServiceModel.Description.MetadataSection>, каждый из которых содержит конкретный диалект метаданных и идентификатор. Возвращенные метаданные можно записать в файлы или (если метаданные содержат документы WSDL) импортировать с помощью <xref:System.ServiceModel.Description.WsdlImporter>.  
  
 Конструкторы <xref:System.ServiceModel.Description.MetadataExchangeClient>, получающие адрес, используют привязку в статическом классе <xref:System.ServiceModel.Description.MetadataExchangeBindings>, который соответствует схеме универсального кода ресурса (URI) этого адреса. В качестве альтернативы можно использовать конструктор <xref:System.ServiceModel.Description.MetadataExchangeClient>, позволяющий явно задать используемую привязку. Заданная привязка применяется для распознавания всех ссылок на метаданные.  
  
 Как и любой другой клиент Windows Communication Foundation (WCF), <xref:System.ServiceModel.Description.MetadataExchangeClient> тип предоставляет конструктор для загрузки конфигураций клиентских конечных точек с помощью имени конфигурации конечной точки. Заданная конфигурация конечной точки должна определять контракт <xref:System.ServiceModel.Description.IMetadataExchange>. Адрес в конфигурации конечной точки не загружается, поэтому следует использовать одну из перегрузок <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>, которые получают адрес. При задании адреса метаданных с помощью экземпляра <xref:System.ServiceModel.EndpointAddress> клиент <xref:System.ServiceModel.Description.MetadataExchangeClient> предполагает, что этот адрес соответствует конечной точке MEX. Если адрес метаданных задается в виде URL-адреса, необходимо также задать используемый режим <xref:System.ServiceModel.Description.MetadataExchangeClientMode> - MEX или HTTP GET.  
  
> [!IMPORTANT]
> По умолчанию <xref:System.ServiceModel.Description.MetadataExchangeClient> распознает все ссылки, включая импорт WSDL, а также импорт схемы XML и включаемые элементы. Эту функцию можно отключить, задав для свойства <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> значение `false`. Максимальным количеством распознаваемых ссылок можно управлять с помощью свойства <xref:System.ServiceModel.Description.MetadataExchangeClient.MaximumResolvedReferences%2A>. Это свойство можно использовать совместно со свойством `MaxReceivedMessageSize` в привязке для управления объемом извлекаемых метаданных.  
  
### <a name="to-use-metadataexchangeclient-to-obtain-metadata"></a>Использование MetadataExchangeClient для получения метаданных  
  
1. Создайте новый объект <xref:System.ServiceModel.Description.MetadataExchangeClient>, явно задав привязку, имя конфигурации конечной точки или адрес метаданных.  
  
2. Настройте <xref:System.ServiceModel.Description.MetadataExchangeClient> в соответствии с требованиями. Например, можно задать учетные данные, которые должны использоваться при запросе метаданных, указать способ распознавания ссылок на метаданные и задать свойство <xref:System.ServiceModel.Description.MetadataExchangeClient.OperationTimeout%2A> для определения времени ожидания ответа на запрос метаданных.  
  
3. Получите объект <xref:System.ServiceModel.Description.MetadataSet>, который содержит извлеченные метаданные, вызвав один из методов <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>. Обратите внимание, что если при создании <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> явно задан адрес, можно использовать только перегрузку <xref:System.ServiceModel.Description.MetadataExchangeClient>, которая не получает аргументов.  
  
## <a name="example"></a>Пример  
 В следующем коде показано использование <xref:System.ServiceModel.Description.MetadataExchangeClient> для загрузки и перечисления файлов метаданных.  

 [!code-csharp[MetadataResolver#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/metadataresolver/cs/client.cs#3)]  

## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы скомпилировать этот пример кода, необходимо сделать ссылку на сборку System.ServiceModel.dll и импортировать пространство имен <xref:System.ServiceModel.Description>.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Description.MetadataResolver>
- <xref:System.ServiceModel.Description.MetadataExchangeClient>
- <xref:System.ServiceModel.Description.WsdlImporter>
