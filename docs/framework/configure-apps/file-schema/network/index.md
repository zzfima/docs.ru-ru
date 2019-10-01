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
ms.openlocfilehash: 5e3bd1b1734fc7fba50b72785531a8b001d6d741
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698149"
---
# <a name="network-settings-schema"></a><span data-ttu-id="440ba-102">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="440ba-102">Network Settings Schema</span></span>
<span data-ttu-id="440ba-103">Параметры сети определяют способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="440ba-103">Network settings specify how the .NET Framework connects to the Internet.</span></span>

<span data-ttu-id="440ba-104">Параметры @no__t -0system. NET > указывают, как .NET Framework подключается к сети.</span><span class="sxs-lookup"><span data-stu-id="440ba-104">The \<system.net> settings specify how the .NET Framework connects to the network.</span></span> <span data-ttu-id="440ba-105">В приведенной ниже таблице описывается назначение каждого дочернего элемента конфигурации для [элемента \<system.Net> (параметры сети)](system-net-element-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="440ba-105">The following table describes the function of each child configuration element under the [\<system.Net> Element (Network Settings)](system-net-element-network-settings.md).</span></span>  
  
|<span data-ttu-id="440ba-106">Элемент</span><span class="sxs-lookup"><span data-stu-id="440ba-106">Element</span></span>|<span data-ttu-id="440ba-107">Описание</span><span class="sxs-lookup"><span data-stu-id="440ba-107">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="440ba-108">Элемент \<authenticationModules> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="440ba-108">\<authenticationModules> Element (Network Settings)</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="440ba-109">Определяет модули, используемые для проверки подлинности интернет-запросов.</span><span class="sxs-lookup"><span data-stu-id="440ba-109">Specifies the modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="440ba-110">Элемент \<connectionManagement> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="440ba-110">\<connectionManagement> Element (Network Settings)</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="440ba-111">Задает максимальное число подключений к узлам в Интернете.</span><span class="sxs-lookup"><span data-stu-id="440ba-111">Specifies the maximum number of connections to Internet hosts.</span></span>|  
|[<span data-ttu-id="440ba-112">Элемент \<defaultProxy> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="440ba-112">\<defaultProxy> Element (Network Settings)</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="440ba-113">Задает прокси-сервер, используемый для HTTP-запросов к Интернету.</span><span class="sxs-lookup"><span data-stu-id="440ba-113">Specifies the proxy server used for HTTP requests to the Internet.</span></span>|  
|[<span data-ttu-id="440ba-114">Элемент \<mailSettings> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="440ba-114">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="440ba-115">Содержит параметры отправки почты.</span><span class="sxs-lookup"><span data-stu-id="440ba-115">Contains settings for mail sending options.</span></span>|  
|[<span data-ttu-id="440ba-116">Элемент \<requestCaching> (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="440ba-116">\<requestCaching> Element (Network Settings)</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="440ba-117">Управляет механизмом кэширования для сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="440ba-117">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="440ba-118">Элемент \<webRequestModules> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="440ba-118">\<webRequestModules> Element (Network Settings)</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="440ba-119">Задает модули, используемые для запроса данных от узлов в Интернете.</span><span class="sxs-lookup"><span data-stu-id="440ba-119">Specifies the modules used to request information from Internet hosts.</span></span>|  
  
<span data-ttu-id="440ba-120">Параметры \<uri > определяют, как .NET Framework обрабатывает веб-адреса, выраженные с помощью универсальных идентификаторов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="440ba-120">The \<uri> settings specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span> <span data-ttu-id="440ba-121">В следующей таблице описывается функция каждого дочернего элемента конфигурации в [элементе \<uri > (Параметры URI)](uri-element-uri-settings.md).</span><span class="sxs-lookup"><span data-stu-id="440ba-121">The following table describes the function of each child configuration element under the [\<uri> Element (Uri Settings)](uri-element-uri-settings.md).</span></span>  
  
|<span data-ttu-id="440ba-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="440ba-122">Element</span></span>|<span data-ttu-id="440ba-123">Описание</span><span class="sxs-lookup"><span data-stu-id="440ba-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="440ba-124">Элемент \<idn> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="440ba-124">\<idn> Element (Uri Settings)</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="440ba-125">Определяет, применяется ли к доменным именам анализ международных доменных имен (IDN).</span><span class="sxs-lookup"><span data-stu-id="440ba-125">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="440ba-126">Элемент \<iriParsing> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="440ba-126">\<iriParsing> Element (Uri Settings)</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="440ba-127">Определяет, применяется ли к <xref:System.Uri> анализ международных идентификаторов ресурсов (IRI) и применяются ли правила анализа IRI.</span><span class="sxs-lookup"><span data-stu-id="440ba-127">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="440ba-128">Элемент \<schemeSettings> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="440ba-128">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="440ba-129">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="440ba-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="440ba-130">См. также</span><span class="sxs-lookup"><span data-stu-id="440ba-130">See also</span></span>

- [<span data-ttu-id="440ba-131">Настройка веб-приложений</span><span class="sxs-lookup"><span data-stu-id="440ba-131">Configuring Internet Applications</span></span>](../../../network-programming/configuring-internet-applications.md)
- [<span data-ttu-id="440ba-132">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="440ba-132">Configuration File Schema</span></span>](../index.md)
