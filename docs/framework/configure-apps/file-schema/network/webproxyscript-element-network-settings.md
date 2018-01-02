---
title: "&lt;webProxyScript&gt; элемент (параметры сети)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webProxyScript
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/webProxyScript
helpviewer_keywords:
- <webProxyScript> element
- webProxyScript element
ms.assetid: a13c26db-6218-4af3-9696-38f24b23bfac
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 4c7d6154d354e806a04ccc9da062db64c534039b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltwebproxyscriptgt-element-network-settings"></a><span data-ttu-id="04220-102">&lt;webProxyScript&gt; элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="04220-102">&lt;webProxyScript&gt; Element (Network Settings)</span></span>
<span data-ttu-id="04220-103">Настраивает характеристики сценария для обнаружения веб-прокси.</span><span class="sxs-lookup"><span data-stu-id="04220-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  
  
 <span data-ttu-id="04220-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="04220-104">\<configuration></span></span>  
<span data-ttu-id="04220-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="04220-105">\<system.net></span></span>  
<span data-ttu-id="04220-106">\<Параметры ></span><span class="sxs-lookup"><span data-stu-id="04220-106">\<settings></span></span>  
<span data-ttu-id="04220-107">\<webProxyScript ></span><span class="sxs-lookup"><span data-stu-id="04220-107">\<webProxyScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04220-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04220-108">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04220-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="04220-109">Attributes and Elements</span></span>  
 <span data-ttu-id="04220-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="04220-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04220-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="04220-111">Attributes</span></span>  
  
|<span data-ttu-id="04220-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="04220-112">Attribute</span></span>|<span data-ttu-id="04220-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="04220-113">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="04220-114">Указывает максимальное время для загрузки скрипта в часах, минутах и секундах.</span><span class="sxs-lookup"><span data-stu-id="04220-114">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="04220-115">Значение по умолчанию составляет одну минуту.</span><span class="sxs-lookup"><span data-stu-id="04220-115">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="04220-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="04220-116">Child Elements</span></span>  
 <span data-ttu-id="04220-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="04220-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="04220-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="04220-118">Parent Elements</span></span>  
  
|<span data-ttu-id="04220-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="04220-119">Element</span></span>|<span data-ttu-id="04220-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="04220-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="04220-121">Параметры</span><span class="sxs-lookup"><span data-stu-id="04220-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="04220-122">Настраивает основные параметры сети для пространства имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="04220-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04220-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="04220-123">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="04220-124">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="04220-124">Configuration Files</span></span>  
 <span data-ttu-id="04220-125">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="04220-125">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04220-126">См. также</span><span class="sxs-lookup"><span data-stu-id="04220-126">See Also</span></span>  
 [<span data-ttu-id="04220-127">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="04220-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
