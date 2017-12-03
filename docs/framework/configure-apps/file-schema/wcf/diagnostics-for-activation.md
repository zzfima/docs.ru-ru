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
ms.openlocfilehash: 1610c77125d2820e3adc06b3c37177058c85abdd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltdiagnosticsgt-for-activation"></a><span data-ttu-id="1c059-102">&lt;diagnostics&gt; для активации</span><span class="sxs-lookup"><span data-stu-id="1c059-102">&lt;diagnostics&gt; for Activation</span></span>
<span data-ttu-id="1c059-103">Настраивает диагностические функции прослушивателя службы [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c059-103">Configures [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="1c059-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="1c059-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="1c059-105">\<Диагностика ></span><span class="sxs-lookup"><span data-stu-id="1c059-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c059-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1c059-106">Syntax</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <diagnostics performanceCountersEnabled="Boolean" />  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a><span data-ttu-id="1c059-107">Тип</span><span class="sxs-lookup"><span data-stu-id="1c059-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c059-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1c059-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1c059-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1c059-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c059-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1c059-110">Attributes</span></span>  
  
|<span data-ttu-id="1c059-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1c059-111">Attribute</span></span>|<span data-ttu-id="1c059-112">Описание</span><span class="sxs-lookup"><span data-stu-id="1c059-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="1c059-113">Логическое значение, определяющее, включены ли счетчики производительности для целей диагностики.</span><span class="sxs-lookup"><span data-stu-id="1c059-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1c059-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1c059-114">Child Elements</span></span>  
 <span data-ttu-id="1c059-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1c059-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1c059-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1c059-116">Parent Elements</span></span>  
  
|<span data-ttu-id="1c059-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="1c059-117">Element</span></span>|<span data-ttu-id="1c059-118">Описание</span><span class="sxs-lookup"><span data-stu-id="1c059-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c059-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="1c059-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="1c059-120">Содержит параметры конфигурации для процесса прослушивателя SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="1c059-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1c059-121">См. также</span><span class="sxs-lookup"><span data-stu-id="1c059-121">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
