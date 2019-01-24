---
title: '&lt;policyImporter&gt;'
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 4075f7fcb1c65da3d9e2e5e5dab52452ca2c9b60
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632170"
---
# <a name="ltpolicyimportergt"></a><span data-ttu-id="49680-102">&lt;policyImporter&gt;</span><span class="sxs-lookup"><span data-stu-id="49680-102">&lt;policyImporter&gt;</span></span>
<span data-ttu-id="49680-103">Задает средство импорта политики, контролирующее импорт положений пользовательской политики о привязках.</span><span class="sxs-lookup"><span data-stu-id="49680-103">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="49680-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="49680-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="49680-105">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="49680-105">\<client></span></span>  
<span data-ttu-id="49680-106">\<метаданные ></span><span class="sxs-lookup"><span data-stu-id="49680-106">\<metadata></span></span>  
<span data-ttu-id="49680-107">\<policyImporters ></span><span class="sxs-lookup"><span data-stu-id="49680-107">\<policyImporters></span></span>  
<span data-ttu-id="49680-108">\<policyImporter ></span><span class="sxs-lookup"><span data-stu-id="49680-108">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49680-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49680-109">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="49680-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="49680-110">Attributes and Elements</span></span>  
 <span data-ttu-id="49680-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="49680-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="49680-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="49680-112">Attributes</span></span>  
  
|<span data-ttu-id="49680-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="49680-113">Attribute</span></span>|<span data-ttu-id="49680-114">Описание</span><span class="sxs-lookup"><span data-stu-id="49680-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="49680-115">Тип этого элемента.</span><span class="sxs-lookup"><span data-stu-id="49680-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="49680-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="49680-116">Child Elements</span></span>  
 <span data-ttu-id="49680-117">Нет</span><span class="sxs-lookup"><span data-stu-id="49680-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="49680-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="49680-118">Parent Elements</span></span>  
  
|<span data-ttu-id="49680-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="49680-119">Element</span></span>|<span data-ttu-id="49680-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="49680-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49680-121">\<policyImporters ></span><span class="sxs-lookup"><span data-stu-id="49680-121">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="49680-122">Задает все средства импорта политики, контролирующие импорт утверждений пользовательской политики о привязках.</span><span class="sxs-lookup"><span data-stu-id="49680-122">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49680-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="49680-123">Remarks</span></span>  
 <span data-ttu-id="49680-124">Средство импорта политики используется для поиска утверждений пользовательской политики о свойствах привязки, а также для подключения пользовательского элемента привязки, реализующего свойства, необходимые для утверждения.</span><span class="sxs-lookup"><span data-stu-id="49680-124">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49680-125">См. также</span><span class="sxs-lookup"><span data-stu-id="49680-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="49680-126">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="49680-126">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="49680-127">Клиенты</span><span class="sxs-lookup"><span data-stu-id="49680-127">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
