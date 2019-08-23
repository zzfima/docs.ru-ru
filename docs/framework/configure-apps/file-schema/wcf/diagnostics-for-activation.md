---
title: <diagnostics> для активации
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 543c41936921eda39017e07f1c97294b268a9141
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919224"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="6e40c-102">\<Диагностика > для активации</span><span class="sxs-lookup"><span data-stu-id="6e40c-102">\<diagnostics> for Activation</span></span>
<span data-ttu-id="6e40c-103">Настраивает функции диагностики прослушивателя Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="6e40c-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="6e40c-104">\<> System. serviceModel. Activation</span><span class="sxs-lookup"><span data-stu-id="6e40c-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="6e40c-105">\<Диагностика ></span><span class="sxs-lookup"><span data-stu-id="6e40c-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e40c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6e40c-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="6e40c-107">Тип</span><span class="sxs-lookup"><span data-stu-id="6e40c-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e40c-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6e40c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6e40c-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6e40c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e40c-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6e40c-110">Attributes</span></span>  
  
|<span data-ttu-id="6e40c-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6e40c-111">Attribute</span></span>|<span data-ttu-id="6e40c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="6e40c-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="6e40c-113">Логическое значение, определяющее, включены ли счетчики производительности для целей диагностики.</span><span class="sxs-lookup"><span data-stu-id="6e40c-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6e40c-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6e40c-114">Child Elements</span></span>  
 <span data-ttu-id="6e40c-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="6e40c-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6e40c-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6e40c-116">Parent Elements</span></span>  
  
|<span data-ttu-id="6e40c-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="6e40c-117">Element</span></span>|<span data-ttu-id="6e40c-118">Описание</span><span class="sxs-lookup"><span data-stu-id="6e40c-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6e40c-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="6e40c-119">\<system.serviceModel.activation></span></span>](system-servicemodel-activation.md)|<span data-ttu-id="6e40c-120">Содержит параметры конфигурации для процесса прослушивателя SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="6e40c-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6e40c-121">См. также</span><span class="sxs-lookup"><span data-stu-id="6e40c-121">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
