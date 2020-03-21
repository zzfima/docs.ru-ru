---
title: Элемент <remove> для authenticationModules (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, authenticationModules
- <authenticationModules>, remove element
- <remove> element, authenticationModules
- authenticationModules, remove element
ms.assetid: abf79949-b05c-465a-b51c-bbeda9a74173
ms.openlocfilehash: d171fea193bbae068e69b8976abb8e56a5623f02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154781"
---
# <a name="remove-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="043c2-102">\<удалить элемент> для проверки подлинностиМодульы (настройки сети)</span><span class="sxs-lookup"><span data-stu-id="043c2-102">\<remove> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="043c2-103">Удаляет модуль аутентификации из приложения.</span><span class="sxs-lookup"><span data-stu-id="043c2-103">Removes an authentication module from the application.</span></span>  

<span data-ttu-id="043c2-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="043c2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="043c2-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="043c2-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="043c2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<аутентификацияМоды>**](authenticationmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="043c2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="043c2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<удалить>**</span><span class="sxs-lookup"><span data-stu-id="043c2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="043c2-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="043c2-108">Syntax</span></span>  
  
```xml  
<remove
   type="authentication module name"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="043c2-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="043c2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="043c2-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="043c2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="043c2-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="043c2-111">Attributes</span></span>  
  
|<span data-ttu-id="043c2-112">**Атрибут**</span><span class="sxs-lookup"><span data-stu-id="043c2-112">**Attribute**</span></span>|<span data-ttu-id="043c2-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="043c2-113">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="043c2-114">**тип**</span><span class="sxs-lookup"><span data-stu-id="043c2-114">**type**</span></span>|<span data-ttu-id="043c2-115">Название модуля проверки подлинности для удаления.</span><span class="sxs-lookup"><span data-stu-id="043c2-115">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="043c2-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="043c2-116">Child Elements</span></span>  
 <span data-ttu-id="043c2-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="043c2-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="043c2-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="043c2-118">Parent Elements</span></span>  
  
|<span data-ttu-id="043c2-119">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="043c2-119">**Element**</span></span>|<span data-ttu-id="043c2-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="043c2-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="043c2-121">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="043c2-121">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="043c2-122">Определяет модули, используемые для проверки подлинности сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="043c2-122">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="043c2-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="043c2-123">Remarks</span></span>  
 <span data-ttu-id="043c2-124">Элемент `remove` удаляет модули аутентификации, которые были определены ранее в файле конфигурации или на более высоком уровне в иерархии конфигурации.</span><span class="sxs-lookup"><span data-stu-id="043c2-124">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="043c2-125">Значение для `type` атрибута должно быть действительным именем класса.</span><span class="sxs-lookup"><span data-stu-id="043c2-125">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="043c2-126">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="043c2-126">Configuration Files</span></span>  
 <span data-ttu-id="043c2-127">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="043c2-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="043c2-128">Пример</span><span class="sxs-lookup"><span data-stu-id="043c2-128">Example</span></span>  
 <span data-ttu-id="043c2-129">Следующий пример удаляет модуль проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="043c2-129">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="043c2-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="043c2-130">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="043c2-131">Схема настройки сети</span><span class="sxs-lookup"><span data-stu-id="043c2-131">Network Settings Schema</span></span>](index.md)
