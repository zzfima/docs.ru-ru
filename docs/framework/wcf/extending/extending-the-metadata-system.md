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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cab59f5ddebdcc1e50921d5540d411e32b562341
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="extending-the-metadata-system"></a><span data-ttu-id="a6c2a-102">Расширение системы метаданных</span><span class="sxs-lookup"><span data-stu-id="a6c2a-102">Extending the Metadata System</span></span>
<span data-ttu-id="a6c2a-103">Система метаданных [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] является набором классов и интерфейсов, представляющих метаданные, необходимые для реализации приложений на основе служб.</span><span class="sxs-lookup"><span data-stu-id="a6c2a-103">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="a6c2a-104">Можно изменять или расширять классы, реализовывать и настраивать интерфейсы для экспорта и импорта пользовательских метаданных, например расширений языка WSDL или пользовательских утверждений WS-PolicyAttachments.</span><span class="sxs-lookup"><span data-stu-id="a6c2a-104">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a6c2a-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="a6c2a-105">In This Section</span></span>  
 [<span data-ttu-id="a6c2a-106">Экспорт пользовательских метаданных для расширения WCF</span><span class="sxs-lookup"><span data-stu-id="a6c2a-106">Exporting Custom Metadata for a WCF Extension</span></span>](../../../../docs/framework/wcf/extending/exporting-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="a6c2a-107">Содержит описание, как реализовать и использовать интерфейс <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> для внедрения в документы WSDL пользовательских утверждений политики.</span><span class="sxs-lookup"><span data-stu-id="a6c2a-107">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interface to embed custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="a6c2a-108">Импорт пользовательских метаданных для расширения WCF</span><span class="sxs-lookup"><span data-stu-id="a6c2a-108">Importing Custom Metadata for a WCF Extension</span></span>](../../../../docs/framework/wcf/extending/importing-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="a6c2a-109">Содержит описание, как реализовать и использовать интерфейс <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> для чтения пользовательских утверждений политики в документах WSDL и ответа на них.</span><span class="sxs-lookup"><span data-stu-id="a6c2a-109">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interface to read and respond to custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="a6c2a-110">Публикация и получение метаданных через настраиваемую привязку.</span><span class="sxs-lookup"><span data-stu-id="a6c2a-110">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 <span data-ttu-id="a6c2a-111">Содержит описание обмена данными для пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="a6c2a-111">Describes how to exchange metadata over custom bindings.</span></span>
