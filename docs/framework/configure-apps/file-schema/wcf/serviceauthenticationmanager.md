---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: 7708dd8a572dd24c2852410b1781fce2807efab9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55263489"
---
# <a name="serviceauthenticationmanager"></a><span data-ttu-id="3c50a-101">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="3c50a-101">\<serviceAuthenticationManager></span></span>
<span data-ttu-id="3c50a-102">Обеспечивает элемент конфигурации рабочего процесса, который устанавливает на уровне службы действительность передачи, сообщения или инициатора.</span><span class="sxs-lookup"><span data-stu-id="3c50a-102">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="3c50a-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3c50a-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="3c50a-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="3c50a-104">\<behaviors></span></span>  
<span data-ttu-id="3c50a-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="3c50a-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="3c50a-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="3c50a-106">\<behavior></span></span>  
<span data-ttu-id="3c50a-107">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="3c50a-107">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c50a-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c50a-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c50a-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3c50a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3c50a-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3c50a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c50a-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3c50a-111">Attributes</span></span>  
  
|<span data-ttu-id="3c50a-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3c50a-112">Attribute</span></span>|<span data-ttu-id="3c50a-113">Описание</span><span class="sxs-lookup"><span data-stu-id="3c50a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3c50a-114">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="3c50a-114">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="3c50a-115">Строка, в которой указан тип политики проверки подлинности для текущего поведения.</span><span class="sxs-lookup"><span data-stu-id="3c50a-115">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3c50a-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3c50a-116">Child Elements</span></span>  
 <span data-ttu-id="3c50a-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3c50a-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3c50a-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3c50a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="3c50a-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="3c50a-119">Element</span></span>|<span data-ttu-id="3c50a-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="3c50a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c50a-121">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="3c50a-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="3c50a-122">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="3c50a-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3c50a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="3c50a-123">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
