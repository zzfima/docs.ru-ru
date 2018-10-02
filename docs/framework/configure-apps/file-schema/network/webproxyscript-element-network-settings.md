---
title: '&lt;webProxyScript&gt; (сетевые параметры)'
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
ms.openlocfilehash: 1e1450d2df424b32aacc5c113b5936001f65915a
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2018
ms.locfileid: "48031777"
---
# <a name="ltwebproxyscriptgt-element-network-settings"></a><span data-ttu-id="cb8bd-102">&lt;webProxyScript&gt; (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="cb8bd-102">&lt;webProxyScript&gt; Element (Network Settings)</span></span>
<span data-ttu-id="cb8bd-103">Настраивает характеристики сценария, используемого для обнаружения веб-прокси.</span><span class="sxs-lookup"><span data-stu-id="cb8bd-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  
  
 <span data-ttu-id="cb8bd-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="cb8bd-104">\<configuration></span></span>  
<span data-ttu-id="cb8bd-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="cb8bd-105">\<system.net></span></span>  
<span data-ttu-id="cb8bd-106">\<Параметры ></span><span class="sxs-lookup"><span data-stu-id="cb8bd-106">\<settings></span></span>  
<span data-ttu-id="cb8bd-107">\<webProxyScript ></span><span class="sxs-lookup"><span data-stu-id="cb8bd-107">\<webProxyScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb8bd-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cb8bd-108">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb8bd-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cb8bd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="cb8bd-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cb8bd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb8bd-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cb8bd-111">Attributes</span></span>  
  
|<span data-ttu-id="cb8bd-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cb8bd-112">Attribute</span></span>|<span data-ttu-id="cb8bd-113">Описание</span><span class="sxs-lookup"><span data-stu-id="cb8bd-113">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="cb8bd-114">Указывает максимальное время для загрузки скрипта в часы, минуты и секунды.</span><span class="sxs-lookup"><span data-stu-id="cb8bd-114">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="cb8bd-115">Значение по умолчанию — одна минута.</span><span class="sxs-lookup"><span data-stu-id="cb8bd-115">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cb8bd-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cb8bd-116">Child Elements</span></span>  
 <span data-ttu-id="cb8bd-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cb8bd-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cb8bd-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cb8bd-118">Parent Elements</span></span>  
  
|<span data-ttu-id="cb8bd-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="cb8bd-119">Element</span></span>|<span data-ttu-id="cb8bd-120">Описание</span><span class="sxs-lookup"><span data-stu-id="cb8bd-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cb8bd-121">Параметры</span><span class="sxs-lookup"><span data-stu-id="cb8bd-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="cb8bd-122">Настраивает основные параметры сети для пространства имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="cb8bd-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb8bd-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="cb8bd-123">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="cb8bd-124">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="cb8bd-124">Configuration Files</span></span>  
 <span data-ttu-id="cb8bd-125">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="cb8bd-125">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb8bd-126">См. также</span><span class="sxs-lookup"><span data-stu-id="cb8bd-126">See Also</span></span>  
 [<span data-ttu-id="cb8bd-127">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="cb8bd-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
