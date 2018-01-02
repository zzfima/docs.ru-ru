---
title: "&lt;diagnostics&gt; для активации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 20b956bb58142f26fa1402f1f974b3984ed759f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltdiagnosticsgt-for-activation"></a><span data-ttu-id="85f66-102">&lt;diagnostics&gt; для активации</span><span class="sxs-lookup"><span data-stu-id="85f66-102">&lt;diagnostics&gt; for Activation</span></span>
<span data-ttu-id="85f66-103">Настраивает диагностические функции прослушивателя службы [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85f66-103">Configures [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="85f66-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="85f66-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="85f66-105">\<Диагностика ></span><span class="sxs-lookup"><span data-stu-id="85f66-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85f66-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="85f66-106">Syntax</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <diagnostics performanceCountersEnabled="Boolean" />  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a><span data-ttu-id="85f66-107">Тип</span><span class="sxs-lookup"><span data-stu-id="85f66-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85f66-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="85f66-108">Attributes and Elements</span></span>  
 <span data-ttu-id="85f66-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="85f66-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85f66-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="85f66-110">Attributes</span></span>  
  
|<span data-ttu-id="85f66-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="85f66-111">Attribute</span></span>|<span data-ttu-id="85f66-112">Описание</span><span class="sxs-lookup"><span data-stu-id="85f66-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="85f66-113">Логическое значение, определяющее, включены ли счетчики производительности для целей диагностики.</span><span class="sxs-lookup"><span data-stu-id="85f66-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85f66-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="85f66-114">Child Elements</span></span>  
 <span data-ttu-id="85f66-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="85f66-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="85f66-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="85f66-116">Parent Elements</span></span>  
  
|<span data-ttu-id="85f66-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="85f66-117">Element</span></span>|<span data-ttu-id="85f66-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="85f66-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="85f66-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="85f66-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="85f66-120">Содержит параметры конфигурации для процесса прослушивателя SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="85f66-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="85f66-121">См. также</span><span class="sxs-lookup"><span data-stu-id="85f66-121">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
