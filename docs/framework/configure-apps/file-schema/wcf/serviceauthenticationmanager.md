---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: 65488c34931f6d7c424ece58a4855e746ea455bc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936414"
---
# <a name="serviceauthenticationmanager"></a><span data-ttu-id="b6cf7-101">\<Сервицеаусентикатионманажер ></span><span class="sxs-lookup"><span data-stu-id="b6cf7-101">\<serviceAuthenticationManager></span></span>
<span data-ttu-id="b6cf7-102">Обеспечивает элемент конфигурации рабочего процесса, который устанавливает на уровне службы действительность передачи, сообщения или инициатора.</span><span class="sxs-lookup"><span data-stu-id="b6cf7-102">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="b6cf7-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b6cf7-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="b6cf7-104">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="b6cf7-104">\<behaviors></span></span>  
<span data-ttu-id="b6cf7-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="b6cf7-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="b6cf7-106">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="b6cf7-106">\<behavior></span></span>  
<span data-ttu-id="b6cf7-107">\<Сервицеаусентикатионманажер ></span><span class="sxs-lookup"><span data-stu-id="b6cf7-107">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6cf7-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6cf7-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6cf7-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b6cf7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b6cf7-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b6cf7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6cf7-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b6cf7-111">Attributes</span></span>  
  
|<span data-ttu-id="b6cf7-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b6cf7-112">Attribute</span></span>|<span data-ttu-id="b6cf7-113">Описание</span><span class="sxs-lookup"><span data-stu-id="b6cf7-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b6cf7-114">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="b6cf7-114">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="b6cf7-115">Строка, в которой указан тип политики проверки подлинности для текущего поведения.</span><span class="sxs-lookup"><span data-stu-id="b6cf7-115">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b6cf7-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b6cf7-116">Child Elements</span></span>  
 <span data-ttu-id="b6cf7-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="b6cf7-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b6cf7-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b6cf7-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b6cf7-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="b6cf7-119">Element</span></span>|<span data-ttu-id="b6cf7-120">Описание</span><span class="sxs-lookup"><span data-stu-id="b6cf7-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6cf7-121">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="b6cf7-121">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="b6cf7-122">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="b6cf7-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b6cf7-123">См. также</span><span class="sxs-lookup"><span data-stu-id="b6cf7-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
