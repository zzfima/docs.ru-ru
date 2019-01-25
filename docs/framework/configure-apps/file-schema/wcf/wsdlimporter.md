---
title: '&lt;wsdlImporter&gt;'
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 5f3d53111c4d303146701b03d7e7b32833cd9edd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54651049"
---
# <a name="ltwsdlimportergt"></a><span data-ttu-id="43126-102">&lt;wsdlImporter&gt;</span><span class="sxs-lookup"><span data-stu-id="43126-102">&lt;wsdlImporter&gt;</span></span>
<span data-ttu-id="43126-103">Задает все средства импорта WSDL, импортирующие метаданные на языке WSDL 1.1 с вложениями WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="43126-103">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
<span data-ttu-id="43126-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="43126-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="43126-105">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="43126-105">\<client></span></span>  
<span data-ttu-id="43126-106">\<метаданные ></span><span class="sxs-lookup"><span data-stu-id="43126-106">\<metadata></span></span>  
<span data-ttu-id="43126-107">\<wsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="43126-107">\<wsdlImporters></span></span>  
<span data-ttu-id="43126-108">\<wsdlImporter ></span><span class="sxs-lookup"><span data-stu-id="43126-108">\<wsdlImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43126-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="43126-109">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43126-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="43126-110">Attributes and Elements</span></span>  
 <span data-ttu-id="43126-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="43126-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43126-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="43126-112">Attributes</span></span>  
  
|<span data-ttu-id="43126-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="43126-113">Attribute</span></span>|<span data-ttu-id="43126-114">Описание</span><span class="sxs-lookup"><span data-stu-id="43126-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="43126-115">Тип этого элемента.</span><span class="sxs-lookup"><span data-stu-id="43126-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="43126-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="43126-116">Child Elements</span></span>  
 <span data-ttu-id="43126-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="43126-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="43126-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="43126-118">Parent Elements</span></span>  
  
|<span data-ttu-id="43126-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="43126-119">Element</span></span>|<span data-ttu-id="43126-120">Описание</span><span class="sxs-lookup"><span data-stu-id="43126-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43126-121">\<wsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="43126-121">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="43126-122">Задает все средства импорта WSDL, импортирующие метаданные на языке WSDL 1.1 с вложениями WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="43126-122">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43126-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="43126-123">Remarks</span></span>  
 <span data-ttu-id="43126-124">Средство импорта WSDL используется для импорта метаданных, а также для их преобразования в различные классы, представляющие данные контракта и конечной точки.</span><span class="sxs-lookup"><span data-stu-id="43126-124">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="43126-125">Он может выборочно импортировать сведения контракта и конечной точки, а также свойства, предоставляющие сведения об ошибках и принимающие сведения о типах, относящиеся к процессу импорта и преобразования.</span><span class="sxs-lookup"><span data-stu-id="43126-125">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="43126-126">Оно также поддерживает импорт данных привязки и свойств, предоставляющих доступ к каким-либо документам политики, документам WSDL, расширениям WSDL и документам схемы XML.</span><span class="sxs-lookup"><span data-stu-id="43126-126">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43126-127">См. также</span><span class="sxs-lookup"><span data-stu-id="43126-127">See also</span></span>
- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="43126-128">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="43126-128">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="43126-129">Клиенты</span><span class="sxs-lookup"><span data-stu-id="43126-129">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
