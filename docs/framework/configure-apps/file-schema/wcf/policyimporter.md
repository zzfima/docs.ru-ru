---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 81f38d2a163163ca7255ca546bbddbbb58fa3a1b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094181"
---
# <a name="policyimporter"></a><span data-ttu-id="c1199-101">\<policyImporter ></span><span class="sxs-lookup"><span data-stu-id="c1199-101">\<policyImporter></span></span>
<span data-ttu-id="c1199-102">Задает средство импорта политики, контролирующее импорт положений пользовательской политики о привязках.</span><span class="sxs-lookup"><span data-stu-id="c1199-102">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="c1199-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c1199-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="c1199-104">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="c1199-104">\<client></span></span>  
<span data-ttu-id="c1199-105">\<метаданные ></span><span class="sxs-lookup"><span data-stu-id="c1199-105">\<metadata></span></span>  
<span data-ttu-id="c1199-106">\<policyImporters ></span><span class="sxs-lookup"><span data-stu-id="c1199-106">\<policyImporters></span></span>  
<span data-ttu-id="c1199-107">\<policyImporter ></span><span class="sxs-lookup"><span data-stu-id="c1199-107">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1199-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c1199-108">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1199-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c1199-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c1199-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c1199-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1199-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c1199-111">Attributes</span></span>  
  
|<span data-ttu-id="c1199-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c1199-112">Attribute</span></span>|<span data-ttu-id="c1199-113">Описание</span><span class="sxs-lookup"><span data-stu-id="c1199-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="c1199-114">Тип этого элемента.</span><span class="sxs-lookup"><span data-stu-id="c1199-114">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c1199-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c1199-115">Child Elements</span></span>  
 <span data-ttu-id="c1199-116">Нет</span><span class="sxs-lookup"><span data-stu-id="c1199-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c1199-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c1199-117">Parent Elements</span></span>  
  
|<span data-ttu-id="c1199-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="c1199-118">Element</span></span>|<span data-ttu-id="c1199-119">Описание</span><span class="sxs-lookup"><span data-stu-id="c1199-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1199-120">\<policyImporters ></span><span class="sxs-lookup"><span data-stu-id="c1199-120">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="c1199-121">Задает все средства импорта политики, контролирующие импорт утверждений пользовательской политики о привязках.</span><span class="sxs-lookup"><span data-stu-id="c1199-121">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1199-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="c1199-122">Remarks</span></span>  
 <span data-ttu-id="c1199-123">Средство импорта политики используется для поиска утверждений пользовательской политики о свойствах привязки, а также для подключения пользовательского элемента привязки, реализующего свойства, необходимые для утверждения.</span><span class="sxs-lookup"><span data-stu-id="c1199-123">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1199-124">См. также</span><span class="sxs-lookup"><span data-stu-id="c1199-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="c1199-125">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="c1199-125">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="c1199-126">Клиенты</span><span class="sxs-lookup"><span data-stu-id="c1199-126">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
