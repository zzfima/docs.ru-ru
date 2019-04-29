---
title: <wsdlImporters>
ms.date: 03/30/2017
ms.assetid: 270c7f93-eab7-47b6-8b94-ac3f5b7f17e4
ms.openlocfilehash: 75f88219ab73d321b3e04c140bbfe964aed0b83a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785480"
---
# <a name="wsdlimporters"></a><span data-ttu-id="e47b5-101">\<wsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="e47b5-101">\<wsdlImporters></span></span>
<span data-ttu-id="e47b5-102">Этот элемент конфигурации указывает всех импортеров WSDL, импортирующих метаданные на языке WSDL 1.1 с вложениями WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="e47b5-102">This configuration element specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="e47b5-103">Каждый дочерний элемент является <`wsdlImporter`>, указывающий способ импорта метаданных, а также для преобразования в различные классы, представляющие сведения контракта и конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e47b5-103">Each child element is a <`wsdlImporter`> that specifies the way to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="e47b5-104">Он может выборочно импортировать сведения контракта и конечной точки, а также свойства, предоставляющие сведения об ошибках и принимающие сведения о типах, относящиеся к процессу импорта и преобразования.</span><span class="sxs-lookup"><span data-stu-id="e47b5-104">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="e47b5-105">Оно также поддерживает импорт данных привязки и свойств, предоставляющих доступ к каким-либо документам политики, документам WSDL, расширениям WSDL и документам схемы XML.</span><span class="sxs-lookup"><span data-stu-id="e47b5-105">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e47b5-106">См. также</span><span class="sxs-lookup"><span data-stu-id="e47b5-106">See also</span></span>

- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="e47b5-107">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="e47b5-107">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="e47b5-108">Клиенты</span><span class="sxs-lookup"><span data-stu-id="e47b5-108">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
