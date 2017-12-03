---
title: "Расширение системы метаданных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: extending metadata [WCF]
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d0c729850e25e9fe4bec37dc366053de8c56f210
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="extending-the-metadata-system"></a>Расширение системы метаданных
Система метаданных [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] является набором классов и интерфейсов, представляющих метаданные, необходимые для реализации приложений на основе служб. Можно изменять или расширять классы, реализовывать и настраивать интерфейсы для экспорта и импорта пользовательских метаданных, например расширений языка WSDL или пользовательских утверждений WS-PolicyAttachments.  
  
## <a name="in-this-section"></a>Содержание  
 [Экспорт пользовательских метаданных для расширения WCF](../../../../docs/framework/wcf/extending/exporting-custom-metadata-for-a-wcf-extension.md)  
 Содержит описание, как реализовать и использовать интерфейс <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> для внедрения в документы WSDL пользовательских утверждений политики.  
  
 [Импорт пользовательских метаданных для расширения WCF](../../../../docs/framework/wcf/extending/importing-custom-metadata-for-a-wcf-extension.md)  
 Содержит описание, как реализовать и использовать интерфейс <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> для чтения пользовательских утверждений политики в документах WSDL и ответа на них.  
  
 [Публикация и получение метаданных через настраиваемую привязку.](../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 Содержит описание обмена данными для пользовательских привязок.
