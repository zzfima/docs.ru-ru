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
ms.openlocfilehash: 9b73c0dc1fe161616c08ef0501241d55e9fea9bc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697931"
---
# <a name="remove-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="28690-102">Элемент > @no__t 0remove для authenticationModules (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="28690-102">\<remove> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="28690-103">Удаляет модуль проверки подлинности из приложения.</span><span class="sxs-lookup"><span data-stu-id="28690-103">Removes an authentication module from the application.</span></span>  
  
[<span data-ttu-id="28690-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="28690-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="28690-105">&nbsp; @ no__t-1[ **@no__t -4system. NET >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="28690-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="28690-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<authenticationModules >** ](authenticationmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="28690-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>  
<span data-ttu-id="28690-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<remove >**</span><span class="sxs-lookup"><span data-stu-id="28690-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28690-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="28690-108">Syntax</span></span>  
  
```xml  
<remove   
   type="authentication module name"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28690-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="28690-109">Attributes and Elements</span></span>  
 <span data-ttu-id="28690-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="28690-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28690-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="28690-111">Attributes</span></span>  
  
|<span data-ttu-id="28690-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="28690-112">**Attribute**</span></span>|<span data-ttu-id="28690-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="28690-113">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="28690-114">**type**</span><span class="sxs-lookup"><span data-stu-id="28690-114">**type**</span></span>|<span data-ttu-id="28690-115">Имя удаляемого модуля проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="28690-115">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="28690-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="28690-116">Child Elements</span></span>  
 <span data-ttu-id="28690-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="28690-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="28690-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="28690-118">Parent Elements</span></span>  
  
|<span data-ttu-id="28690-119">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="28690-119">**Element**</span></span>|<span data-ttu-id="28690-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="28690-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="28690-121">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="28690-121">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="28690-122">Указывает модули, используемые для проверки подлинности сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="28690-122">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28690-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="28690-123">Remarks</span></span>  
 <span data-ttu-id="28690-124">Элемент `remove` удаляет модули проверки подлинности, которые были определены ранее в файле конфигурации или на более высоком уровне иерархии конфигурации.</span><span class="sxs-lookup"><span data-stu-id="28690-124">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="28690-125">Значение атрибута `type` должно быть допустимым именем класса.</span><span class="sxs-lookup"><span data-stu-id="28690-125">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="28690-126">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="28690-126">Configuration Files</span></span>  
 <span data-ttu-id="28690-127">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="28690-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="28690-128">Пример</span><span class="sxs-lookup"><span data-stu-id="28690-128">Example</span></span>  
 <span data-ttu-id="28690-129">В следующем примере удаляется модуль проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="28690-129">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="28690-130">См. также</span><span class="sxs-lookup"><span data-stu-id="28690-130">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="28690-131">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="28690-131">Network Settings Schema</span></span>](index.md)
