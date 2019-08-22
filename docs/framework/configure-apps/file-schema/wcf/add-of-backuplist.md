---
title: <add> из <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 53af01a519c244376b262db1f6515a438dcc554f
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663368"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="e4510-102">\<Добавление > \<> баккуплист</span><span class="sxs-lookup"><span data-stu-id="e4510-102">\<add> of \<backupList></span></span>
<span data-ttu-id="e4510-103">Представляет элемент конфигурации, в котором задается элемент резервной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e4510-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="e4510-104">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="e4510-104">\<system.serviceModel></span></span>  
<span data-ttu-id="e4510-105">\<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="e4510-105">\<routing></span></span>  
<span data-ttu-id="e4510-106">\<Баккуплистс ></span><span class="sxs-lookup"><span data-stu-id="e4510-106">\<backupLists></span></span>  
<span data-ttu-id="e4510-107">\<Баккуплист ></span><span class="sxs-lookup"><span data-stu-id="e4510-107">\<backupList></span></span>  
<span data-ttu-id="e4510-108">\<add></span><span class="sxs-lookup"><span data-stu-id="e4510-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4510-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e4510-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e4510-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e4510-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e4510-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e4510-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e4510-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e4510-112">Attributes</span></span>  
  
|<span data-ttu-id="e4510-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e4510-113">Attribute</span></span>|<span data-ttu-id="e4510-114">Описание</span><span class="sxs-lookup"><span data-stu-id="e4510-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e4510-115">имя</span><span class="sxs-lookup"><span data-stu-id="e4510-115">name</span></span>|<span data-ttu-id="e4510-116">Строка, задающая имя резервной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e4510-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e4510-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e4510-117">Child Elements</span></span>  
 <span data-ttu-id="e4510-118">Нет.</span><span class="sxs-lookup"><span data-stu-id="e4510-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e4510-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e4510-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e4510-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="e4510-120">Element</span></span>|<span data-ttu-id="e4510-121">Описание</span><span class="sxs-lookup"><span data-stu-id="e4510-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e4510-122">\<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="e4510-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="e4510-123">Содержит список конечных точек, которые служба маршрутизации должна использовать в случае, если основная конечная точка недоступна.</span><span class="sxs-lookup"><span data-stu-id="e4510-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e4510-124">См. также</span><span class="sxs-lookup"><span data-stu-id="e4510-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
