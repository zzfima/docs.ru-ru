---
title: '&lt;Удалить&gt; элемент для authenticationModules (параметры сети)'
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
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 332f8eb4fb1a5a02df76c5745522037b029a2407
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2018
ms.locfileid: "48873272"
---
# <a name="ltremovegt-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="bfd23-102">&lt;Удалить&gt; элемент для authenticationModules (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="bfd23-102">&lt;remove&gt; Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="bfd23-103">Удаляет модуль проверки подлинности из приложения.</span><span class="sxs-lookup"><span data-stu-id="bfd23-103">Removes an authentication module from the application.</span></span>  
  
 <span data-ttu-id="bfd23-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bfd23-104">\<configuration></span></span>  
<span data-ttu-id="bfd23-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="bfd23-105">\<system.net></span></span>  
<span data-ttu-id="bfd23-106">\<authenticationModules ></span><span class="sxs-lookup"><span data-stu-id="bfd23-106">\<authenticationModules></span></span>  
<span data-ttu-id="bfd23-107">\<Удалить ></span><span class="sxs-lookup"><span data-stu-id="bfd23-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfd23-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bfd23-108">Syntax</span></span>  
  
```xml  
<remove   
   type="authentication module name"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bfd23-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bfd23-109">Attributes and Elements</span></span>  
 <span data-ttu-id="bfd23-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bfd23-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bfd23-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bfd23-111">Attributes</span></span>  
  
|<span data-ttu-id="bfd23-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="bfd23-112">**Attribute**</span></span>|<span data-ttu-id="bfd23-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="bfd23-113">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="bfd23-114">**type**</span><span class="sxs-lookup"><span data-stu-id="bfd23-114">**type**</span></span>|<span data-ttu-id="bfd23-115">Имя модуля проверки подлинности для удаления.</span><span class="sxs-lookup"><span data-stu-id="bfd23-115">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bfd23-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bfd23-116">Child Elements</span></span>  
 <span data-ttu-id="bfd23-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bfd23-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bfd23-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bfd23-118">Parent Elements</span></span>  
  
|<span data-ttu-id="bfd23-119">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="bfd23-119">**Element**</span></span>|<span data-ttu-id="bfd23-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="bfd23-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="bfd23-121">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="bfd23-121">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="bfd23-122">Задает модули, используемые для проверки подлинности сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="bfd23-122">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bfd23-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="bfd23-123">Remarks</span></span>  
 <span data-ttu-id="bfd23-124">`remove` Элемент удаляет модули проверки подлинности, которые были ранее определены в файле конфигурации или на более высоком уровне в иерархии конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bfd23-124">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="bfd23-125">Значение для `type` атрибут должен быть допустимым именем класса.</span><span class="sxs-lookup"><span data-stu-id="bfd23-125">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="bfd23-126">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="bfd23-126">Configuration Files</span></span>  
 <span data-ttu-id="bfd23-127">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="bfd23-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bfd23-128">Пример</span><span class="sxs-lookup"><span data-stu-id="bfd23-128">Example</span></span>  
 <span data-ttu-id="bfd23-129">В следующем примере удаляется модуля проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="bfd23-129">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bfd23-130">См. также</span><span class="sxs-lookup"><span data-stu-id="bfd23-130">See Also</span></span>  
 <xref:System.Net.IAuthenticationModule>  
 <xref:System.Net.AuthenticationManager>  
 [<span data-ttu-id="bfd23-131">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="bfd23-131">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
