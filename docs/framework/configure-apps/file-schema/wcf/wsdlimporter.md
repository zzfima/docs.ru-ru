---
title: <wsdlImporter>
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 1f34486296465b3ea0b5b05bd9492062c85ad8c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670252"
---
# <a name="wsdlimporter"></a><span data-ttu-id="3652e-101">\<wsdlImporter ></span><span class="sxs-lookup"><span data-stu-id="3652e-101">\<wsdlImporter></span></span>
<span data-ttu-id="3652e-102">Задает все средства импорта WSDL, импортирующие метаданные на языке WSDL 1.1 с вложениями WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="3652e-102">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
<span data-ttu-id="3652e-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3652e-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="3652e-104">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="3652e-104">\<client></span></span>  
<span data-ttu-id="3652e-105">\<метаданные ></span><span class="sxs-lookup"><span data-stu-id="3652e-105">\<metadata></span></span>  
<span data-ttu-id="3652e-106">\<wsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="3652e-106">\<wsdlImporters></span></span>  
<span data-ttu-id="3652e-107">\<wsdlImporter ></span><span class="sxs-lookup"><span data-stu-id="3652e-107">\<wsdlImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3652e-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3652e-108">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3652e-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3652e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3652e-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3652e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3652e-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3652e-111">Attributes</span></span>  
  
|<span data-ttu-id="3652e-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3652e-112">Attribute</span></span>|<span data-ttu-id="3652e-113">Описание</span><span class="sxs-lookup"><span data-stu-id="3652e-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="3652e-114">Тип этого элемента.</span><span class="sxs-lookup"><span data-stu-id="3652e-114">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3652e-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3652e-115">Child Elements</span></span>  
 <span data-ttu-id="3652e-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3652e-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3652e-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3652e-117">Parent Elements</span></span>  
  
|<span data-ttu-id="3652e-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="3652e-118">Element</span></span>|<span data-ttu-id="3652e-119">Описание</span><span class="sxs-lookup"><span data-stu-id="3652e-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3652e-120">\<wsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="3652e-120">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="3652e-121">Задает все средства импорта WSDL, импортирующие метаданные на языке WSDL 1.1 с вложениями WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="3652e-121">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3652e-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="3652e-122">Remarks</span></span>  
 <span data-ttu-id="3652e-123">Средство импорта WSDL используется для импорта метаданных, а также для их преобразования в различные классы, представляющие данные контракта и конечной точки.</span><span class="sxs-lookup"><span data-stu-id="3652e-123">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="3652e-124">Он может выборочно импортировать сведения контракта и конечной точки, а также свойства, предоставляющие сведения об ошибках и принимающие сведения о типах, относящиеся к процессу импорта и преобразования.</span><span class="sxs-lookup"><span data-stu-id="3652e-124">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="3652e-125">Оно также поддерживает импорт данных привязки и свойств, предоставляющих доступ к каким-либо документам политики, документам WSDL, расширениям WSDL и документам схемы XML.</span><span class="sxs-lookup"><span data-stu-id="3652e-125">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3652e-126">См. также</span><span class="sxs-lookup"><span data-stu-id="3652e-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="3652e-127">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="3652e-127">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="3652e-128">Клиенты</span><span class="sxs-lookup"><span data-stu-id="3652e-128">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
