---
title: <wsdlImporter>
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 13c9400874f1e02fac3ce0c3010153ad7806288c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915192"
---
# <a name="wsdlimporter"></a><span data-ttu-id="1e483-101">\<wsdlImporter ></span><span class="sxs-lookup"><span data-stu-id="1e483-101">\<wsdlImporter></span></span>
<span data-ttu-id="1e483-102">Задает все средства импорта WSDL, импортирующие метаданные на языке WSDL 1.1 с вложениями WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="1e483-102">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
<span data-ttu-id="1e483-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1e483-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="1e483-104">\<> клиента</span><span class="sxs-lookup"><span data-stu-id="1e483-104">\<client></span></span>  
<span data-ttu-id="1e483-105">\<> метаданных</span><span class="sxs-lookup"><span data-stu-id="1e483-105">\<metadata></span></span>  
<span data-ttu-id="1e483-106">\<Всдлимпортерс ></span><span class="sxs-lookup"><span data-stu-id="1e483-106">\<wsdlImporters></span></span>  
<span data-ttu-id="1e483-107">\<wsdlImporter ></span><span class="sxs-lookup"><span data-stu-id="1e483-107">\<wsdlImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e483-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e483-108">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e483-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1e483-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1e483-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1e483-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e483-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1e483-111">Attributes</span></span>  
  
|<span data-ttu-id="1e483-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1e483-112">Attribute</span></span>|<span data-ttu-id="1e483-113">Описание</span><span class="sxs-lookup"><span data-stu-id="1e483-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="1e483-114">Тип этого элемента.</span><span class="sxs-lookup"><span data-stu-id="1e483-114">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1e483-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1e483-115">Child Elements</span></span>  
 <span data-ttu-id="1e483-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="1e483-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1e483-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1e483-117">Parent Elements</span></span>  
  
|<span data-ttu-id="1e483-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="1e483-118">Element</span></span>|<span data-ttu-id="1e483-119">Описание</span><span class="sxs-lookup"><span data-stu-id="1e483-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e483-120">\<Всдлимпортерс ></span><span class="sxs-lookup"><span data-stu-id="1e483-120">\<wsdlImporters></span></span>](wsdlimporters.md)|<span data-ttu-id="1e483-121">Задает все средства импорта WSDL, импортирующие метаданные на языке WSDL 1.1 с вложениями WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="1e483-121">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e483-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="1e483-122">Remarks</span></span>  
 <span data-ttu-id="1e483-123">Средство импорта WSDL используется для импорта метаданных, а также для их преобразования в различные классы, представляющие данные контракта и конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1e483-123">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="1e483-124">Он может выборочно импортировать сведения контракта и конечной точки, а также свойства, предоставляющие сведения об ошибках и принимающие сведения о типах, относящиеся к процессу импорта и преобразования.</span><span class="sxs-lookup"><span data-stu-id="1e483-124">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="1e483-125">Оно также поддерживает импорт данных привязки и свойств, предоставляющих доступ к каким-либо документам политики, документам WSDL, расширениям WSDL и документам схемы XML.</span><span class="sxs-lookup"><span data-stu-id="1e483-125">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e483-126">См. также</span><span class="sxs-lookup"><span data-stu-id="1e483-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="1e483-127">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="1e483-127">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="1e483-128">Клиенты</span><span class="sxs-lookup"><span data-stu-id="1e483-128">Clients</span></span>](../../../wcf/feature-details/clients.md)
