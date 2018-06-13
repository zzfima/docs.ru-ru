---
title: '&lt;authenticationModules&gt; элемент (параметры сети)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules
helpviewer_keywords:
- authenticationModules element
- <authenticationModules> element
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 6d7f811a5746fa07264a192efdc4c5c02323e1f4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743333"
---
# <a name="ltauthenticationmodulesgt-element-network-settings"></a><span data-ttu-id="817bd-102">&lt;authenticationModules&gt; элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="817bd-102">&lt;authenticationModules&gt; Element (Network Settings)</span></span>
<span data-ttu-id="817bd-103">Задает модули, используемые для проверки подлинности сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="817bd-103">Specifies modules used to authenticate network requests.</span></span>  
  
 <span data-ttu-id="817bd-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="817bd-104">\<configuration></span></span>  
<span data-ttu-id="817bd-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="817bd-105">\<system.net></span></span>  
<span data-ttu-id="817bd-106">\<authenticationModules ></span><span class="sxs-lookup"><span data-stu-id="817bd-106">\<authenticationModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="817bd-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="817bd-107">Syntax</span></span>  
  
```xml  
<authenticationModules>   
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="817bd-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="817bd-108">Attributes and Elements</span></span>  
 <span data-ttu-id="817bd-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="817bd-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="817bd-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="817bd-110">Attributes</span></span>  
 <span data-ttu-id="817bd-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="817bd-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="817bd-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="817bd-112">Child Elements</span></span>  
  
|<span data-ttu-id="817bd-113">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="817bd-113">**Element**</span></span>|<span data-ttu-id="817bd-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="817bd-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="817bd-115">add</span><span class="sxs-lookup"><span data-stu-id="817bd-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="817bd-116">Добавляет модуль проверки подлинности для приложения.</span><span class="sxs-lookup"><span data-stu-id="817bd-116">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="817bd-117">clear</span><span class="sxs-lookup"><span data-stu-id="817bd-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="817bd-118">Удаляет все модули проверки подлинности из приложения.</span><span class="sxs-lookup"><span data-stu-id="817bd-118">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="817bd-119">remove</span><span class="sxs-lookup"><span data-stu-id="817bd-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="817bd-120">Удаляет модуль проверки подлинности из приложения.</span><span class="sxs-lookup"><span data-stu-id="817bd-120">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="817bd-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="817bd-121">Parent Elements</span></span>  
  
|<span data-ttu-id="817bd-122">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="817bd-122">**Element**</span></span>|<span data-ttu-id="817bd-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="817bd-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="817bd-124">System.NET</span><span class="sxs-lookup"><span data-stu-id="817bd-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="817bd-125">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="817bd-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="817bd-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="817bd-126">Remarks</span></span>  
 <span data-ttu-id="817bd-127">`authenticationModule` Элемент задает модули проверки подлинности, которые выполняют процесс проверки подлинности на сервере.</span><span class="sxs-lookup"><span data-stu-id="817bd-127">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="817bd-128">Модуль проверки подлинности необходимо реализовать <xref:System.Net.IAuthenticationModule> интерфейса.</span><span class="sxs-lookup"><span data-stu-id="817bd-128">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="817bd-129">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="817bd-129">Configuration Files</span></span>  
 <span data-ttu-id="817bd-130">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="817bd-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="817bd-131">Пример</span><span class="sxs-lookup"><span data-stu-id="817bd-131">Example</span></span>  
 <span data-ttu-id="817bd-132">В следующем примере включается модуля проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="817bd-132">The following example enables an authentication module.</span></span> <span data-ttu-id="817bd-133">Следует заменить значения для Version и PublicKeyToken правильные значения для указанного модуля.</span><span class="sxs-lookup"><span data-stu-id="817bd-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="817bd-134">См. также</span><span class="sxs-lookup"><span data-stu-id="817bd-134">See Also</span></span>  
 <xref:System.Net.IAuthenticationModule>  
 <xref:System.Net.AuthenticationManager>  
 [<span data-ttu-id="817bd-135">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="817bd-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
