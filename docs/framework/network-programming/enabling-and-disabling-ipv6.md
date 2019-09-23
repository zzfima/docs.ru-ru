---
title: Включение и отключение IPv6
ms.date: 03/30/2017
ms.assetid: 6408d3ef-c9ba-49d9-b15e-fe74bd3ef031
ms.openlocfilehash: 66c802dd5feb865faf7469cb7da04fbffcb4a2d6
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71048562"
---
# <a name="enabling-and-disabling-ipv6"></a><span data-ttu-id="0dfe2-102">Включение и отключение IPv6</span><span class="sxs-lookup"><span data-stu-id="0dfe2-102">Enabling and Disabling IPv6</span></span>
<span data-ttu-id="0dfe2-103">Чтобы использовать протокол IPv6, убедитесь, что он поддерживается вашей версией операционной системы, а также что операционная система и сетевые классы настроены должным образом.</span><span class="sxs-lookup"><span data-stu-id="0dfe2-103">To use the IPv6 protocol, ensure that you are running a version of the operating system that supports IPv6 and ensure that the operating system and the networking classes are configured properly.</span></span>  
  
## <a name="configuration-steps"></a><span data-ttu-id="0dfe2-104">Шаги настройки</span><span class="sxs-lookup"><span data-stu-id="0dfe2-104">Configuration Steps</span></span>  
 <span data-ttu-id="0dfe2-105">В следующей таблице перечислены различные конфигурации</span><span class="sxs-lookup"><span data-stu-id="0dfe2-105">The following table lists various configurations</span></span>  
  
|<span data-ttu-id="0dfe2-106">Операционная система поддерживает протокол IPv6?</span><span class="sxs-lookup"><span data-stu-id="0dfe2-106">Operating system IPv6-enabled?</span></span>|<span data-ttu-id="0dfe2-107">Сетевые классы поддерживают протокол IPv6?</span><span class="sxs-lookup"><span data-stu-id="0dfe2-107">Networking classes IPv6-enabled?</span></span>|<span data-ttu-id="0dfe2-108">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="0dfe2-108">Description</span></span>|  
|-------------------------------------|---------------------------------------|-----------------|  
|<span data-ttu-id="0dfe2-109">Нет</span><span class="sxs-lookup"><span data-stu-id="0dfe2-109">No</span></span>|<span data-ttu-id="0dfe2-110">Нет</span><span class="sxs-lookup"><span data-stu-id="0dfe2-110">No</span></span>|<span data-ttu-id="0dfe2-111">Можно анализировать IPv6-адреса.</span><span class="sxs-lookup"><span data-stu-id="0dfe2-111">Can parse IPv6 addresses.</span></span>|  
|<span data-ttu-id="0dfe2-112">Нет</span><span class="sxs-lookup"><span data-stu-id="0dfe2-112">No</span></span>|<span data-ttu-id="0dfe2-113">Yes</span><span class="sxs-lookup"><span data-stu-id="0dfe2-113">Yes</span></span>|<span data-ttu-id="0dfe2-114">Можно анализировать IPv6-адреса.</span><span class="sxs-lookup"><span data-stu-id="0dfe2-114">Can parse IPv6 addresses.</span></span>|  
|<span data-ttu-id="0dfe2-115">Yes</span><span class="sxs-lookup"><span data-stu-id="0dfe2-115">Yes</span></span>|<span data-ttu-id="0dfe2-116">Нет</span><span class="sxs-lookup"><span data-stu-id="0dfe2-116">No</span></span>|<span data-ttu-id="0dfe2-117">Можно анализировать IPv6-адреса и разрешать их, используя методы разрешения имен, не помеченные как устаревшие.</span><span class="sxs-lookup"><span data-stu-id="0dfe2-117">Can parse IPv6 addresses and resolve IPv6 addresses using name resolution methods not marked obsolete.</span></span>|  
|<span data-ttu-id="0dfe2-118">Yes</span><span class="sxs-lookup"><span data-stu-id="0dfe2-118">Yes</span></span>|<span data-ttu-id="0dfe2-119">Yes</span><span class="sxs-lookup"><span data-stu-id="0dfe2-119">Yes</span></span>|<span data-ttu-id="0dfe2-120">Можно анализировать и разрешать IPv6-адреса, используя все методы, в том числе и помеченные как устаревшие.</span><span class="sxs-lookup"><span data-stu-id="0dfe2-120">Can parse and resolve IPv6 addresses using all methods including those marked obsolete.</span></span>|  
  
 <span data-ttu-id="0dfe2-121">Обратите внимание, что если требуется включить поддержку IPv6 для всех классов в пространстве имен System.Net, необходимо изменить файл конфигурации компьютера или приложения.</span><span class="sxs-lookup"><span data-stu-id="0dfe2-121">Be aware that to enable the IPv6 support for all classes in the System.Net namespace, you must modify the computer configuration file or the configuration file for the application.</span></span> <span data-ttu-id="0dfe2-122">Файл конфигурации приложения имеет более высокий приоритет, чем файл конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="0dfe2-122">The configuration file for an application has precedence over the computer configuration file.</span></span>  
  
 <span data-ttu-id="0dfe2-123">Пример изменения файла конфигурации компьютера (*machine.config*) для включения поддержки IPv6 см. в разделе [Практическое руководство. Изменение файла конфигурации компьютера для включения поддержки IPv6](how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).</span><span class="sxs-lookup"><span data-stu-id="0dfe2-123">For an example of how to modify the computer configuration file, *machine.config*, to enable Ipv6 support see, [How to: Modify the Computer Configuration File to Enable Ipv6 Support](how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).</span></span> <span data-ttu-id="0dfe2-124">Также убедитесь, что в операционной системе включена поддержка протокола IPv6.</span><span class="sxs-lookup"><span data-stu-id="0dfe2-124">Also, ensure that the IPv6 support is enabled for the operating system.</span></span>  
  
 <span data-ttu-id="0dfe2-125">В файле конфигурации для платформы .NET Framework параметры установлены следующим образом</span><span class="sxs-lookup"><span data-stu-id="0dfe2-125">The .NET Framework has a configuration switch set in a configuration file as follows</span></span>  
  
