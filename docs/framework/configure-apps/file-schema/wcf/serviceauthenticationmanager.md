---
title: '&lt;serviceAuthenticationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: 3b58214a1fd7a50fb1a9ab3dfee0a14870f8a476
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltserviceauthenticationmanagergt"></a><span data-ttu-id="8d498-102">&lt;serviceAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="8d498-102">&lt;serviceAuthenticationManager&gt;</span></span>
<span data-ttu-id="8d498-103">Обеспечивает элемент конфигурации рабочего процесса, который устанавливает на уровне службы действительность передачи, сообщения или инициатора.</span><span class="sxs-lookup"><span data-stu-id="8d498-103">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator..</span></span>  
  
<span data-ttu-id="8d498-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8d498-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8d498-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="8d498-105">\<behaviors></span></span>  
<span data-ttu-id="8d498-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="8d498-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="8d498-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="8d498-107">\<behavior></span></span>  
<span data-ttu-id="8d498-108">\<serviceAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="8d498-108">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d498-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d498-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8d498-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8d498-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8d498-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8d498-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8d498-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8d498-112">Attributes</span></span>  
  
|<span data-ttu-id="8d498-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8d498-113">Attribute</span></span>|<span data-ttu-id="8d498-114">Описание</span><span class="sxs-lookup"><span data-stu-id="8d498-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8d498-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="8d498-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="8d498-116">Строка, в которой указан тип политики проверки подлинности для текущего поведения.</span><span class="sxs-lookup"><span data-stu-id="8d498-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8d498-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8d498-117">Child Elements</span></span>  
 <span data-ttu-id="8d498-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8d498-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8d498-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8d498-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8d498-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="8d498-120">Element</span></span>|<span data-ttu-id="8d498-121">Описание</span><span class="sxs-lookup"><span data-stu-id="8d498-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8d498-122">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="8d498-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="8d498-123">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="8d498-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8d498-124">См. также</span><span class="sxs-lookup"><span data-stu-id="8d498-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
