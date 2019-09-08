---
title: Расширение системы метаданных
ms.date: 03/30/2017
helpviewer_keywords:
- extending metadata [WCF]
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
ms.openlocfilehash: d3ce7e1a228e6303be1009c7b72f4e889b40c536
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795723"
---
# <a name="extending-the-metadata-system"></a>Расширение системы метаданных
Система метаданных Windows Communication Foundation (WCF) — это группа классов и интерфейсов, представляющих метаданные, необходимые для реализации приложений на основе служб. Можно изменять или расширять классы, реализовывать и настраивать интерфейсы для экспорта и импорта пользовательских метаданных, например расширений языка WSDL или пользовательских утверждений WS-PolicyAttachments.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Экспорт пользовательских метаданных для расширения WCF](exporting-custom-metadata-for-a-wcf-extension.md)  
 Содержит описание, как реализовать и использовать интерфейс <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> для внедрения в документы WSDL пользовательских утверждений политики.  
  
 [Импорт пользовательских метаданных для расширения WCF](importing-custom-metadata-for-a-wcf-extension.md)  
 Содержит описание, как реализовать и использовать интерфейс <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> для чтения пользовательских утверждений политики в документах WSDL и ответа на них.  
  
 [Публикация и получение метаданных через пользовательскую привязку](publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 Содержит описание обмена данными для пользовательских привязок.
