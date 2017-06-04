---
title: "Извлечение метаданных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "метаданные [WCF], извлечение"
ms.assetid: 18d8ba4c-af0f-4827-a50b-4202d767bacc
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Извлечение метаданных
Извлечение метаданных — это процесс запроса и извлечения метаданных из конечной точки метаданных, например конечной точки метаданных WS\-MetadataExchange \(MEX\) или конечной точки метаданных HTTP\/GET.  
  
## Извлечение метаданных с помощью программы командной строки Svcutil.exe  
 Метаданные службы можно извлечь с помощью протокола WS\-MetadataExchange и запросов HTTP\/GET, воспользовавшись для этого средством [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) и передав ему параметр `/target:metadata` и адрес.Средство Svcutil.exe загружает метаданные, расположенные по указанному адресу, и сохраняет файл на диске.Средство Svcutil.exe использует внутри себя экземпляр <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName> и загружает из конфигурации конфигурацию конечной точки <xref:System.ServiceModel.Description.IMetadataExchange>, имя которой соответствует схеме адреса, переданного в качестве входных данных средству Svcutil.exe.  
  
## Извлечение метаданных программным образом с помощью класса MetadataExchangeClient  
 Среда [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] позволяет извлекать метаданные служб с помощью стандартизованных протоколов, например WS\-MetadataExchange и запросов HTTP\/GET.Оба эти протокола поддерживаются типом <xref:System.ServiceModel.Description.MetadataExchangeClient>.Чтобы получить метаданные службы с помощью типа <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName>, необходимо указать адрес конечной точки метаданных и необязательную привязку.В роли привязки, используемой экземпляром <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName>, может выступать одна из привязок по умолчанию статического класса <xref:System.ServiceModel.Description.MetadataExchangeBindings>, предоставляемая пользователем привязка или привязка, загруженная из конфигурации конечной точки для контракта `IMetadataExchange`.Кроме того, тип <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName> может выполнять разрешение URL\-адресов ссылок HTTP на метаданные с помощью типа <xref:System.Net.HttpWebRequest>.  
  
 По умолчанию экземпляр <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName> связан с одним экземпляром <xref:System.ServiceModel.ChannelFactory>.Можно изменить или заменить экземпляр <xref:System.ServiceModel.ChannelFactory?displayProperty=fullName>, используемый экземпляром <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName>, переопределив виртуальный метод <xref:System.ServiceModel.Description.MetadataExchangeClient.GetChannelFactory%2A>.Аналогично можно изменить или заменить экземпляр <xref:System.Net.HttpWebRequest>, используемый экземпляром <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName> для создания запросов HTTP\/GET, переопределив виртуальный метод <xref:System.ServiceModel.Description.MetadataExchangeClient.GetWebRequest%2A?displayProperty=fullName>.  
  
## В этом разделе  
 [Как использовать Svcutil.exe для загрузки документов метаданных](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)  
 Загрузка документов метаданных с помощью средства Svcutil.exe.  
  
 [Как использовать MetadataResolver для динамического получения метаданных привязки](../../../../docs/framework/wcf/feature-details/how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md)  
 Получение метаданных привязки динамически во время выполнения с помощью класса <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=fullName>.  
  
 [Как использовать MetadataExchangeClient для получения метаданных](../../../../docs/framework/wcf/feature-details/how-to-use-metadataexchangeclient-to-retrieve-metadata.md)  
 Использование класса <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName> для загрузки файлов метаданных в объект <xref:System.ServiceModel.Description.MetadataSet?displayProperty=fullName>, содержащий объекты <xref:System.ServiceModel.Description.MetadataSection?displayProperty=fullName>, для записи в файлы или для других целей.  
  
## См. также  
 <xref:System.ServiceModel.Description.MetadataExchangeClient>