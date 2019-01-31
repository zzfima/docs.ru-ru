---
title: Элемент <webProxyScript> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webProxyScript
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/webProxyScript
helpviewer_keywords:
- <webProxyScript> element
- webProxyScript element
ms.assetid: a13c26db-6218-4af3-9696-38f24b23bfac
ms.openlocfilehash: e823d6065ea23f3a47dad6853a1b9e1237a616c9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257828"
---
# <a name="webproxyscript-element-network-settings"></a><span data-ttu-id="48853-102">\<webProxyScript > (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="48853-102">\<webProxyScript> Element (Network Settings)</span></span>
<span data-ttu-id="48853-103">Настраивает характеристики сценария, используемого для обнаружения веб-прокси.</span><span class="sxs-lookup"><span data-stu-id="48853-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  
  
 <span data-ttu-id="48853-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="48853-104">\<configuration></span></span>  
<span data-ttu-id="48853-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="48853-105">\<system.net></span></span>  
<span data-ttu-id="48853-106">\<Параметры ></span><span class="sxs-lookup"><span data-stu-id="48853-106">\<settings></span></span>  
<span data-ttu-id="48853-107">\<webProxyScript ></span><span class="sxs-lookup"><span data-stu-id="48853-107">\<webProxyScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48853-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="48853-108">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48853-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="48853-109">Attributes and Elements</span></span>  
 <span data-ttu-id="48853-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="48853-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48853-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="48853-111">Attributes</span></span>  
  
|<span data-ttu-id="48853-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="48853-112">Attribute</span></span>|<span data-ttu-id="48853-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="48853-113">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="48853-114">Указывает максимальное время для загрузки скрипта в часы, минуты и секунды.</span><span class="sxs-lookup"><span data-stu-id="48853-114">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="48853-115">Значение по умолчанию — одна минута.</span><span class="sxs-lookup"><span data-stu-id="48853-115">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="48853-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="48853-116">Child Elements</span></span>  
 <span data-ttu-id="48853-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="48853-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="48853-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="48853-118">Parent Elements</span></span>  
  
|<span data-ttu-id="48853-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="48853-119">Element</span></span>|<span data-ttu-id="48853-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="48853-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="48853-121">Параметры</span><span class="sxs-lookup"><span data-stu-id="48853-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="48853-122">Настраивает основные параметры сети для пространства имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="48853-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48853-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="48853-123">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="48853-124">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="48853-124">Configuration Files</span></span>  
 <span data-ttu-id="48853-125">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="48853-125">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48853-126">См. также</span><span class="sxs-lookup"><span data-stu-id="48853-126">See also</span></span>
- [<span data-ttu-id="48853-127">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="48853-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
