---
title: Схема параметров сети
ms.date: 03/30/2017
helpviewer_keywords:
- elements [.NET Framework], network configuration elements
- sending data, network configuration elements
- receiving data, network configuration elements
- configuration settings [.NET Framework], networks
- Internet, network configuration elements
- network configuration elements
- network settings
- connections [.NET Framework], network configuration elements
- network resources, network configuration elements
ms.assetid: f1de5a0f-76c5-4833-819f-5222b8146340
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: c080ff7ebef680712581d1f77fd4eb1ec99c6a86
ms.sourcegitcommit: e8dc507cfdaad504fc9d4c83d28d24569dcef91c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/03/2018
ms.locfileid: "32742618"
---
# <a name="network-settings-schema"></a><span data-ttu-id="74f19-102">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="74f19-102">Network Settings Schema</span></span>
<span data-ttu-id="74f19-103">Параметры сети определяют способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="74f19-103">Network settings specify how the .NET Framework connects to the Internet.</span></span> <span data-ttu-id="74f19-104">В приведенной ниже таблице описывается назначение каждого дочернего элемента конфигурации для [элемента \<system.Net> (параметры сети)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="74f19-104">The following table describes the function of each child configuration element under the [\<system.Net> Element (Network Settings)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md).</span></span>  
  
|<span data-ttu-id="74f19-105">Элемент</span><span class="sxs-lookup"><span data-stu-id="74f19-105">Element</span></span>|<span data-ttu-id="74f19-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="74f19-106">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74f19-107">Элемент \<authenticationModules> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="74f19-107">\<authenticationModules> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="74f19-108">Определяет модули, используемые для проверки подлинности интернет-запросов.</span><span class="sxs-lookup"><span data-stu-id="74f19-108">Specifies the modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="74f19-109">Элемент \<connectionManagement> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="74f19-109">\<connectionManagement> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="74f19-110">Задает максимальное число подключений к узлам в Интернете.</span><span class="sxs-lookup"><span data-stu-id="74f19-110">Specifies the maximum number of connections to Internet hosts.</span></span>|  
|[<span data-ttu-id="74f19-111">Элемент \<defaultProxy> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="74f19-111">\<defaultProxy> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="74f19-112">Задает прокси-сервер, используемый для HTTP-запросов к Интернету.</span><span class="sxs-lookup"><span data-stu-id="74f19-112">Specifies the proxy server used for HTTP requests to the Internet.</span></span>|  
|[<span data-ttu-id="74f19-113">Элемент \<mailSettings> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="74f19-113">\<mailSettings> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="74f19-114">Содержит параметры отправки почты.</span><span class="sxs-lookup"><span data-stu-id="74f19-114">Contains settings for mail sending options.</span></span>|  
|[<span data-ttu-id="74f19-115">Элемент \<requestCaching> (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="74f19-115">\<requestCaching> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="74f19-116">Определяет механизм кэширования для сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="74f19-116">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="74f19-117">Элемент \<webRequestModules> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="74f19-117">\<webRequestModules> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="74f19-118">Задает модули, используемые для запроса данных от узлов в Интернете.</span><span class="sxs-lookup"><span data-stu-id="74f19-118">Specifies the modules used to request information from Internet hosts.</span></span>|  
  
 <span data-ttu-id="74f19-119">Параметры универсальных кодов ресурсов (URI) определяют, как платформа .NET Framework обрабатывает веб-адреса, выраженные с использованием URI.</span><span class="sxs-lookup"><span data-stu-id="74f19-119">Uri settings specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span> <span data-ttu-id="74f19-120">В приведенной ниже таблице описывается назначение каждого дочернего элемента конфигурации для [элемента \<Uri> (параметры URI)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md).</span><span class="sxs-lookup"><span data-stu-id="74f19-120">The following table describes the function of each child configuration element under the [\<Uri> Element (Uri Settings)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md).</span></span>  
  
|<span data-ttu-id="74f19-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="74f19-121">Element</span></span>|<span data-ttu-id="74f19-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="74f19-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74f19-123">Элемент \<idn> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="74f19-123">\<idn> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|<span data-ttu-id="74f19-124">Определяет, применяется ли к доменным именам анализ международных доменных имен (IDN).</span><span class="sxs-lookup"><span data-stu-id="74f19-124">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="74f19-125">Элемент \<iriParsing> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="74f19-125">\<iriParsing> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|<span data-ttu-id="74f19-126">Определяет, применяется ли к <xref:System.Uri> анализ международных идентификаторов ресурсов (IRI) и применяются ли правила анализа IRI.</span><span class="sxs-lookup"><span data-stu-id="74f19-126">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="74f19-127">Элемент \<schemeSettings> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="74f19-127">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="74f19-128">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="74f19-128">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="74f19-129">См. также</span><span class="sxs-lookup"><span data-stu-id="74f19-129">See Also</span></span>  
 [<span data-ttu-id="74f19-130">Настройка веб-приложений</span><span class="sxs-lookup"><span data-stu-id="74f19-130">Configuring Internet Applications</span></span>](../../../../../docs/framework/network-programming/configuring-internet-applications.md)  
 [<span data-ttu-id="74f19-131">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="74f19-131">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
