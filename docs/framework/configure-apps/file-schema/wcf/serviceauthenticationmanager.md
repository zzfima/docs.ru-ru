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
ms.openlocfilehash: 077878ae1746008532c3bee6b12913f98afc343f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltserviceauthenticationmanagergt"></a><span data-ttu-id="3d8cc-102">&lt;serviceAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="3d8cc-102">&lt;serviceAuthenticationManager&gt;</span></span>
<span data-ttu-id="3d8cc-103">Обеспечивает элемент конфигурации рабочего процесса, который устанавливает на уровне службы действительность передачи, сообщения или инициатора.</span><span class="sxs-lookup"><span data-stu-id="3d8cc-103">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator..</span></span>  
  
<span data-ttu-id="3d8cc-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3d8cc-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3d8cc-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="3d8cc-105">\<behaviors></span></span>  
<span data-ttu-id="3d8cc-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="3d8cc-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="3d8cc-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="3d8cc-107">\<behavior></span></span>  
<span data-ttu-id="3d8cc-108">\<serviceAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="3d8cc-108">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d8cc-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d8cc-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d8cc-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3d8cc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3d8cc-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3d8cc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d8cc-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3d8cc-112">Attributes</span></span>  
  
|<span data-ttu-id="3d8cc-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3d8cc-113">Attribute</span></span>|<span data-ttu-id="3d8cc-114">Описание</span><span class="sxs-lookup"><span data-stu-id="3d8cc-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3d8cc-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="3d8cc-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="3d8cc-116">Строка, в которой указан тип политики проверки подлинности для текущего поведения.</span><span class="sxs-lookup"><span data-stu-id="3d8cc-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3d8cc-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3d8cc-117">Child Elements</span></span>  
 <span data-ttu-id="3d8cc-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3d8cc-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3d8cc-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3d8cc-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3d8cc-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="3d8cc-120">Element</span></span>|<span data-ttu-id="3d8cc-121">Описание</span><span class="sxs-lookup"><span data-stu-id="3d8cc-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d8cc-122">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="3d8cc-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="3d8cc-123">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="3d8cc-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3d8cc-124">См. также</span><span class="sxs-lookup"><span data-stu-id="3d8cc-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
