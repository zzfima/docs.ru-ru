---
title: '&lt;wsdlImporters&gt;'
ms.date: 03/30/2017
ms.assetid: 270c7f93-eab7-47b6-8b94-ac3f5b7f17e4
ms.openlocfilehash: aa07bb2af0c448c08908902f1243d152d16daded
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54705922"
---
# <a name="ltwsdlimportersgt"></a><span data-ttu-id="4ee4a-102">&lt;wsdlImporters&gt;</span><span class="sxs-lookup"><span data-stu-id="4ee4a-102">&lt;wsdlImporters&gt;</span></span>
<span data-ttu-id="4ee4a-103">Этот элемент конфигурации указывает всех импортеров WSDL, импортирующих метаданные на языке WSDL 1.1 с вложениями WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="4ee4a-103">This configuration element specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="4ee4a-104">Каждый дочерний элемент — это элемент <`wsdlImporter`>, который указывает способ импорта метаданных, а также способ преобразования сведений в различные классы, представляющие сведения контракта и конечной точки.</span><span class="sxs-lookup"><span data-stu-id="4ee4a-104">Each child element is a <`wsdlImporter`> that specifies the way to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="4ee4a-105">Он может выборочно импортировать сведения контракта и конечной точки, а также свойства, предоставляющие сведения об ошибках и принимающие сведения о типах, относящиеся к процессу импорта и преобразования.</span><span class="sxs-lookup"><span data-stu-id="4ee4a-105">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="4ee4a-106">Оно также поддерживает импорт данных привязки и свойств, предоставляющих доступ к каким-либо документам политики, документам WSDL, расширениям WSDL и документам схемы XML.</span><span class="sxs-lookup"><span data-stu-id="4ee4a-106">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ee4a-107">См. также</span><span class="sxs-lookup"><span data-stu-id="4ee4a-107">See also</span></span>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="4ee4a-108">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="4ee4a-108">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="4ee4a-109">Клиенты</span><span class="sxs-lookup"><span data-stu-id="4ee4a-109">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
