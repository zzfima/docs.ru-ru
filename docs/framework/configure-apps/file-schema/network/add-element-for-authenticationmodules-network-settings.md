---
title: Элемент <add> для authenticationModules (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/add
helpviewer_keywords:
- authenticationModules, add element
- add element, authenticationModules
- <authenticationModules>, add element
- <add> element, authenticationModules
ms.assetid: 333c5fb0-a2ab-4db8-8531-a7fe37bb9b5b
ms.openlocfilehash: 4181a045079bdb455a63ebda722dd6b0daf33c4d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155119"
---
# <a name="add-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="614ea-102">\<добавить элемент> для аутентификацииModules (Настройки сети)</span><span class="sxs-lookup"><span data-stu-id="614ea-102">\<add> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="614ea-103">Добавляет модуль аутентификации в приложение.</span><span class="sxs-lookup"><span data-stu-id="614ea-103">Adds an authentication module to the application.</span></span>  

<span data-ttu-id="614ea-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="614ea-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="614ea-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="614ea-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="614ea-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<аутентификацияМоды>**](authenticationmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="614ea-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="614ea-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<добавить>**</span><span class="sxs-lookup"><span data-stu-id="614ea-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="614ea-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="614ea-108">Syntax</span></span>  
  
```xml  
<add
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="614ea-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="614ea-109">Attributes and Elements</span></span>  
 <span data-ttu-id="614ea-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="614ea-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="614ea-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="614ea-111">Attributes</span></span>  
  
|<span data-ttu-id="614ea-112">**Атрибут**</span><span class="sxs-lookup"><span data-stu-id="614ea-112">**Attribute**</span></span>|<span data-ttu-id="614ea-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="614ea-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="614ea-114">Полностью квалифицированное имя <xref:System.Type.FullName%2A> типа (указано свойством) <xref:System.Reflection.Assembly.FullName%2A> и название сборки (указанное свойством), разделенное запятой.</span><span class="sxs-lookup"><span data-stu-id="614ea-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="614ea-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="614ea-115">Child Elements</span></span>  
 <span data-ttu-id="614ea-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="614ea-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="614ea-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="614ea-117">Parent Elements</span></span>  
  
|<span data-ttu-id="614ea-118">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="614ea-118">**Element**</span></span>|<span data-ttu-id="614ea-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="614ea-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="614ea-120">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="614ea-120">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="614ea-121">Определяет модули, используемые для проверки подлинности сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="614ea-121">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="614ea-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="614ea-122">Remarks</span></span>  
 <span data-ttu-id="614ea-123">Элемент `add` добавляет модуль проверки подлинности в конец списка зарегистрированных модулей проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="614ea-123">The `add` element adds an authentication module to the end of the list of registered authentication modules.</span></span> <span data-ttu-id="614ea-124">Модули аутентификации называются в порядке, в котором они были добавлены в список.</span><span class="sxs-lookup"><span data-stu-id="614ea-124">Authentication modules are called in the order in which they were added to the list.</span></span>  
  
 <span data-ttu-id="614ea-125">Значение для `type` атрибута должно быть действительным именем типа и соответствующим именем сборки, разделенным запятой.</span><span class="sxs-lookup"><span data-stu-id="614ea-125">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="614ea-126">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="614ea-126">Configuration Files</span></span>  
 <span data-ttu-id="614ea-127">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="614ea-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="614ea-128">Пример</span><span class="sxs-lookup"><span data-stu-id="614ea-128">Example</span></span>  
 <span data-ttu-id="614ea-129">Следующий пример позволяет модули аутентификации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="614ea-129">The following example enables the default authentication modules.</span></span> <span data-ttu-id="614ea-130">Необходимо заменить значения для версии и PublicKeyToken правильными значениями для указанного модуля.</span><span class="sxs-lookup"><span data-stu-id="614ea-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
        <authenticationModules>  
            <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NegotiateClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.KerberosClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NtlmClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.BasicClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
        </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="614ea-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="614ea-131">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="614ea-132">Схема настройки сети</span><span class="sxs-lookup"><span data-stu-id="614ea-132">Network Settings Schema</span></span>](index.md)
