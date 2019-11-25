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
ms.openlocfilehash: dbad888cd0537f63c09840ac1053f924db9ea9bc
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089061"
---
# <a name="webproxyscript-element-network-settings"></a><span data-ttu-id="b2455-102">Элемент \<Вебпроксискрипт > (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="b2455-102">\<webProxyScript> Element (Network Settings)</span></span>
<span data-ttu-id="b2455-103">Настраивает характеристики сценария, используемого для обнаружения веб-прокси.</span><span class="sxs-lookup"><span data-stu-id="b2455-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  

<span data-ttu-id="b2455-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b2455-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b2455-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b2455-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="b2455-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](settings-element-network-settings.md) ></span><span class="sxs-lookup"><span data-stu-id="b2455-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>\
<span data-ttu-id="b2455-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<вебпроксискрипт >**</span><span class="sxs-lookup"><span data-stu-id="b2455-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webProxyScript>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b2455-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2455-108">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2455-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b2455-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b2455-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b2455-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2455-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b2455-111">Attributes</span></span>  
  
|<span data-ttu-id="b2455-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b2455-112">Attribute</span></span>|<span data-ttu-id="b2455-113">Описание</span><span class="sxs-lookup"><span data-stu-id="b2455-113">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="b2455-114">Указывает максимальное время загрузки скрипта в часах, минутах и секундах.</span><span class="sxs-lookup"><span data-stu-id="b2455-114">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="b2455-115">Значение по умолчанию — одна минута.</span><span class="sxs-lookup"><span data-stu-id="b2455-115">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2455-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b2455-116">Child Elements</span></span>  
 <span data-ttu-id="b2455-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b2455-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b2455-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b2455-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b2455-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="b2455-119">Element</span></span>|<span data-ttu-id="b2455-120">Описание</span><span class="sxs-lookup"><span data-stu-id="b2455-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2455-121">Параметры</span><span class="sxs-lookup"><span data-stu-id="b2455-121">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="b2455-122">Настраивает основные параметры сети для пространства имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="b2455-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2455-123">Заметки</span><span class="sxs-lookup"><span data-stu-id="b2455-123">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b2455-124">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="b2455-124">Configuration Files</span></span>  
 <span data-ttu-id="b2455-125">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="b2455-125">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2455-126">См. также</span><span class="sxs-lookup"><span data-stu-id="b2455-126">See also</span></span>

- [<span data-ttu-id="b2455-127">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="b2455-127">Network Settings Schema</span></span>](index.md)
