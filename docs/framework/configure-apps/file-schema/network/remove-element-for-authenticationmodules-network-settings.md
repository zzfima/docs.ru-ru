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
ms.openlocfilehash: 7f923ce73760fa42a2c435d346f9d1097a5ed82f
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664041"
---
# <a name="remove-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="53b38-102">\<Удаление элемента > для authenticationModules (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="53b38-102">\<remove> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="53b38-103">Удаляет модуль проверки подлинности из приложения.</span><span class="sxs-lookup"><span data-stu-id="53b38-103">Removes an authentication module from the application.</span></span>  
  
 <span data-ttu-id="53b38-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="53b38-104">\<configuration></span></span>  
<span data-ttu-id="53b38-105">\<> System. NET</span><span class="sxs-lookup"><span data-stu-id="53b38-105">\<system.net></span></span>  
<span data-ttu-id="53b38-106">\<authenticationModules ></span><span class="sxs-lookup"><span data-stu-id="53b38-106">\<authenticationModules></span></span>  
<span data-ttu-id="53b38-107">\<Удалить ></span><span class="sxs-lookup"><span data-stu-id="53b38-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53b38-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="53b38-108">Syntax</span></span>  
  
```xml  
<remove   
   type="authentication module name"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53b38-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="53b38-109">Attributes and Elements</span></span>  
 <span data-ttu-id="53b38-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="53b38-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53b38-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="53b38-111">Attributes</span></span>  
  
|<span data-ttu-id="53b38-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="53b38-112">**Attribute**</span></span>|<span data-ttu-id="53b38-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="53b38-113">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="53b38-114">**type**</span><span class="sxs-lookup"><span data-stu-id="53b38-114">**type**</span></span>|<span data-ttu-id="53b38-115">Имя удаляемого модуля проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="53b38-115">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53b38-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="53b38-116">Child Elements</span></span>  
 <span data-ttu-id="53b38-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="53b38-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="53b38-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="53b38-118">Parent Elements</span></span>  
  
|<span data-ttu-id="53b38-119">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="53b38-119">**Element**</span></span>|<span data-ttu-id="53b38-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="53b38-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="53b38-121">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="53b38-121">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="53b38-122">Указывает модули, используемые для проверки подлинности сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="53b38-122">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53b38-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="53b38-123">Remarks</span></span>  
 <span data-ttu-id="53b38-124">`remove` Элемент удаляет модули проверки подлинности, которые были определены ранее в файле конфигурации или на более высоком уровне иерархии конфигурации.</span><span class="sxs-lookup"><span data-stu-id="53b38-124">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="53b38-125">Значение `type` атрибута должно быть допустимым именем класса.</span><span class="sxs-lookup"><span data-stu-id="53b38-125">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="53b38-126">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="53b38-126">Configuration Files</span></span>  
 <span data-ttu-id="53b38-127">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="53b38-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="53b38-128">Пример</span><span class="sxs-lookup"><span data-stu-id="53b38-128">Example</span></span>  
 <span data-ttu-id="53b38-129">В следующем примере удаляется модуль проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="53b38-129">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="53b38-130">См. также</span><span class="sxs-lookup"><span data-stu-id="53b38-130">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="53b38-131">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="53b38-131">Network Settings Schema</span></span>](index.md)
