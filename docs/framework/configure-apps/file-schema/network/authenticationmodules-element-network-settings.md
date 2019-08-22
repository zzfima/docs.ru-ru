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
ms.openlocfilehash: 6488bfcd97e27a184b4a8cd1498d1c60f32babda
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659487"
---
# <a name="authenticationmodules-element-network-settings"></a><span data-ttu-id="f387e-102">\<Элемент > authenticationModules (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="f387e-102">\<authenticationModules> Element (Network Settings)</span></span>
<span data-ttu-id="f387e-103">Указывает модули, используемые для проверки подлинности сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="f387e-103">Specifies modules used to authenticate network requests.</span></span>  
  
 <span data-ttu-id="f387e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f387e-104">\<configuration></span></span>  
<span data-ttu-id="f387e-105">\<> System. NET</span><span class="sxs-lookup"><span data-stu-id="f387e-105">\<system.net></span></span>  
<span data-ttu-id="f387e-106">\<authenticationModules ></span><span class="sxs-lookup"><span data-stu-id="f387e-106">\<authenticationModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f387e-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f387e-107">Syntax</span></span>  
  
```xml  
<authenticationModules>   
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f387e-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f387e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f387e-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f387e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f387e-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f387e-110">Attributes</span></span>  
 <span data-ttu-id="f387e-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="f387e-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f387e-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f387e-112">Child Elements</span></span>  
  
|<span data-ttu-id="f387e-113">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="f387e-113">**Element**</span></span>|<span data-ttu-id="f387e-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f387e-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f387e-115">add</span><span class="sxs-lookup"><span data-stu-id="f387e-115">add</span></span>](add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="f387e-116">Добавляет модуль проверки подлинности в приложение.</span><span class="sxs-lookup"><span data-stu-id="f387e-116">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="f387e-117">clear</span><span class="sxs-lookup"><span data-stu-id="f387e-117">clear</span></span>](clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="f387e-118">Удаляет из приложения все модули проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="f387e-118">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="f387e-119">remove</span><span class="sxs-lookup"><span data-stu-id="f387e-119">remove</span></span>](remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="f387e-120">Удаляет модуль проверки подлинности из приложения.</span><span class="sxs-lookup"><span data-stu-id="f387e-120">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f387e-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f387e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="f387e-122">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="f387e-122">**Element**</span></span>|<span data-ttu-id="f387e-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f387e-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f387e-124">system.net</span><span class="sxs-lookup"><span data-stu-id="f387e-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="f387e-125">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="f387e-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f387e-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="f387e-126">Remarks</span></span>  
 <span data-ttu-id="f387e-127">`authenticationModule` Элемент указывает модули проверки подлинности, которые выполняют процесс проверки подлинности с сервером.</span><span class="sxs-lookup"><span data-stu-id="f387e-127">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="f387e-128">Модуль проверки подлинности должен <xref:System.Net.IAuthenticationModule> реализовывать интерфейс.</span><span class="sxs-lookup"><span data-stu-id="f387e-128">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f387e-129">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="f387e-129">Configuration Files</span></span>  
 <span data-ttu-id="f387e-130">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="f387e-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f387e-131">Пример</span><span class="sxs-lookup"><span data-stu-id="f387e-131">Example</span></span>  
 <span data-ttu-id="f387e-132">В следующем примере включается модуль проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="f387e-132">The following example enables an authentication module.</span></span> <span data-ttu-id="f387e-133">Необходимо заменить значения для Version и PublicKeyToken правильными значениями для указанного модуля.</span><span class="sxs-lookup"><span data-stu-id="f387e-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f387e-134">См. также</span><span class="sxs-lookup"><span data-stu-id="f387e-134">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="f387e-135">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="f387e-135">Network Settings Schema</span></span>](index.md)
