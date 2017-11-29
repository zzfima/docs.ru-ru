---
title: "Практическое руководство. Импорт метаданных в конечные точки службы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b69dbe20-92a1-4911-89d8-ffbc3dad4663
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ca59de38ddb37260de5106a65419ebdc46f73151
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-import-metadata-into-service-endpoints"></a>Практическое руководство. Импорт метаданных в конечные точки службы
В этом разделе объясняется, как импортировать метаданные в коллекцию конечных точек службы и использовать службы, определенные в [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md). Кроме того, в этом разделе демонстрируется создание клиентского приложения, импортирующего метаданные из службы, а затем вызывающего в службе метод `Add`.  
  
### <a name="to-import-metadata-into-service-endpoints"></a>Импорт метаданных в конечные точки службы  
  
1.  Объявите объект <xref:System.ServiceModel.EndpointAddress> и инициализируйте его с помощью универсального кода ресурса (URI) для адреса обмена метаданными (MEX) этой службы.  
  
     [!code-csharp[UE_ImportMetadata#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#0)]  
  
2.  Создайте клиент <xref:System.ServiceModel.Description.MetadataExchangeClient>, передающий адрес MEX, и вызовите метод <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>. Это позволяет извлечь метаданные из службы.  
  
     [!code-csharp[UE_ImportMetadata#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#1)]  
  
3.  Создайте устройство импорта <xref:System.ServiceModel.Description.WsdlImporter>, передающее ранее извлеченные метаданные, и вызовите метод <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>. Эти действия позволяют создать коллекцию объектов <xref:System.ServiceModel.Description.ContractDescription>. В зависимости от потребностей также можно было вызвать метод <xref:System.ServiceModel.Description.WsdlImporter.ImportAllEndpoints%2A> или <xref:System.ServiceModel.Description.WsdlImporter.ImportAllBindings%2A>  
  
     [!code-csharp[UE_ImportMetadata#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#2)]  
  
    > [!NOTE]
    >  После импорта метаданных невозможно будет создать клиентский канал или экспортировать метаданные. Это объясняется тем, что на данном этапе не имеется никакой информации о типе. Информация о типе требуется для фактического взаимодействия со службой или экспорта метаданных. Для создания сведений о типе необходимо создать код, показанный в шагах 4 и 5. Кроме того, можно использовать вспомогательный класс <xref:System.ServiceModel.Description.MetadataResolver>. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Как: использование MetadataResolver для динамического получения метаданных привязки](../../../../docs/framework/wcf/feature-details/how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md).  
  
4.  Создайте информацию о типе для каждого контракта.  
  
     [!code-csharp[UE_ImportMetadata#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#3)]  
  
5.  Теперь этой информацией можно пользоваться. В следующем примере кода создается исходный код C#.  
  
     [!code-csharp[UE_ImportMetadata#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#4)]  
  
## <a name="see-also"></a>См. также  
 [Метаданные](../../../../docs/framework/wcf/feature-details/metadata.md)  
 [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md)
