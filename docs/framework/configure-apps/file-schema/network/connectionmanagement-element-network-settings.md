---
title: '&lt;connectionManagement&gt; (сетевые параметры)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement
- http://schemas.microsoft.com/.NetConfiguration/v2.0#connectionManagement
helpviewer_keywords:
- <connectionManagement> element
- connectionManagement element
ms.assetid: bedccaab-12a2-4511-8f67-e961f249aec6
ms.openlocfilehash: 7cc5f2a37c0520ee48a10afeb4b9bc83ffd61033
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2018
ms.locfileid: "50201547"
---
# <a name="ltconnectionmanagementgt-element-network-settings"></a><span data-ttu-id="32037-102">&lt;connectionManagement&gt; (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="32037-102">&lt;connectionManagement&gt; Element (Network Settings)</span></span>
<span data-ttu-id="32037-103">Задает максимальное число подключений к сетевому узлу.</span><span class="sxs-lookup"><span data-stu-id="32037-103">Specifies the maximum number of connections to a network host.</span></span>  
  
 <span data-ttu-id="32037-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="32037-104">\<configuration></span></span>  
<span data-ttu-id="32037-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="32037-105">\<system.net></span></span>  
<span data-ttu-id="32037-106">\<connectionManagement ></span><span class="sxs-lookup"><span data-stu-id="32037-106">\<connectionManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32037-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="32037-107">Syntax</span></span>  
  
```xml  
<connectionManagement>   
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32037-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="32037-108">Attributes and Elements</span></span>  
 <span data-ttu-id="32037-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="32037-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32037-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="32037-110">Attributes</span></span>  
 <span data-ttu-id="32037-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="32037-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="32037-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="32037-112">Child Elements</span></span>  
  
|<span data-ttu-id="32037-113">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="32037-113">**Element**</span></span>|<span data-ttu-id="32037-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="32037-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="32037-115">add</span><span class="sxs-lookup"><span data-stu-id="32037-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="32037-116">Добавляет IP-адрес или DNS-имя в список управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="32037-116">Adds an IP address or DNS name to the connection management list.</span></span>|  
|[<span data-ttu-id="32037-117">clear</span><span class="sxs-lookup"><span data-stu-id="32037-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="32037-118">Очищает список управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="32037-118">Clears the connection management list.</span></span>|  
|[<span data-ttu-id="32037-119">remove</span><span class="sxs-lookup"><span data-stu-id="32037-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="32037-120">Удаляет IP-адрес или DNS-имя из списка управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="32037-120">Removes an IP address or DNS name from the connection management list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="32037-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="32037-121">Parent Elements</span></span>  
  
|<span data-ttu-id="32037-122">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="32037-122">**Element**</span></span>|<span data-ttu-id="32037-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="32037-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="32037-124">System.NET</span><span class="sxs-lookup"><span data-stu-id="32037-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="32037-125">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="32037-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32037-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="32037-126">Remarks</span></span>  
 <span data-ttu-id="32037-127">`connectionManagement` Элемент определяет максимальное число подключений к серверу или группе серверов.</span><span class="sxs-lookup"><span data-stu-id="32037-127">The `connectionManagement` element defines the maximum number of connections to a server or group of servers.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="32037-128">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="32037-128">Configuration Files</span></span>  
 <span data-ttu-id="32037-129">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="32037-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="32037-130">Пример</span><span class="sxs-lookup"><span data-stu-id="32037-130">Example</span></span>  
 <span data-ttu-id="32037-131">В следующем примере настраивается приложение для использования четырех подключений к серверу `www.contoso.com` и двух подключений ко всем остальным серверам.</span><span class="sxs-lookup"><span data-stu-id="32037-131">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="32037-132">См. также</span><span class="sxs-lookup"><span data-stu-id="32037-132">See Also</span></span>  
- <xref:System.Net.ServicePoint>  
- <xref:System.Net.ServicePointManager>  
- [<span data-ttu-id="32037-133">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="32037-133">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
