---
title: <net.pipe>
ms.date: 03/30/2017
ms.assetid: 6a0f0318-f8f6-466c-9fae-199d7274a82e
ms.openlocfilehash: dd984b2ab89060451b1b2d02c324e803766908ce
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397718"
---
# <a name="netpipe"></a><span data-ttu-id="e516f-102">\<> NET. pipe</span><span class="sxs-lookup"><span data-stu-id="e516f-102">\<net.pipe></span></span>
<span data-ttu-id="e516f-103">Задает параметры конфигурации для службы активации именованных каналов, которая управляет временем существования соединения для именованного канала, а также обрабатывает запросы на активацию, которые поступают по именованным каналам.</span><span class="sxs-lookup"><span data-stu-id="e516f-103">Specifies configuration settings for the Named Pipe Activation Service, which manages the lifetime of the named pipe connection, and handles activation requests that arrive over named pipes.</span></span>  
  
<span data-ttu-id="e516f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e516f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e516f-105">&nbsp;&nbsp;[ **\<> System. serviceModel. Activation**](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="e516f-105">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="e516f-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<> NET. pipe**</span><span class="sxs-lookup"><span data-stu-id="e516f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<net.pipe>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e516f-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e516f-107">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="e516f-108">Тип</span><span class="sxs-lookup"><span data-stu-id="e516f-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e516f-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e516f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e516f-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e516f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e516f-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e516f-111">Attributes</span></span>  
  
|<span data-ttu-id="e516f-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e516f-112">Attribute</span></span>|<span data-ttu-id="e516f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e516f-113">Description</span></span>|  
|---------------|-----------------|  
|`maxPendingAccepts`|<span data-ttu-id="e516f-114">Целое число, которое определяет максимальное количество одновременных необработанных принимающих потоков в конечной точке для общей службы.</span><span class="sxs-lookup"><span data-stu-id="e516f-114">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="e516f-115">Значение по умолчанию — 2</span><span class="sxs-lookup"><span data-stu-id="e516f-115">The default is 2.</span></span>|  
|`maxPendingConnections`|<span data-ttu-id="e516f-116">Целое число, задающее максимальное количество соединений, которые могут ожидать распределения.</span><span class="sxs-lookup"><span data-stu-id="e516f-116">An integer that specifies the maximum number of connections that can wait for dispatch.</span></span> <span data-ttu-id="e516f-117">Значение по умолчанию — 100.</span><span class="sxs-lookup"><span data-stu-id="e516f-117">The default is 100.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="e516f-118">Значение <xref:System.TimeSpan>, определяющее время ожидания для чтения данных кадрирования и проведения распределения подключений из базовых подключений.</span><span class="sxs-lookup"><span data-stu-id="e516f-118">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="e516f-119">Значение по умолчанию - 00:00:10.</span><span class="sxs-lookup"><span data-stu-id="e516f-119">The default is "00:00:10"</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e516f-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e516f-120">Child Elements</span></span>  
  
|<span data-ttu-id="e516f-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="e516f-121">Element</span></span>|<span data-ttu-id="e516f-122">Описание</span><span class="sxs-lookup"><span data-stu-id="e516f-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e516f-123">\<Алловаккаунтс ></span><span class="sxs-lookup"><span data-stu-id="e516f-123">\<allowAccounts></span></span>](allowaccounts.md)|<span data-ttu-id="e516f-124">Коллекция элементов конфигурации, которая содержит `securityIdentifier` атрибут для указания учетных записей пользователей для процессов, размещающий службы WCF, и которым предоставляется доступ к службе общего доступа.</span><span class="sxs-lookup"><span data-stu-id="e516f-124">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e516f-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e516f-125">Parent Elements</span></span>  
  
|<span data-ttu-id="e516f-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="e516f-126">Element</span></span>|<span data-ttu-id="e516f-127">Описание</span><span class="sxs-lookup"><span data-stu-id="e516f-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e516f-128">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="e516f-128">\<system.serviceModel.activation></span></span>](system-servicemodel-activation.md)|<span data-ttu-id="e516f-129">Содержит параметры конфигурации для процесса прослушивателя SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="e516f-129">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e516f-130">См. также</span><span class="sxs-lookup"><span data-stu-id="e516f-130">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection>
