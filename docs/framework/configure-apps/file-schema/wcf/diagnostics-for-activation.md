---
title: '&lt;diagnostics&gt; для активации'
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 4e5332eed87ded51cebcd614f45cbc8e80e570fb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747935"
---
# <a name="ltdiagnosticsgt-for-activation"></a><span data-ttu-id="ea7ee-102">&lt;diagnostics&gt; для активации</span><span class="sxs-lookup"><span data-stu-id="ea7ee-102">&lt;diagnostics&gt; for Activation</span></span>
<span data-ttu-id="ea7ee-103">Настраивает диагностические функции прослушивателя Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ea7ee-103">Configures Windows Communication Foundation (WCF) listener's diagnostics functionalities.</span></span>  
  
 <span data-ttu-id="ea7ee-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="ea7ee-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="ea7ee-105">\<Диагностика ></span><span class="sxs-lookup"><span data-stu-id="ea7ee-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea7ee-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ea7ee-106">Syntax</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <diagnostics performanceCountersEnabled="Boolean" />  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a><span data-ttu-id="ea7ee-107">Тип</span><span class="sxs-lookup"><span data-stu-id="ea7ee-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea7ee-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ea7ee-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ea7ee-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ea7ee-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea7ee-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ea7ee-110">Attributes</span></span>  
  
|<span data-ttu-id="ea7ee-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ea7ee-111">Attribute</span></span>|<span data-ttu-id="ea7ee-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ea7ee-112">Description</span></span>|  
|---------------|-----------------|  
|`performanceCountersEnabled`|<span data-ttu-id="ea7ee-113">Логическое значение, определяющее, включены ли счетчики производительности для целей диагностики.</span><span class="sxs-lookup"><span data-stu-id="ea7ee-113">A Boolean value that indicates whether performance counters are enabled for diagnostic purposes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ea7ee-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ea7ee-114">Child Elements</span></span>  
 <span data-ttu-id="ea7ee-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ea7ee-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ea7ee-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ea7ee-116">Parent Elements</span></span>  
  
|<span data-ttu-id="ea7ee-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="ea7ee-117">Element</span></span>|<span data-ttu-id="ea7ee-118">Описание</span><span class="sxs-lookup"><span data-stu-id="ea7ee-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea7ee-119">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="ea7ee-119">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="ea7ee-120">Содержит параметры конфигурации для процесса прослушивателя SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="ea7ee-120">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ea7ee-121">См. также</span><span class="sxs-lookup"><span data-stu-id="ea7ee-121">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
