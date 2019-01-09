---
title: '&lt;NET.pipe&gt;'
ms.date: 03/30/2017
ms.assetid: 6a0f0318-f8f6-466c-9fae-199d7274a82e
ms.openlocfilehash: 8a525f0684902841a2be75823932935e7533ba8b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151154"
---
# <a name="ltnetpipegt"></a><span data-ttu-id="fca23-102">&lt;NET.pipe&gt;</span><span class="sxs-lookup"><span data-stu-id="fca23-102">&lt;net.pipe&gt;</span></span>
<span data-ttu-id="fca23-103">Задает параметры конфигурации для службы активации именованных каналов, которая управляет временем существования соединения для именованного канала, а также обрабатывает запросы на активацию, которые поступают по именованным каналам.</span><span class="sxs-lookup"><span data-stu-id="fca23-103">Specifies configuration settings for the Named Pipe Activation Service, which manages the lifetime of the named pipe connection, and handles activation requests that arrive over named pipes.</span></span>  
  
 <span data-ttu-id="fca23-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="fca23-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="fca23-105">\<NET.pipe ></span><span class="sxs-lookup"><span data-stu-id="fca23-105">\<net.pipe></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fca23-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fca23-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <net.pipe maxPendingAccepts="Integer"
              maxPendingConnections="Integer"
              receiveTimeout="TimeSpan">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18" />
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19" />
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-20" />
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only) -->
        <add securityIdentifier="S-1-5-32-568" />
      </allowAccounts>
    </net.pipe>
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="fca23-107">Тип</span><span class="sxs-lookup"><span data-stu-id="fca23-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fca23-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fca23-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fca23-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fca23-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fca23-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fca23-110">Attributes</span></span>  
  
|<span data-ttu-id="fca23-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fca23-111">Attribute</span></span>|<span data-ttu-id="fca23-112">Описание</span><span class="sxs-lookup"><span data-stu-id="fca23-112">Description</span></span>|  
|---------------|-----------------|  
|`maxPendingAccepts`|<span data-ttu-id="fca23-113">Целое число, которое определяет максимальное количество одновременных необработанных принимающих потоков в конечной точке для общей службы.</span><span class="sxs-lookup"><span data-stu-id="fca23-113">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="fca23-114">Значение по умолчанию — 2.</span><span class="sxs-lookup"><span data-stu-id="fca23-114">The default is 2.</span></span>|  
|`maxPendingConnections`|<span data-ttu-id="fca23-115">Целое число, задающее максимальное количество соединений, которые могут ожидать распределения.</span><span class="sxs-lookup"><span data-stu-id="fca23-115">An integer that specifies the maximum number of connections that can wait for dispatch.</span></span> <span data-ttu-id="fca23-116">Значение по умолчанию — 100.</span><span class="sxs-lookup"><span data-stu-id="fca23-116">The default is 100.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="fca23-117">Значение `TimeSpan`, определяющее время ожидания для чтения данных кадрирования и проведения распределения подключений из базовых подключений.</span><span class="sxs-lookup"><span data-stu-id="fca23-117">A `TimeSpan` that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="fca23-118">Значение по умолчанию - 00:00:10.</span><span class="sxs-lookup"><span data-stu-id="fca23-118">The default is "00:00:10"</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fca23-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fca23-119">Child Elements</span></span>  
  
|<span data-ttu-id="fca23-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="fca23-120">Element</span></span>|<span data-ttu-id="fca23-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="fca23-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fca23-122">\<allowAccounts ></span><span class="sxs-lookup"><span data-stu-id="fca23-122">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="fca23-123">Коллекция элементов конфигурации, которые содержат `securityIdentifier` атрибут для указания учетных записей пользователей для процессов размещения служб WCF, которые предоставляются доступ при подключении к совместно используемой службе.</span><span class="sxs-lookup"><span data-stu-id="fca23-123">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fca23-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fca23-124">Parent Elements</span></span>  
  
|<span data-ttu-id="fca23-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="fca23-125">Element</span></span>|<span data-ttu-id="fca23-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="fca23-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fca23-127">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="fca23-127">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="fca23-128">Содержит параметры конфигурации для процесса прослушивателя SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="fca23-128">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fca23-129">См. также</span><span class="sxs-lookup"><span data-stu-id="fca23-129">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection>
