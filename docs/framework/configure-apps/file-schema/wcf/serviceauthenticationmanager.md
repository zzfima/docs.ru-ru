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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2385b96460e0a3d53efb62054fb7da334ddd2d49
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltserviceauthenticationmanagergt"></a><span data-ttu-id="97968-102">&lt;serviceAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="97968-102">&lt;serviceAuthenticationManager&gt;</span></span>
<span data-ttu-id="97968-103">Обеспечивает элемент конфигурации рабочего процесса, который устанавливает на уровне службы действительность передачи, сообщения или инициатора.</span><span class="sxs-lookup"><span data-stu-id="97968-103">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator..</span></span>  
  
<span data-ttu-id="97968-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="97968-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="97968-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="97968-105">\<behaviors></span></span>  
<span data-ttu-id="97968-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="97968-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="97968-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="97968-107">\<behavior></span></span>  
<span data-ttu-id="97968-108">\<serviceAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="97968-108">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97968-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="97968-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97968-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="97968-110">Attributes and Elements</span></span>  
 <span data-ttu-id="97968-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="97968-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97968-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="97968-112">Attributes</span></span>  
  
|<span data-ttu-id="97968-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="97968-113">Attribute</span></span>|<span data-ttu-id="97968-114">Описание</span><span class="sxs-lookup"><span data-stu-id="97968-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="97968-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="97968-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="97968-116">Строка, в которой указан тип политики проверки подлинности для текущего поведения.</span><span class="sxs-lookup"><span data-stu-id="97968-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="97968-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="97968-117">Child Elements</span></span>  
 <span data-ttu-id="97968-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="97968-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="97968-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="97968-119">Parent Elements</span></span>  
  
|<span data-ttu-id="97968-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="97968-120">Element</span></span>|<span data-ttu-id="97968-121">Описание</span><span class="sxs-lookup"><span data-stu-id="97968-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97968-122">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="97968-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="97968-123">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="97968-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="97968-124">См. также</span><span class="sxs-lookup"><span data-stu-id="97968-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
