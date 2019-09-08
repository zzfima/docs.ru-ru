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
# <a name="extending-the-metadata-system"></a><span data-ttu-id="2f972-102">Расширение системы метаданных</span><span class="sxs-lookup"><span data-stu-id="2f972-102">Extending the Metadata System</span></span>
<span data-ttu-id="2f972-103">Система метаданных Windows Communication Foundation (WCF) — это группа классов и интерфейсов, представляющих метаданные, необходимые для реализации приложений на основе служб.</span><span class="sxs-lookup"><span data-stu-id="2f972-103">The Windows Communication Foundation (WCF) metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="2f972-104">Можно изменять или расширять классы, реализовывать и настраивать интерфейсы для экспорта и импорта пользовательских метаданных, например расширений языка WSDL или пользовательских утверждений WS-PolicyAttachments.</span><span class="sxs-lookup"><span data-stu-id="2f972-104">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2f972-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="2f972-105">In This Section</span></span>  
 [<span data-ttu-id="2f972-106">Экспорт пользовательских метаданных для расширения WCF</span><span class="sxs-lookup"><span data-stu-id="2f972-106">Exporting Custom Metadata for a WCF Extension</span></span>](exporting-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="2f972-107">Содержит описание, как реализовать и использовать интерфейс <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> для внедрения в документы WSDL пользовательских утверждений политики.</span><span class="sxs-lookup"><span data-stu-id="2f972-107">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interface to embed custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="2f972-108">Импорт пользовательских метаданных для расширения WCF</span><span class="sxs-lookup"><span data-stu-id="2f972-108">Importing Custom Metadata for a WCF Extension</span></span>](importing-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="2f972-109">Содержит описание, как реализовать и использовать интерфейс <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> для чтения пользовательских утверждений политики в документах WSDL и ответа на них.</span><span class="sxs-lookup"><span data-stu-id="2f972-109">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interface to read and respond to custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="2f972-110">Публикация и получение метаданных через пользовательскую привязку</span><span class="sxs-lookup"><span data-stu-id="2f972-110">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 <span data-ttu-id="2f972-111">Содержит описание обмена данными для пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="2f972-111">Describes how to exchange metadata over custom bindings.</span></span>
