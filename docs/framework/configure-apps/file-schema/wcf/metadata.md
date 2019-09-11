---
title: <metadata>
ms.date: 03/30/2017
ms.assetid: d09653eb-e355-4c73-b87b-28f93d56480d
ms.openlocfilehash: 028e4d3fbe7bce06caa7497c8f95f3b293a4b068
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855223"
---
# <a name="metadata"></a><span data-ttu-id="70463-101">\<> метаданных</span><span class="sxs-lookup"><span data-stu-id="70463-101">\<metadata></span></span>
<span data-ttu-id="70463-102">Задает способ обработки метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="70463-102">Specifies how service metadata can be processed.</span></span>  
  
<span data-ttu-id="70463-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="70463-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="70463-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="70463-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="70463-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> клиента**](client.md)</span><span class="sxs-lookup"><span data-stu-id="70463-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="70463-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> метаданных**</span><span class="sxs-lookup"><span data-stu-id="70463-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<metadata>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70463-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="70463-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <client>
    <metadata>
      <policyImporters>
        <policyImporter type="string" />
      </policyImporters>
      <wsdlImporters>
        <wsdlImporter type="string" />
      </wsdlImporters>
    </metadata>
  </client>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70463-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="70463-108">Attributes and Elements</span></span>  
 <span data-ttu-id="70463-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="70463-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70463-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="70463-110">Attributes</span></span>  
 <span data-ttu-id="70463-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="70463-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="70463-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="70463-112">Child Elements</span></span>  
  
|<span data-ttu-id="70463-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="70463-113">Element</span></span>|<span data-ttu-id="70463-114">Описание</span><span class="sxs-lookup"><span data-stu-id="70463-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="70463-115">\<Полициимпортерс ></span><span class="sxs-lookup"><span data-stu-id="70463-115">\<policyImporters></span></span>](policyimporters.md)|<span data-ttu-id="70463-116">Задает все средства импорта политики, контролирующие импорт утверждений пользовательской политики о привязках.</span><span class="sxs-lookup"><span data-stu-id="70463-116">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span> <span data-ttu-id="70463-117">Средство импорта политики используется для поиска утверждений пользовательской политики о свойствах привязки, а также для подключения пользовательского элемента привязки, реализующего свойства, необходимые для утверждения.</span><span class="sxs-lookup"><span data-stu-id="70463-117">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>|  
|[<span data-ttu-id="70463-118">\<Всдлимпортерс ></span><span class="sxs-lookup"><span data-stu-id="70463-118">\<wsdlImporters></span></span>](wsdlimporters.md)|<span data-ttu-id="70463-119">Задает все средства импорта WSDL, импортирующие метаданные на языке WSDL 1.1 с вложениями WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="70463-119">Specifies all the WSDL importers that import Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="70463-120">Средство импорта WSDL используется для импорта метаданных, а также для их преобразования в различные классы, представляющие данные контракта и конечной точки.</span><span class="sxs-lookup"><span data-stu-id="70463-120">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="70463-121">Он может выборочно импортировать сведения контракта и конечной точки, а также свойства, предоставляющие сведения об ошибках и принимающие сведения о типах, относящиеся к процессу импорта и преобразования.</span><span class="sxs-lookup"><span data-stu-id="70463-121">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="70463-122">Оно также поддерживает импорт данных привязки и свойств, предоставляющих доступ к каким-либо документам политики, документам WSDL, расширениям WSDL и документам схемы XML.</span><span class="sxs-lookup"><span data-stu-id="70463-122">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="70463-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="70463-123">Parent Elements</span></span>  
  
|<span data-ttu-id="70463-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="70463-124">Element</span></span>|<span data-ttu-id="70463-125">Описание</span><span class="sxs-lookup"><span data-stu-id="70463-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="70463-126">\<> клиента</span><span class="sxs-lookup"><span data-stu-id="70463-126">\<client></span></span>](client.md)|<span data-ttu-id="70463-127">В разделе client определяется список конечных точек, к которым может подключаться клиент.</span><span class="sxs-lookup"><span data-stu-id="70463-127">The client section defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="70463-128">См. также</span><span class="sxs-lookup"><span data-stu-id="70463-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="70463-129">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="70463-129">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="70463-130">Клиенты</span><span class="sxs-lookup"><span data-stu-id="70463-130">Clients</span></span>](../../../wcf/feature-details/clients.md)
