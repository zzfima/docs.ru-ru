---
title: Элемент <clear> для authenticationModules (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, authenticationModules
- <authenticationModules>, clear element
- <clear> element, authenticationModules
- authenticationModules, clear element
ms.assetid: dc522c45-4a80-4831-8955-f7b68a47edfd
ms.openlocfilehash: e3abd1b4c76ebda885703ccf961d58657b582f19
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087514"
---
# <a name="clear-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="4be2b-102">\<Clear > элемента для authenticationModules (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="4be2b-102">\<clear> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="4be2b-103">Удаляет из приложения все модули проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="4be2b-103">Clears all authentication modules from the application.</span></span>  

<span data-ttu-id="4be2b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4be2b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4be2b-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4be2b-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="4be2b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<authenticationModules >** ](authenticationmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4be2b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="4be2b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="4be2b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="4be2b-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4be2b-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4be2b-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4be2b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4be2b-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4be2b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4be2b-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4be2b-111">Attributes</span></span>  
 <span data-ttu-id="4be2b-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4be2b-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4be2b-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4be2b-113">Child Elements</span></span>  
 <span data-ttu-id="4be2b-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4be2b-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4be2b-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4be2b-115">Parent Elements</span></span>  
  
|<span data-ttu-id="4be2b-116">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="4be2b-116">**Element**</span></span>|<span data-ttu-id="4be2b-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="4be2b-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4be2b-118">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="4be2b-118">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="4be2b-119">Указывает модули, используемые для проверки подлинности сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="4be2b-119">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4be2b-120">Заметки</span><span class="sxs-lookup"><span data-stu-id="4be2b-120">Remarks</span></span>  
 <span data-ttu-id="4be2b-121">Элемент `clear` удаляет все модули проверки подлинности, определенные ранее в файле конфигурации или на более высоком уровне иерархии конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4be2b-121">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4be2b-122">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="4be2b-122">Configuration Files</span></span>  
 <span data-ttu-id="4be2b-123">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="4be2b-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4be2b-124">Пример</span><span class="sxs-lookup"><span data-stu-id="4be2b-124">Example</span></span>  
 <span data-ttu-id="4be2b-125">В следующем примере удаляются все настроенные модули проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="4be2b-125">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4be2b-126">См. также</span><span class="sxs-lookup"><span data-stu-id="4be2b-126">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="4be2b-127">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="4be2b-127">Network Settings Schema</span></span>](index.md)
