---
title: '&lt;wsdlImporter&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc85c93dc73918d661195e33ce5094622db36af4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltwsdlimportergt"></a><span data-ttu-id="62801-102">&lt;wsdlImporter&gt;</span><span class="sxs-lookup"><span data-stu-id="62801-102">&lt;wsdlImporter&gt;</span></span>
<span data-ttu-id="62801-103">Задает все средства импорта WSDL, импортирующие метаданные на языке WSDL 1.1 с вложениями WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="62801-103">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
<span data-ttu-id="62801-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="62801-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="62801-105">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="62801-105">\<client></span></span>  
<span data-ttu-id="62801-106">\<метаданные ></span><span class="sxs-lookup"><span data-stu-id="62801-106">\<metadata></span></span>  
<span data-ttu-id="62801-107">\<wsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="62801-107">\<wsdlImporters></span></span>  
<span data-ttu-id="62801-108">\<wsdlImporter ></span><span class="sxs-lookup"><span data-stu-id="62801-108">\<wsdlImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62801-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62801-109">Syntax</span></span>  
  
```xml  
<metadata>  
  <wsdlImporters>  
    <wsdlImporter type="string" />  
  </wsdlImporters>  
</metadata>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62801-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="62801-110">Attributes and Elements</span></span>  
 <span data-ttu-id="62801-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="62801-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62801-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="62801-112">Attributes</span></span>  
  
|<span data-ttu-id="62801-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="62801-113">Attribute</span></span>|<span data-ttu-id="62801-114">Описание</span><span class="sxs-lookup"><span data-stu-id="62801-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="62801-115">Тип этого элемента.</span><span class="sxs-lookup"><span data-stu-id="62801-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="62801-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="62801-116">Child Elements</span></span>  
 <span data-ttu-id="62801-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="62801-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="62801-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="62801-118">Parent Elements</span></span>  
  
|<span data-ttu-id="62801-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="62801-119">Element</span></span>|<span data-ttu-id="62801-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="62801-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62801-121">\<wsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="62801-121">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="62801-122">Задает все средства импорта WSDL, импортирующие метаданные на языке WSDL 1.1 с вложениями WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="62801-122">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62801-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="62801-123">Remarks</span></span>  
 <span data-ttu-id="62801-124">Средство импорта WSDL используется для импорта метаданных, а также для их преобразования в различные классы, представляющие данные контракта и конечной точки.</span><span class="sxs-lookup"><span data-stu-id="62801-124">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="62801-125">Он может выборочно импортировать сведения контракта и конечной точки, а также свойства, предоставляющие сведения об ошибках и принимающие сведения о типах, относящиеся к процессу импорта и преобразования.</span><span class="sxs-lookup"><span data-stu-id="62801-125">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="62801-126">Оно также поддерживает импорт данных привязки и свойств, предоставляющих доступ к каким-либо документам политики, документам WSDL, расширениям WSDL и документам схемы XML.</span><span class="sxs-lookup"><span data-stu-id="62801-126">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62801-127">См. также</span><span class="sxs-lookup"><span data-stu-id="62801-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElement>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 <xref:System.ServiceModel.Description.WsdlImporter>  
 [<span data-ttu-id="62801-128">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="62801-128">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="62801-129">Клиенты</span><span class="sxs-lookup"><span data-stu-id="62801-129">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
