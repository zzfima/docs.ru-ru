---
title: <diagnostics> для активации
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 30456963a7d74a93e39bb1fddc0910daae97f039
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203812"
---
# <a name="diagnostics-for-activation"></a><span data-ttu-id="36bbb-102">\<Диагностика > для активации</span><span class="sxs-lookup"><span data-stu-id="36bbb-102">\<diagnostics> for Activation</span></span>
<span data-ttu-id="36bbb-103">Настраивает диагностические функции прослушивателя службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="36bbb-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="36bbb-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="36bbb-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="36bbb-105">\<Диагностика ></span><span class="sxs-lookup"><span data-stu-id="36bbb-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36bbb-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="36bbb-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="36bbb-107">Тип</span><span class="sxs-lookup"><span data-stu-id="36bbb-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36bbb-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="36bbb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="36bbb-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="36bbb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36bbb-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="36bbb-110">Attributes</span></span>  
  
|<span data-ttu-id="36bbb-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="36bbb-111">Attribute</span></span>|<span data-ttu-id="36bbb-112">Описание</span><span class="sxs-lookup"><span data-stu-id="36bbb-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="36bbb-113">Логическое значение, определяющее, включены ли счетчики производительности для целей диагностики.</span><span class="sxs-lookup"><span data-stu-id="36bbb-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="36bbb-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="36bbb-114">Child Elements</span></span>  
 <span data-ttu-id="36bbb-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="36bbb-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="36bbb-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="36bbb-116">Parent Elements</span></span>  
  
|<span data-ttu-id="36bbb-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="36bbb-117">Element</span></span>|<span data-ttu-id="36bbb-118">Описание</span><span class="sxs-lookup"><span data-stu-id="36bbb-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36bbb-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="36bbb-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="36bbb-120">Содержит параметры конфигурации для процесса прослушивателя SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="36bbb-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="36bbb-121">См. также</span><span class="sxs-lookup"><span data-stu-id="36bbb-121">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
