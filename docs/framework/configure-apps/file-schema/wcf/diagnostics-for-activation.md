---
title: <diagnostics> для активации
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 33b2cd4c5ae1b4076892a61aa7e2b927efa1ddc1
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400411"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="f8ee1-102">\<Диагностика > для активации</span><span class="sxs-lookup"><span data-stu-id="f8ee1-102">\<diagnostics> for Activation</span></span>
<span data-ttu-id="f8ee1-103">Настраивает функции диагностики прослушивателя Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f8ee1-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
<span data-ttu-id="f8ee1-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f8ee1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f8ee1-105">&nbsp;&nbsp;[ **\<> System. serviceModel. Activation**](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="f8ee1-105">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="f8ee1-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Диагностика >**</span><span class="sxs-lookup"><span data-stu-id="f8ee1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<diagnostics>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8ee1-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8ee1-107">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="f8ee1-108">Тип</span><span class="sxs-lookup"><span data-stu-id="f8ee1-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f8ee1-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f8ee1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f8ee1-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f8ee1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f8ee1-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f8ee1-111">Attributes</span></span>  
  
|<span data-ttu-id="f8ee1-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f8ee1-112">Attribute</span></span>|<span data-ttu-id="f8ee1-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f8ee1-113">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="f8ee1-114">Логическое значение, определяющее, включены ли счетчики производительности для целей диагностики.</span><span class="sxs-lookup"><span data-stu-id="f8ee1-114">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f8ee1-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f8ee1-115">Child Elements</span></span>  
 <span data-ttu-id="f8ee1-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="f8ee1-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f8ee1-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f8ee1-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f8ee1-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="f8ee1-118">Element</span></span>|<span data-ttu-id="f8ee1-119">Описание</span><span class="sxs-lookup"><span data-stu-id="f8ee1-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f8ee1-120">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="f8ee1-120">\<system.serviceModel.activation></span></span>](system-servicemodel-activation.md)|<span data-ttu-id="f8ee1-121">Содержит параметры конфигурации для процесса прослушивателя SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="f8ee1-121">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f8ee1-122">См. также</span><span class="sxs-lookup"><span data-stu-id="f8ee1-122">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
