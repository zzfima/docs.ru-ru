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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 29f2e56dd18da9dc3ce3206f5c3c80f4a47a7ff0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltdiagnosticsgt-for-activation"></a><span data-ttu-id="eed62-102">&lt;diagnostics&gt; для активации</span><span class="sxs-lookup"><span data-stu-id="eed62-102">&lt;diagnostics&gt; for Activation</span></span>
<span data-ttu-id="eed62-103">Настраивает диагностические функции прослушивателя службы [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eed62-103">Configures [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="eed62-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="eed62-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="eed62-105">\<Диагностика ></span><span class="sxs-lookup"><span data-stu-id="eed62-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eed62-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eed62-106">Syntax</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <diagnostics performanceCountersEnabled="Boolean" />  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a><span data-ttu-id="eed62-107">Тип</span><span class="sxs-lookup"><span data-stu-id="eed62-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eed62-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="eed62-108">Attributes and Elements</span></span>  
 <span data-ttu-id="eed62-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="eed62-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eed62-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="eed62-110">Attributes</span></span>  
  
|<span data-ttu-id="eed62-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="eed62-111">Attribute</span></span>|<span data-ttu-id="eed62-112">Описание</span><span class="sxs-lookup"><span data-stu-id="eed62-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="eed62-113">Логическое значение, определяющее, включены ли счетчики производительности для целей диагностики.</span><span class="sxs-lookup"><span data-stu-id="eed62-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eed62-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="eed62-114">Child Elements</span></span>  
 <span data-ttu-id="eed62-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="eed62-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eed62-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="eed62-116">Parent Elements</span></span>  
  
|<span data-ttu-id="eed62-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="eed62-117">Element</span></span>|<span data-ttu-id="eed62-118">Описание</span><span class="sxs-lookup"><span data-stu-id="eed62-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eed62-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="eed62-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="eed62-120">Содержит параметры конфигурации для процесса прослушивателя SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="eed62-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eed62-121">См. также</span><span class="sxs-lookup"><span data-stu-id="eed62-121">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
