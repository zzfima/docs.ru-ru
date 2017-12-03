---
title: "&lt;метаданные&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d09653eb-e355-4c73-b87b-28f93d56480d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 06444f30ab06f04644a7a6c5ad596388ecceeaf1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltmetadatagt"></a><span data-ttu-id="6d564-102">&lt;метаданные&gt;</span><span class="sxs-lookup"><span data-stu-id="6d564-102">&lt;metadata&gt;</span></span>
<span data-ttu-id="6d564-103">Задает способ обработки метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="6d564-103">Specifies how service metadata can be processed.</span></span>  
  
 <span data-ttu-id="6d564-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="6d564-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6d564-105">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="6d564-105">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d564-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d564-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
    <client>  
        <metadata>  
                   <policyImporters>  
                          <policyImporter type="string" />  
                   </policyImporters  
                 <wsdlImporters>  
                      <wsdlImporter type="string" />  
                 </wsdlImporters>  
        </metadata>  
    </client>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6d564-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6d564-107">Attributes and Elements</span></span>  
 <span data-ttu-id="6d564-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6d564-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6d564-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6d564-109">Attributes</span></span>  
 <span data-ttu-id="6d564-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6d564-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6d564-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6d564-111">Child Elements</span></span>  
  
|<span data-ttu-id="6d564-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="6d564-112">Element</span></span>|<span data-ttu-id="6d564-113">Описание</span><span class="sxs-lookup"><span data-stu-id="6d564-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6d564-114">\<policyImporters ></span><span class="sxs-lookup"><span data-stu-id="6d564-114">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="6d564-115">Задает все средства импорта политики, контролирующие импорт утверждений пользовательской политики о привязках.</span><span class="sxs-lookup"><span data-stu-id="6d564-115">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span> <span data-ttu-id="6d564-116">Средство импорта политики используется для поиска утверждений пользовательской политики о свойствах привязки, а также для подключения пользовательского элемента привязки, реализующего свойства, необходимые для утверждения.</span><span class="sxs-lookup"><span data-stu-id="6d564-116">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>|  
|[<span data-ttu-id="6d564-117">\<wsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="6d564-117">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="6d564-118">Задает все средства импорта WSDL, импортирующие метаданные на языке WSDL 1.1 с вложениями WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="6d564-118">Specifies all the WSDL importers that import Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="6d564-119">Средство импорта WSDL используется для импорта метаданных, а также для их преобразования в различные классы, представляющие данные контракта и конечной точки.</span><span class="sxs-lookup"><span data-stu-id="6d564-119">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="6d564-120">Он может выборочно импортировать сведения контракта и конечной точки, а также свойства, предоставляющие сведения об ошибках и принимающие сведения о типах, относящиеся к процессу импорта и преобразования.</span><span class="sxs-lookup"><span data-stu-id="6d564-120">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="6d564-121">Оно также поддерживает импорт данных привязки и свойств, предоставляющих доступ к каким-либо документам политики, документам WSDL, расширениям WSDL и документам схемы XML.</span><span class="sxs-lookup"><span data-stu-id="6d564-121">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6d564-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6d564-122">Parent Elements</span></span>  
  
|<span data-ttu-id="6d564-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="6d564-123">Element</span></span>|<span data-ttu-id="6d564-124">Описание</span><span class="sxs-lookup"><span data-stu-id="6d564-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6d564-125">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="6d564-125">\<client></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|<span data-ttu-id="6d564-126">В разделе client определяется список конечных точек, к которым может подключаться клиент.</span><span class="sxs-lookup"><span data-stu-id="6d564-126">The client section defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6d564-127">См. также</span><span class="sxs-lookup"><span data-stu-id="6d564-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 <xref:System.ServiceModel.Description.WsdlImporter>  
 [<span data-ttu-id="6d564-128">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="6d564-128">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="6d564-129">Клиенты</span><span class="sxs-lookup"><span data-stu-id="6d564-129">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
