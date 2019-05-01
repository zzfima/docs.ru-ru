---
title: Расширение системы метаданных
ms.date: 03/30/2017
helpviewer_keywords:
- extending metadata [WCF]
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
ms.openlocfilehash: 7ccef0c2b908a8f78249742decd6c46a862e541e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991306"
---
# <a name="extending-the-metadata-system"></a>Расширение системы метаданных
Система метаданных Windows Communication Foundation (WCF) — это набор классов и интерфейсов, представляющих метаданные, необходимые для реализации приложений на основе службы. Можно изменять или расширять классы, реализовывать и настраивать интерфейсы для экспорта и импорта пользовательских метаданных, например расширений языка WSDL или пользовательских утверждений WS-PolicyAttachments.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Экспорт пользовательских метаданных для расширения WCF](../../../../docs/framework/wcf/extending/exporting-custom-metadata-for-a-wcf-extension.md)  
 Содержит описание, как реализовать и использовать интерфейс <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> для внедрения в документы WSDL пользовательских утверждений политики.  
  
 [Импорт пользовательских метаданных для расширения WCF](../../../../docs/framework/wcf/extending/importing-custom-metadata-for-a-wcf-extension.md)  
 Содержит описание, как реализовать и использовать интерфейс <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> для чтения пользовательских утверждений политики в документах WSDL и ответа на них.  
  
 [Публикация и получение метаданных через пользовательскую привязку](../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 Содержит описание обмена данными для пользовательских привязок.
