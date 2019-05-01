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
# <a name="extending-the-metadata-system"></a><span data-ttu-id="628ec-102">Расширение системы метаданных</span><span class="sxs-lookup"><span data-stu-id="628ec-102">Extending the Metadata System</span></span>
<span data-ttu-id="628ec-103">Система метаданных Windows Communication Foundation (WCF) — это набор классов и интерфейсов, представляющих метаданные, необходимые для реализации приложений на основе службы.</span><span class="sxs-lookup"><span data-stu-id="628ec-103">The Windows Communication Foundation (WCF) metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="628ec-104">Можно изменять или расширять классы, реализовывать и настраивать интерфейсы для экспорта и импорта пользовательских метаданных, например расширений языка WSDL или пользовательских утверждений WS-PolicyAttachments.</span><span class="sxs-lookup"><span data-stu-id="628ec-104">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="628ec-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="628ec-105">In This Section</span></span>  
 [<span data-ttu-id="628ec-106">Экспорт пользовательских метаданных для расширения WCF</span><span class="sxs-lookup"><span data-stu-id="628ec-106">Exporting Custom Metadata for a WCF Extension</span></span>](../../../../docs/framework/wcf/extending/exporting-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="628ec-107">Содержит описание, как реализовать и использовать интерфейс <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> для внедрения в документы WSDL пользовательских утверждений политики.</span><span class="sxs-lookup"><span data-stu-id="628ec-107">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interface to embed custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="628ec-108">Импорт пользовательских метаданных для расширения WCF</span><span class="sxs-lookup"><span data-stu-id="628ec-108">Importing Custom Metadata for a WCF Extension</span></span>](../../../../docs/framework/wcf/extending/importing-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="628ec-109">Содержит описание, как реализовать и использовать интерфейс <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> для чтения пользовательских утверждений политики в документах WSDL и ответа на них.</span><span class="sxs-lookup"><span data-stu-id="628ec-109">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interface to read and respond to custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="628ec-110">Публикация и получение метаданных через пользовательскую привязку</span><span class="sxs-lookup"><span data-stu-id="628ec-110">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 <span data-ttu-id="628ec-111">Содержит описание обмена данными для пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="628ec-111">Describes how to exchange metadata over custom bindings.</span></span>