```xml  
<system.net>  
  ...  
  <settings>  
    ...  
    <ipv6 enabled="true"/>  
    ...  
  </settings>  
  ...  
</system.net>  
```  
  
 <span data-ttu-id="0dfe2-126">Для .NET Framework версии 1.1 и более ранних версий параметр конфигурации **ipv6 enabled** указывает, возвращают ли члены класса <xref:System.Net.Dns?displayProperty=nameWithType> IPv6-адреса.</span><span class="sxs-lookup"><span data-stu-id="0dfe2-126">For .NET Framework version 1.1 and earlier, the value of the **ipv6 enabled** configuration switch specifies whether members of the <xref:System.Net.Dns?displayProperty=nameWithType> class return IPv6 addresses.</span></span>  
  
 <span data-ttu-id="0dfe2-127">Для .NET Framework версии 2.0 и более поздней версии, если Windows поддерживает IPv6, то члены класса <xref:System.Net.Dns?displayProperty=nameWithType> (например, метод <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType>) будут возвращать IPv6-адреса с одним ограничением.</span><span class="sxs-lookup"><span data-stu-id="0dfe2-127">For .NET Framework version 2.0 and later, if Windows supports IPv6, then members of the <xref:System.Net.Dns?displayProperty=nameWithType> class, (for example, the <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType> method), will return IPv6 addresses with one limitation.</span></span> <span data-ttu-id="0dfe2-128">Устаревшие члены службы доменных имен <xref:System.Net.Dns?displayProperty=nameWithType> (например, метод <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType>) считывают и распознают значение из файла конфигурации для параметра ipv6 enabled.</span><span class="sxs-lookup"><span data-stu-id="0dfe2-128">Obsolete members of the DNS <xref:System.Net.Dns?displayProperty=nameWithType> (for example, the <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType> method) will read and recognize the value in the configuration file for the ipv6 enabled setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dfe2-129">См. также</span><span class="sxs-lookup"><span data-stu-id="0dfe2-129">See also</span></span>

- [<span data-ttu-id="0dfe2-130">Протокол IP версии 6</span><span class="sxs-lookup"><span data-stu-id="0dfe2-130">Internet Protocol Version 6</span></span>](internet-protocol-version-6.md)
- [<span data-ttu-id="0dfe2-131">Сокеты</span><span class="sxs-lookup"><span data-stu-id="0dfe2-131">Sockets</span></span>](sockets.md)
- [<span data-ttu-id="0dfe2-132">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="0dfe2-132">Network Settings Schema</span></span>](../configure-apps/file-schema/network/index.md)
- [<span data-ttu-id="0dfe2-133">Элемент \<ipv6> (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="0dfe2-133">\<ipv6> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/ipv6-element-network-settings.md)
