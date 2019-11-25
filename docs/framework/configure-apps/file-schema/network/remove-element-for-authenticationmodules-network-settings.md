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
ms.openlocfilehash: 2113b2b81ae347b398b0f25028dc6c361aec8447
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089183"
---
# <a name="remove-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="eac24-102">\<удалить элемент > для authenticationModules (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="eac24-102">\<remove> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="eac24-103">Удаляет модуль проверки подлинности из приложения.</span><span class="sxs-lookup"><span data-stu-id="eac24-103">Removes an authentication module from the application.</span></span>  

<span data-ttu-id="eac24-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="eac24-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="eac24-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="eac24-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="eac24-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<authenticationModules >** ](authenticationmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="eac24-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="eac24-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<удалить >**</span><span class="sxs-lookup"><span data-stu-id="eac24-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="eac24-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eac24-108">Syntax</span></span>  
  
```xml  
<remove   
   type="authentication module name"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eac24-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="eac24-109">Attributes and Elements</span></span>  
 <span data-ttu-id="eac24-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="eac24-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eac24-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="eac24-111">Attributes</span></span>  
  
|<span data-ttu-id="eac24-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="eac24-112">**Attribute**</span></span>|<span data-ttu-id="eac24-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="eac24-113">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="eac24-114">**type**</span><span class="sxs-lookup"><span data-stu-id="eac24-114">**type**</span></span>|<span data-ttu-id="eac24-115">Имя удаляемого модуля проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="eac24-115">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eac24-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="eac24-116">Child Elements</span></span>  
 <span data-ttu-id="eac24-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="eac24-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eac24-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="eac24-118">Parent Elements</span></span>  
  
|<span data-ttu-id="eac24-119">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="eac24-119">**Element**</span></span>|<span data-ttu-id="eac24-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="eac24-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="eac24-121">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="eac24-121">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="eac24-122">Указывает модули, используемые для проверки подлинности сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="eac24-122">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eac24-123">Заметки</span><span class="sxs-lookup"><span data-stu-id="eac24-123">Remarks</span></span>  
 <span data-ttu-id="eac24-124">Элемент `remove` удаляет модули проверки подлинности, которые были определены ранее в файле конфигурации или на более высоком уровне иерархии конфигурации.</span><span class="sxs-lookup"><span data-stu-id="eac24-124">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="eac24-125">Значение атрибута `type` должно быть допустимым именем класса.</span><span class="sxs-lookup"><span data-stu-id="eac24-125">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="eac24-126">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="eac24-126">Configuration Files</span></span>  
 <span data-ttu-id="eac24-127">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="eac24-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eac24-128">Пример</span><span class="sxs-lookup"><span data-stu-id="eac24-128">Example</span></span>  
 <span data-ttu-id="eac24-129">В следующем примере удаляется модуль проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="eac24-129">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="eac24-130">См. также</span><span class="sxs-lookup"><span data-stu-id="eac24-130">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="eac24-131">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="eac24-131">Network Settings Schema</span></span>](index.md)
