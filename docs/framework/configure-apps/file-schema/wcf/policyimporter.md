---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 273bd0d5e68a661c639b82264b440b83d8127427
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933795"
---
# <a name="policyimporter"></a><span data-ttu-id="aa058-101">\<Полициимпортер ></span><span class="sxs-lookup"><span data-stu-id="aa058-101">\<policyImporter></span></span>
<span data-ttu-id="aa058-102">Задает средство импорта политики, контролирующее импорт положений пользовательской политики о привязках.</span><span class="sxs-lookup"><span data-stu-id="aa058-102">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="aa058-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="aa058-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="aa058-104">\<> клиента</span><span class="sxs-lookup"><span data-stu-id="aa058-104">\<client></span></span>  
<span data-ttu-id="aa058-105">\<> метаданных</span><span class="sxs-lookup"><span data-stu-id="aa058-105">\<metadata></span></span>  
<span data-ttu-id="aa058-106">\<Полициимпортерс ></span><span class="sxs-lookup"><span data-stu-id="aa058-106">\<policyImporters></span></span>  
<span data-ttu-id="aa058-107">\<Полициимпортер ></span><span class="sxs-lookup"><span data-stu-id="aa058-107">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa058-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa058-108">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa058-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="aa058-109">Attributes and Elements</span></span>  
 <span data-ttu-id="aa058-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="aa058-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa058-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aa058-111">Attributes</span></span>  
  
|<span data-ttu-id="aa058-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="aa058-112">Attribute</span></span>|<span data-ttu-id="aa058-113">Описание</span><span class="sxs-lookup"><span data-stu-id="aa058-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="aa058-114">Тип этого элемента.</span><span class="sxs-lookup"><span data-stu-id="aa058-114">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aa058-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="aa058-115">Child Elements</span></span>  
 <span data-ttu-id="aa058-116">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="aa058-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aa058-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="aa058-117">Parent Elements</span></span>  
  
|<span data-ttu-id="aa058-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="aa058-118">Element</span></span>|<span data-ttu-id="aa058-119">Описание</span><span class="sxs-lookup"><span data-stu-id="aa058-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa058-120">\<Полициимпортерс ></span><span class="sxs-lookup"><span data-stu-id="aa058-120">\<policyImporters></span></span>](policyimporters.md)|<span data-ttu-id="aa058-121">Задает все средства импорта политики, контролирующие импорт утверждений пользовательской политики о привязках.</span><span class="sxs-lookup"><span data-stu-id="aa058-121">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa058-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="aa058-122">Remarks</span></span>  
 <span data-ttu-id="aa058-123">Средство импорта политики используется для поиска утверждений пользовательской политики о свойствах привязки, а также для подключения пользовательского элемента привязки, реализующего свойства, необходимые для утверждения.</span><span class="sxs-lookup"><span data-stu-id="aa058-123">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa058-124">См. также</span><span class="sxs-lookup"><span data-stu-id="aa058-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="aa058-125">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="aa058-125">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="aa058-126">Клиенты</span><span class="sxs-lookup"><span data-stu-id="aa058-126">Clients</span></span>](../../../wcf/feature-details/clients.md)
