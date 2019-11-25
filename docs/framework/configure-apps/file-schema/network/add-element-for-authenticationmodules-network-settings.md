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
ms.openlocfilehash: 9c011cf1216b98fa20e330e185e4cf2c331b31d4
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087955"
---
# <a name="add-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="e74c3-102">\<добавить элемент > для authenticationModules (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="e74c3-102">\<add> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="e74c3-103">Добавляет модуль проверки подлинности в приложение.</span><span class="sxs-lookup"><span data-stu-id="e74c3-103">Adds an authentication module to the application.</span></span>  

<span data-ttu-id="e74c3-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e74c3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e74c3-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e74c3-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="e74c3-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<authenticationModules >** ](authenticationmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e74c3-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="e74c3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<добавить >**</span><span class="sxs-lookup"><span data-stu-id="e74c3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e74c3-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e74c3-108">Syntax</span></span>  
  
```xml  
<add
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e74c3-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e74c3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e74c3-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e74c3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e74c3-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e74c3-111">Attributes</span></span>  
  
|<span data-ttu-id="e74c3-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="e74c3-112">**Attribute**</span></span>|<span data-ttu-id="e74c3-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e74c3-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="e74c3-114">Полное имя типа (обозначенное свойством <xref:System.Type.FullName%2A>) и имя сборки (определяемое свойством <xref:System.Reflection.Assembly.FullName%2A>), разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="e74c3-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e74c3-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e74c3-115">Child Elements</span></span>  
 <span data-ttu-id="e74c3-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e74c3-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e74c3-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e74c3-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e74c3-118">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="e74c3-118">**Element**</span></span>|<span data-ttu-id="e74c3-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e74c3-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e74c3-120">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="e74c3-120">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="e74c3-121">Указывает модули, используемые для проверки подлинности сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="e74c3-121">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e74c3-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="e74c3-122">Remarks</span></span>  
 <span data-ttu-id="e74c3-123">Элемент `add` добавляет модуль проверки подлинности в конец списка зарегистрированных модулей проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e74c3-123">The `add` element adds an authentication module to the end of the list of registered authentication modules.</span></span> <span data-ttu-id="e74c3-124">Модули проверки подлинности вызываются в том порядке, в котором они были добавлены в список.</span><span class="sxs-lookup"><span data-stu-id="e74c3-124">Authentication modules are called in the order in which they were added to the list.</span></span>  
  
 <span data-ttu-id="e74c3-125">Значением атрибута `type` должно быть допустимое имя типа и соответствующее имя сборки, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="e74c3-125">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e74c3-126">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="e74c3-126">Configuration Files</span></span>  
 <span data-ttu-id="e74c3-127">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="e74c3-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e74c3-128">Пример</span><span class="sxs-lookup"><span data-stu-id="e74c3-128">Example</span></span>  
 <span data-ttu-id="e74c3-129">В следующем примере включаются модули проверки подлинности по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e74c3-129">The following example enables the default authentication modules.</span></span> <span data-ttu-id="e74c3-130">Необходимо заменить значения для Version и PublicKeyToken правильными значениями для указанного модуля.</span><span class="sxs-lookup"><span data-stu-id="e74c3-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e74c3-131">См. также</span><span class="sxs-lookup"><span data-stu-id="e74c3-131">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="e74c3-132">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="e74c3-132">Network Settings Schema</span></span>](index.md)
