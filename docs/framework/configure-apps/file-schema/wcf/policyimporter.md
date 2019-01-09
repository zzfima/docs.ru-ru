---
title: '&lt;policyImporter&gt;'
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 22d90ff9d0cd5325300cf42437836f075cbf8c31
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148491"
---
# <a name="ltpolicyimportergt"></a><span data-ttu-id="c6919-102">&lt;policyImporter&gt;</span><span class="sxs-lookup"><span data-stu-id="c6919-102">&lt;policyImporter&gt;</span></span>
<span data-ttu-id="c6919-103">Задает средство импорта политики, контролирующее импорт положений пользовательской политики о привязках.</span><span class="sxs-lookup"><span data-stu-id="c6919-103">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="c6919-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c6919-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c6919-105">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="c6919-105">\<client></span></span>  
<span data-ttu-id="c6919-106">\<метаданные ></span><span class="sxs-lookup"><span data-stu-id="c6919-106">\<metadata></span></span>  
<span data-ttu-id="c6919-107">\<policyImporters ></span><span class="sxs-lookup"><span data-stu-id="c6919-107">\<policyImporters></span></span>  
<span data-ttu-id="c6919-108">\<policyImporter ></span><span class="sxs-lookup"><span data-stu-id="c6919-108">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6919-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c6919-109">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6919-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c6919-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c6919-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c6919-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6919-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c6919-112">Attributes</span></span>  
  
|<span data-ttu-id="c6919-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c6919-113">Attribute</span></span>|<span data-ttu-id="c6919-114">Описание</span><span class="sxs-lookup"><span data-stu-id="c6919-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="c6919-115">Тип этого элемента.</span><span class="sxs-lookup"><span data-stu-id="c6919-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c6919-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c6919-116">Child Elements</span></span>  
 <span data-ttu-id="c6919-117">Нет</span><span class="sxs-lookup"><span data-stu-id="c6919-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c6919-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c6919-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c6919-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="c6919-119">Element</span></span>|<span data-ttu-id="c6919-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="c6919-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6919-121">\<policyImporters ></span><span class="sxs-lookup"><span data-stu-id="c6919-121">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="c6919-122">Задает все средства импорта политики, контролирующие импорт утверждений пользовательской политики о привязках.</span><span class="sxs-lookup"><span data-stu-id="c6919-122">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6919-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="c6919-123">Remarks</span></span>  
 <span data-ttu-id="c6919-124">Средство импорта политики используется для поиска утверждений пользовательской политики о свойствах привязки, а также для подключения пользовательского элемента привязки, реализующего свойства, необходимые для утверждения.</span><span class="sxs-lookup"><span data-stu-id="c6919-124">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6919-125">См. также</span><span class="sxs-lookup"><span data-stu-id="c6919-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElement>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 [<span data-ttu-id="c6919-126">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="c6919-126">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="c6919-127">Клиенты</span><span class="sxs-lookup"><span data-stu-id="c6919-127">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
