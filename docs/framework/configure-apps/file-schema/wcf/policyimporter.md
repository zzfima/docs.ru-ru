---
title: "&lt;Импортер политики policyImporter&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2226b4f55025c9dec3fdeb4f9b4f51016ffd3e8e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltpolicyimportergt"></a><span data-ttu-id="bad7b-102">&lt;Импортер политики policyImporter&gt;</span><span class="sxs-lookup"><span data-stu-id="bad7b-102">&lt;policyImporter&gt;</span></span>
<span data-ttu-id="bad7b-103">Задает средство импорта политики, контролирующее импорт положений пользовательской политики о привязках.</span><span class="sxs-lookup"><span data-stu-id="bad7b-103">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="bad7b-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="bad7b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bad7b-105">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="bad7b-105">\<client></span></span>  
<span data-ttu-id="bad7b-106">\<метаданные ></span><span class="sxs-lookup"><span data-stu-id="bad7b-106">\<metadata></span></span>  
<span data-ttu-id="bad7b-107">\<policyImporters ></span><span class="sxs-lookup"><span data-stu-id="bad7b-107">\<policyImporters></span></span>  
<span data-ttu-id="bad7b-108">\<Импортер политики policyImporter ></span><span class="sxs-lookup"><span data-stu-id="bad7b-108">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bad7b-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bad7b-109">Syntax</span></span>  
  
```xml  
<metadata>  
   <policyImporters>  
      <policyImporter type="string" />  
   </policyImporters>  
</metadata>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bad7b-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bad7b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bad7b-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bad7b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bad7b-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bad7b-112">Attributes</span></span>  
  
|<span data-ttu-id="bad7b-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bad7b-113">Attribute</span></span>|<span data-ttu-id="bad7b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="bad7b-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="bad7b-115">Тип этого элемента.</span><span class="sxs-lookup"><span data-stu-id="bad7b-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bad7b-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bad7b-116">Child Elements</span></span>  
 <span data-ttu-id="bad7b-117">Нет</span><span class="sxs-lookup"><span data-stu-id="bad7b-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bad7b-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bad7b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="bad7b-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="bad7b-119">Element</span></span>|<span data-ttu-id="bad7b-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="bad7b-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bad7b-121">\<policyImporters ></span><span class="sxs-lookup"><span data-stu-id="bad7b-121">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="bad7b-122">Задает все средства импорта политики, контролирующие импорт утверждений пользовательской политики о привязках.</span><span class="sxs-lookup"><span data-stu-id="bad7b-122">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bad7b-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="bad7b-123">Remarks</span></span>  
 <span data-ttu-id="bad7b-124">Средство импорта политики используется для поиска утверждений пользовательской политики о свойствах привязки, а также для подключения пользовательского элемента привязки, реализующего свойства, необходимые для утверждения.</span><span class="sxs-lookup"><span data-stu-id="bad7b-124">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bad7b-125">См. также</span><span class="sxs-lookup"><span data-stu-id="bad7b-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElement>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 [<span data-ttu-id="bad7b-126">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="bad7b-126">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="bad7b-127">Клиенты</span><span class="sxs-lookup"><span data-stu-id="bad7b-127">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
