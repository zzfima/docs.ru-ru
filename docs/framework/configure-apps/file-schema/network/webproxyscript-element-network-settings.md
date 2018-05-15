---
title: '&lt;webProxyScript&gt; элемент (параметры сети)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webProxyScript
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/webProxyScript
helpviewer_keywords:
- <webProxyScript> element
- webProxyScript element
ms.assetid: a13c26db-6218-4af3-9696-38f24b23bfac
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 6843662b73f6b7d45dd12616f5118569a2d19975
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltwebproxyscriptgt-element-network-settings"></a><span data-ttu-id="1404f-102">&lt;webProxyScript&gt; элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="1404f-102">&lt;webProxyScript&gt; Element (Network Settings)</span></span>
<span data-ttu-id="1404f-103">Настраивает характеристики сценария для обнаружения веб-прокси.</span><span class="sxs-lookup"><span data-stu-id="1404f-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  
  
 <span data-ttu-id="1404f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1404f-104">\<configuration></span></span>  
<span data-ttu-id="1404f-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="1404f-105">\<system.net></span></span>  
<span data-ttu-id="1404f-106">\<Параметры ></span><span class="sxs-lookup"><span data-stu-id="1404f-106">\<settings></span></span>  
<span data-ttu-id="1404f-107">\<webProxyScript ></span><span class="sxs-lookup"><span data-stu-id="1404f-107">\<webProxyScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1404f-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1404f-108">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1404f-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1404f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1404f-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1404f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1404f-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1404f-111">Attributes</span></span>  
  
|<span data-ttu-id="1404f-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1404f-112">Attribute</span></span>|<span data-ttu-id="1404f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="1404f-113">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="1404f-114">Указывает максимальное время для загрузки скрипта в часах, минутах и секундах.</span><span class="sxs-lookup"><span data-stu-id="1404f-114">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="1404f-115">Значение по умолчанию составляет одну минуту.</span><span class="sxs-lookup"><span data-stu-id="1404f-115">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1404f-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1404f-116">Child Elements</span></span>  
 <span data-ttu-id="1404f-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1404f-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1404f-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1404f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="1404f-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="1404f-119">Element</span></span>|<span data-ttu-id="1404f-120">Описание</span><span class="sxs-lookup"><span data-stu-id="1404f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1404f-121">Параметры</span><span class="sxs-lookup"><span data-stu-id="1404f-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="1404f-122">Настраивает основные параметры сети для пространства имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="1404f-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1404f-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="1404f-123">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="1404f-124">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="1404f-124">Configuration Files</span></span>  
 <span data-ttu-id="1404f-125">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="1404f-125">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1404f-126">См. также</span><span class="sxs-lookup"><span data-stu-id="1404f-126">See Also</span></span>  
 [<span data-ttu-id="1404f-127">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="1404f-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
