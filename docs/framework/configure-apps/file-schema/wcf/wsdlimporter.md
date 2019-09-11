---
title: <wsdlImporter>
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 317921a66fa3b8d1f0026d676ea674b67732b3df
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854754"
---
# <a name="wsdlimporter"></a><span data-ttu-id="6c161-101">\<wsdlImporter ></span><span class="sxs-lookup"><span data-stu-id="6c161-101">\<wsdlImporter></span></span>
<span data-ttu-id="6c161-102">Задает все средства импорта WSDL, импортирующие метаданные на языке WSDL 1.1 с вложениями WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="6c161-102">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
<span data-ttu-id="6c161-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6c161-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6c161-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="6c161-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6c161-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> клиента**](client.md)</span><span class="sxs-lookup"><span data-stu-id="6c161-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="6c161-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> метаданных**](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="6c161-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)</span></span>\
<span data-ttu-id="6c161-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Всдлимпортерс >** ](wsdlimporters.md)</span><span class="sxs-lookup"><span data-stu-id="6c161-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsdlImporters>**](wsdlimporters.md)</span></span>  
<span data-ttu-id="6c161-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<wsdlImporter >**</span><span class="sxs-lookup"><span data-stu-id="6c161-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsdlImporter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c161-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c161-109">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c161-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6c161-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6c161-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6c161-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c161-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6c161-112">Attributes</span></span>  
  
|<span data-ttu-id="6c161-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6c161-113">Attribute</span></span>|<span data-ttu-id="6c161-114">Описание</span><span class="sxs-lookup"><span data-stu-id="6c161-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="6c161-115">Тип этого элемента.</span><span class="sxs-lookup"><span data-stu-id="6c161-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6c161-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6c161-116">Child Elements</span></span>  
 <span data-ttu-id="6c161-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="6c161-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6c161-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6c161-118">Parent Elements</span></span>  
  
|<span data-ttu-id="6c161-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="6c161-119">Element</span></span>|<span data-ttu-id="6c161-120">Описание</span><span class="sxs-lookup"><span data-stu-id="6c161-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c161-121">\<Всдлимпортерс ></span><span class="sxs-lookup"><span data-stu-id="6c161-121">\<wsdlImporters></span></span>](wsdlimporters.md)|<span data-ttu-id="6c161-122">Задает все средства импорта WSDL, импортирующие метаданные на языке WSDL 1.1 с вложениями WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="6c161-122">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c161-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="6c161-123">Remarks</span></span>  
 <span data-ttu-id="6c161-124">Средство импорта WSDL используется для импорта метаданных, а также для их преобразования в различные классы, представляющие данные контракта и конечной точки.</span><span class="sxs-lookup"><span data-stu-id="6c161-124">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="6c161-125">Он может выборочно импортировать сведения контракта и конечной точки, а также свойства, предоставляющие сведения об ошибках и принимающие сведения о типах, относящиеся к процессу импорта и преобразования.</span><span class="sxs-lookup"><span data-stu-id="6c161-125">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="6c161-126">Оно также поддерживает импорт данных привязки и свойств, предоставляющих доступ к каким-либо документам политики, документам WSDL, расширениям WSDL и документам схемы XML.</span><span class="sxs-lookup"><span data-stu-id="6c161-126">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c161-127">См. также</span><span class="sxs-lookup"><span data-stu-id="6c161-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="6c161-128">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="6c161-128">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="6c161-129">Клиенты</span><span class="sxs-lookup"><span data-stu-id="6c161-129">Clients</span></span>](../../../wcf/feature-details/clients.md)
