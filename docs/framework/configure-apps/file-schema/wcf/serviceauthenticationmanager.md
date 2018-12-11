---
title: '&lt;serviceAuthenticationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: 34c50e0e8c259190d3f66aa7ad1369befc629d44
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53154087"
---
# <a name="ltserviceauthenticationmanagergt"></a><span data-ttu-id="e16df-102">&lt;serviceAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="e16df-102">&lt;serviceAuthenticationManager&gt;</span></span>
<span data-ttu-id="e16df-103">Обеспечивает элемент конфигурации рабочего процесса, который устанавливает на уровне службы действительность передачи, сообщения или инициатора.</span><span class="sxs-lookup"><span data-stu-id="e16df-103">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="e16df-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e16df-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e16df-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="e16df-105">\<behaviors></span></span>  
<span data-ttu-id="e16df-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e16df-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="e16df-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="e16df-107">\<behavior></span></span>  
<span data-ttu-id="e16df-108">\<serviceAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="e16df-108">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e16df-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e16df-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e16df-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e16df-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e16df-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e16df-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e16df-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e16df-112">Attributes</span></span>  
  
|<span data-ttu-id="e16df-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e16df-113">Attribute</span></span>|<span data-ttu-id="e16df-114">Описание</span><span class="sxs-lookup"><span data-stu-id="e16df-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e16df-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="e16df-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="e16df-116">Строка, в которой указан тип политики проверки подлинности для текущего поведения.</span><span class="sxs-lookup"><span data-stu-id="e16df-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e16df-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e16df-117">Child Elements</span></span>  
 <span data-ttu-id="e16df-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e16df-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e16df-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e16df-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e16df-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="e16df-120">Element</span></span>|<span data-ttu-id="e16df-121">Описание</span><span class="sxs-lookup"><span data-stu-id="e16df-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e16df-122">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="e16df-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="e16df-123">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="e16df-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e16df-124">См. также</span><span class="sxs-lookup"><span data-stu-id="e16df-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
