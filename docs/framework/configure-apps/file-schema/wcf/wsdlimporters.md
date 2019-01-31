---
title: <wsdlImporters>
ms.date: 03/30/2017
ms.assetid: 270c7f93-eab7-47b6-8b94-ac3f5b7f17e4
ms.openlocfilehash: 81fb25f6a77456608fd3cb0d5e73f67c7f7867c3
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55274577"
---
# <a name="wsdlimporters"></a><span data-ttu-id="e644a-101">\<wsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="e644a-101">\<wsdlImporters></span></span>
<span data-ttu-id="e644a-102">Этот элемент конфигурации указывает всех импортеров WSDL, импортирующих метаданные на языке WSDL 1.1 с вложениями WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="e644a-102">This configuration element specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="e644a-103">Каждый дочерний элемент — это элемент <`wsdlImporter`>, который указывает способ импорта метаданных, а также способ преобразования сведений в различные классы, представляющие сведения контракта и конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e644a-103">Each child element is a <`wsdlImporter`> that specifies the way to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="e644a-104">Он может выборочно импортировать сведения контракта и конечной точки, а также свойства, предоставляющие сведения об ошибках и принимающие сведения о типах, относящиеся к процессу импорта и преобразования.</span><span class="sxs-lookup"><span data-stu-id="e644a-104">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="e644a-105">Оно также поддерживает импорт данных привязки и свойств, предоставляющих доступ к каким-либо документам политики, документам WSDL, расширениям WSDL и документам схемы XML.</span><span class="sxs-lookup"><span data-stu-id="e644a-105">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e644a-106">См. также</span><span class="sxs-lookup"><span data-stu-id="e644a-106">See also</span></span>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="e644a-107">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="e644a-107">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="e644a-108">Клиенты</span><span class="sxs-lookup"><span data-stu-id="e644a-108">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
