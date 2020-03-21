---
title: Элемент <authenticationModules> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules
helpviewer_keywords:
- authenticationModules element
- <authenticationModules> element
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
ms.openlocfilehash: b502cc4a0958f074018d4b0ce6b3fb118b811c2f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154976"
---
# <a name="authenticationmodules-element-network-settings"></a><span data-ttu-id="5edef-102">\<Элемент authenticationModules> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="5edef-102">\<authenticationModules> Element (Network Settings)</span></span>
<span data-ttu-id="5edef-103">Определяет модули, используемые для проверки подлинности сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="5edef-103">Specifies modules used to authenticate network requests.</span></span>  

<span data-ttu-id="5edef-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5edef-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5edef-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="5edef-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="5edef-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<аутентификацияМоды>**</span><span class="sxs-lookup"><span data-stu-id="5edef-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<authenticationModules>**</span></span>

## <a name="syntax"></a><span data-ttu-id="5edef-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5edef-107">Syntax</span></span>  
  
```xml  
<authenticationModules>
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5edef-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5edef-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5edef-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5edef-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5edef-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5edef-110">Attributes</span></span>  
 <span data-ttu-id="5edef-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="5edef-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5edef-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5edef-112">Child Elements</span></span>  
  
|<span data-ttu-id="5edef-113">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="5edef-113">**Element**</span></span>|<span data-ttu-id="5edef-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5edef-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="5edef-115">добавление</span><span class="sxs-lookup"><span data-stu-id="5edef-115">add</span></span>](add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="5edef-116">Добавляет модуль аутентификации в приложение.</span><span class="sxs-lookup"><span data-stu-id="5edef-116">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="5edef-117">Ясно</span><span class="sxs-lookup"><span data-stu-id="5edef-117">clear</span></span>](clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="5edef-118">Очищает все модули аутентификации от приложения.</span><span class="sxs-lookup"><span data-stu-id="5edef-118">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="5edef-119">удаление</span><span class="sxs-lookup"><span data-stu-id="5edef-119">remove</span></span>](remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="5edef-120">Удаляет модуль аутентификации из приложения.</span><span class="sxs-lookup"><span data-stu-id="5edef-120">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5edef-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5edef-121">Parent Elements</span></span>  
  
|<span data-ttu-id="5edef-122">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="5edef-122">**Element**</span></span>|<span data-ttu-id="5edef-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5edef-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="5edef-124">system.net</span><span class="sxs-lookup"><span data-stu-id="5edef-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="5edef-125">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="5edef-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5edef-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="5edef-126">Remarks</span></span>  
 <span data-ttu-id="5edef-127">Элемент `authenticationModule` определяет модули аутентификации, которые проводят процесс проверки подлинности с сервером.</span><span class="sxs-lookup"><span data-stu-id="5edef-127">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="5edef-128">Модуль проверки подлинности <xref:System.Net.IAuthenticationModule> должен реализовать интерфейс.</span><span class="sxs-lookup"><span data-stu-id="5edef-128">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="5edef-129">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="5edef-129">Configuration Files</span></span>  
 <span data-ttu-id="5edef-130">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="5edef-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5edef-131">Пример</span><span class="sxs-lookup"><span data-stu-id="5edef-131">Example</span></span>  
 <span data-ttu-id="5edef-132">Следующий пример позволяет модуль аутентификации.</span><span class="sxs-lookup"><span data-stu-id="5edef-132">The following example enables an authentication module.</span></span> <span data-ttu-id="5edef-133">Необходимо заменить значения для версии и PublicKeyToken правильными значениями для указанного модуля.</span><span class="sxs-lookup"><span data-stu-id="5edef-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5edef-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5edef-134">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="5edef-135">Схема настройки сети</span><span class="sxs-lookup"><span data-stu-id="5edef-135">Network Settings Schema</span></span>](index.md)
