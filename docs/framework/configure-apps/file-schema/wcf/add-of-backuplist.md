---
title: '&lt;add&gt; для &lt;backupList&gt;'
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 2cc7cce62082317bb86218d68bd2881b74649771
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670190"
---
# <a name="ltaddgt-of-ltbackuplistgt"></a><span data-ttu-id="da8ce-102">&lt;add&gt; для &lt;backupList&gt;</span><span class="sxs-lookup"><span data-stu-id="da8ce-102">&lt;add&gt; of &lt;backupList&gt;</span></span>
<span data-ttu-id="da8ce-103">Представляет элемент конфигурации, в котором задается элемент резервной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="da8ce-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="da8ce-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="da8ce-104">\<system.serviceModel></span></span>  
<span data-ttu-id="da8ce-105">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="da8ce-105">\<routing></span></span>  
<span data-ttu-id="da8ce-106">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="da8ce-106">\<backupLists></span></span>  
<span data-ttu-id="da8ce-107">\<backupList ></span><span class="sxs-lookup"><span data-stu-id="da8ce-107">\<backupList></span></span>  
<span data-ttu-id="da8ce-108">\<add></span><span class="sxs-lookup"><span data-stu-id="da8ce-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da8ce-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da8ce-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da8ce-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="da8ce-110">Attributes and Elements</span></span>  
 <span data-ttu-id="da8ce-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="da8ce-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da8ce-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="da8ce-112">Attributes</span></span>  
  
|<span data-ttu-id="da8ce-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="da8ce-113">Attribute</span></span>|<span data-ttu-id="da8ce-114">Описание</span><span class="sxs-lookup"><span data-stu-id="da8ce-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="da8ce-115">имя</span><span class="sxs-lookup"><span data-stu-id="da8ce-115">name</span></span>|<span data-ttu-id="da8ce-116">Строка, задающая имя резервной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="da8ce-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="da8ce-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="da8ce-117">Child Elements</span></span>  
 <span data-ttu-id="da8ce-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="da8ce-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="da8ce-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="da8ce-119">Parent Elements</span></span>  
  
|<span data-ttu-id="da8ce-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="da8ce-120">Element</span></span>|<span data-ttu-id="da8ce-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="da8ce-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da8ce-122">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="da8ce-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="da8ce-123">Содержит список конечных точек, которые вы хотите использовать служба маршрутизации в случае, если основная конечная точка становится недоступной.</span><span class="sxs-lookup"><span data-stu-id="da8ce-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="da8ce-124">См. также</span><span class="sxs-lookup"><span data-stu-id="da8ce-124">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
