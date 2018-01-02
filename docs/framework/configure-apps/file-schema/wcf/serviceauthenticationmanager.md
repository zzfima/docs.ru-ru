---
title: '&lt;serviceAuthenticationManager&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b46df4f069259ae4bb2d2769e20c6ad9e6090c00
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltserviceauthenticationmanagergt"></a><span data-ttu-id="a046f-102">&lt;serviceAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="a046f-102">&lt;serviceAuthenticationManager&gt;</span></span>
<span data-ttu-id="a046f-103">Обеспечивает элемент конфигурации рабочего процесса, который устанавливает на уровне службы действительность передачи, сообщения или инициатора.</span><span class="sxs-lookup"><span data-stu-id="a046f-103">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator..</span></span>  
  
<span data-ttu-id="a046f-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a046f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a046f-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="a046f-105">\<behaviors></span></span>  
<span data-ttu-id="a046f-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a046f-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="a046f-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="a046f-107">\<behavior></span></span>  
<span data-ttu-id="a046f-108">\<serviceAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="a046f-108">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a046f-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a046f-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a046f-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a046f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a046f-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a046f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a046f-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a046f-112">Attributes</span></span>  
  
|<span data-ttu-id="a046f-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a046f-113">Attribute</span></span>|<span data-ttu-id="a046f-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a046f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a046f-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="a046f-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="a046f-116">Строка, в которой указан тип политики проверки подлинности для текущего поведения.</span><span class="sxs-lookup"><span data-stu-id="a046f-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a046f-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a046f-117">Child Elements</span></span>  
 <span data-ttu-id="a046f-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a046f-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a046f-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a046f-119">Parent Elements</span></span>  
  
|<span data-ttu-id="a046f-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="a046f-120">Element</span></span>|<span data-ttu-id="a046f-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="a046f-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a046f-122">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="a046f-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="a046f-123">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="a046f-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a046f-124">См. также</span><span class="sxs-lookup"><span data-stu-id="a046f-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
