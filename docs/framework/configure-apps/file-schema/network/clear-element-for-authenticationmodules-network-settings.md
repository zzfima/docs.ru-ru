---
title: '&lt;Очистить&gt; элемент для authenticationModules (параметры сети)'
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
ms.openlocfilehash: b2f5194cc6a4c7c0329edb2a1718a642781f79b9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563422"
---
# <a name="ltcleargt-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="3d3ee-102">&lt;Очистить&gt; элемент для authenticationModules (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="3d3ee-102">&lt;clear&gt; Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="3d3ee-103">Удаляет все модули проверки подлинности из приложения.</span><span class="sxs-lookup"><span data-stu-id="3d3ee-103">Clears all authentication modules from the application.</span></span>  
  
 <span data-ttu-id="3d3ee-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3d3ee-104">\<configuration></span></span>  
<span data-ttu-id="3d3ee-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="3d3ee-105">\<system.net></span></span>  
<span data-ttu-id="3d3ee-106">\<authenticationModules></span><span class="sxs-lookup"><span data-stu-id="3d3ee-106">\<authenticationModules></span></span>  
<span data-ttu-id="3d3ee-107">\<Очистить ></span><span class="sxs-lookup"><span data-stu-id="3d3ee-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d3ee-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d3ee-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d3ee-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3d3ee-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3d3ee-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3d3ee-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d3ee-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3d3ee-111">Attributes</span></span>  
 <span data-ttu-id="3d3ee-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3d3ee-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3d3ee-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3d3ee-113">Child Elements</span></span>  
 <span data-ttu-id="3d3ee-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3d3ee-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3d3ee-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3d3ee-115">Parent Elements</span></span>  
  
|<span data-ttu-id="3d3ee-116">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="3d3ee-116">**Element**</span></span>|<span data-ttu-id="3d3ee-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="3d3ee-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="3d3ee-118">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="3d3ee-118">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="3d3ee-119">Задает модули, используемые для проверки подлинности сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="3d3ee-119">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d3ee-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="3d3ee-120">Remarks</span></span>  
 <span data-ttu-id="3d3ee-121">`clear` Приводит к удалению всех модулей проверки подлинности, которые были ранее определены в файле конфигурации или на более высоком уровне в иерархии конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3d3ee-121">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3d3ee-122">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="3d3ee-122">Configuration Files</span></span>  
 <span data-ttu-id="3d3ee-123">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="3d3ee-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d3ee-124">Пример</span><span class="sxs-lookup"><span data-stu-id="3d3ee-124">Example</span></span>  
 <span data-ttu-id="3d3ee-125">В следующем примере удаляется все настроенные модули проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="3d3ee-125">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3d3ee-126">См. также</span><span class="sxs-lookup"><span data-stu-id="3d3ee-126">See also</span></span>
- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="3d3ee-127">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="3d3ee-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
