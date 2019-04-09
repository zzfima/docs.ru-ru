---
title: <authenticationModules> (Сетевые параметры)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules
helpviewer_keywords:
- authenticationModules element
- <authenticationModules> element
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
ms.openlocfilehash: 8878bcbdf8b3613677231db3e91a6d71dfa10bae
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143342"
---
# <a name="authenticationmodules-element-network-settings"></a><span data-ttu-id="95b46-102">\<authenticationModules > (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="95b46-102">\<authenticationModules> Element (Network Settings)</span></span>
<span data-ttu-id="95b46-103">Задает модули, используемые для проверки подлинности сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="95b46-103">Specifies modules used to authenticate network requests.</span></span>  
  
 <span data-ttu-id="95b46-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="95b46-104">\<configuration></span></span>  
<span data-ttu-id="95b46-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="95b46-105">\<system.net></span></span>  
<span data-ttu-id="95b46-106">\<authenticationModules></span><span class="sxs-lookup"><span data-stu-id="95b46-106">\<authenticationModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95b46-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="95b46-107">Syntax</span></span>  
  
```xml  
<authenticationModules>   
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95b46-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="95b46-108">Attributes and Elements</span></span>  
 <span data-ttu-id="95b46-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="95b46-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95b46-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="95b46-110">Attributes</span></span>  
 <span data-ttu-id="95b46-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="95b46-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="95b46-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="95b46-112">Child Elements</span></span>  
  
|**<span data-ttu-id="95b46-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="95b46-113">Element</span></span>**|**<span data-ttu-id="95b46-114">Описание</span><span class="sxs-lookup"><span data-stu-id="95b46-114">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="95b46-115">add</span><span class="sxs-lookup"><span data-stu-id="95b46-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="95b46-116">Добавляет модуль проверки подлинности в приложение.</span><span class="sxs-lookup"><span data-stu-id="95b46-116">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="95b46-117">очистить</span><span class="sxs-lookup"><span data-stu-id="95b46-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="95b46-118">Удаляет все модули проверки подлинности из приложения.</span><span class="sxs-lookup"><span data-stu-id="95b46-118">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="95b46-119">remove</span><span class="sxs-lookup"><span data-stu-id="95b46-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="95b46-120">Удаляет модуль проверки подлинности из приложения.</span><span class="sxs-lookup"><span data-stu-id="95b46-120">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="95b46-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="95b46-121">Parent Elements</span></span>  
  
|**<span data-ttu-id="95b46-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="95b46-122">Element</span></span>**|**<span data-ttu-id="95b46-123">Описание</span><span class="sxs-lookup"><span data-stu-id="95b46-123">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="95b46-124">system.net</span><span class="sxs-lookup"><span data-stu-id="95b46-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="95b46-125">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="95b46-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95b46-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="95b46-126">Remarks</span></span>  
 <span data-ttu-id="95b46-127">`authenticationModule` Элемент определяет модули проверки подлинности, которые выполняют процесс проверки подлинности с сервером.</span><span class="sxs-lookup"><span data-stu-id="95b46-127">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="95b46-128">Модуль проверки подлинности должны реализовывать <xref:System.Net.IAuthenticationModule> интерфейс.</span><span class="sxs-lookup"><span data-stu-id="95b46-128">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="95b46-129">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="95b46-129">Configuration Files</span></span>  
 <span data-ttu-id="95b46-130">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="95b46-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="95b46-131">Пример</span><span class="sxs-lookup"><span data-stu-id="95b46-131">Example</span></span>  
 <span data-ttu-id="95b46-132">В следующем примере включается модуля проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="95b46-132">The following example enables an authentication module.</span></span> <span data-ttu-id="95b46-133">Следует заменить значения для версии и PublicKeyToken правильными значениями для указанного модуля.</span><span class="sxs-lookup"><span data-stu-id="95b46-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="95b46-134">См. также</span><span class="sxs-lookup"><span data-stu-id="95b46-134">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="95b46-135">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="95b46-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
