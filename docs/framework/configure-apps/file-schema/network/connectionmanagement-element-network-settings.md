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
ms.openlocfilehash: ff2f895ca50f0d16ee9e16406f92b087b03e391e
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/26/2018
ms.locfileid: "50049117"
---
# <a name="ltconnectionmanagementgt-element-network-settings"></a><span data-ttu-id="cf185-102">&lt;connectionManagement&gt; (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="cf185-102">&lt;connectionManagement&gt; Element (Network Settings)</span></span>
<span data-ttu-id="cf185-103">Задает максимальное число подключений к сетевому узлу.</span><span class="sxs-lookup"><span data-stu-id="cf185-103">Specifies the maximum number of connections to a network host.</span></span>  
  
 <span data-ttu-id="cf185-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="cf185-104">\<configuration></span></span>  
<span data-ttu-id="cf185-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="cf185-105">\<system.net></span></span>  
<span data-ttu-id="cf185-106">\<connectionManagement ></span><span class="sxs-lookup"><span data-stu-id="cf185-106">\<connectionManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf185-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf185-107">Syntax</span></span>  
  
```xml  
<connectionManagement>   
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cf185-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cf185-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cf185-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cf185-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cf185-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cf185-110">Attributes</span></span>  
 <span data-ttu-id="cf185-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cf185-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cf185-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cf185-112">Child Elements</span></span>  
  
|<span data-ttu-id="cf185-113">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="cf185-113">**Element**</span></span>|<span data-ttu-id="cf185-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="cf185-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="cf185-115">add</span><span class="sxs-lookup"><span data-stu-id="cf185-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="cf185-116">Добавляет IP-адрес или DNS-имя в список управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="cf185-116">Adds an IP address or DNS name to the connection management list.</span></span>|  
|[<span data-ttu-id="cf185-117">clear</span><span class="sxs-lookup"><span data-stu-id="cf185-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="cf185-118">Очищает список управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="cf185-118">Clears the connection management list.</span></span>|  
|[<span data-ttu-id="cf185-119">remove</span><span class="sxs-lookup"><span data-stu-id="cf185-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="cf185-120">Удаляет IP-адрес или DNS-имя из списка управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="cf185-120">Removes an IP address or DNS name from the connection management list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cf185-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cf185-121">Parent Elements</span></span>  
  
|<span data-ttu-id="cf185-122">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="cf185-122">**Element**</span></span>|<span data-ttu-id="cf185-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="cf185-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="cf185-124">System.NET</span><span class="sxs-lookup"><span data-stu-id="cf185-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="cf185-125">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="cf185-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf185-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="cf185-126">Remarks</span></span>  
 <span data-ttu-id="cf185-127">`connectionManagement` Элемент определяет максимальное число подключений к серверу или группе серверов.</span><span class="sxs-lookup"><span data-stu-id="cf185-127">The `connectionManagement` element defines the maximum number of connections to a server or group of servers.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="cf185-128">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="cf185-128">Configuration Files</span></span>  
 <span data-ttu-id="cf185-129">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="cf185-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf185-130">Пример</span><span class="sxs-lookup"><span data-stu-id="cf185-130">Example</span></span>  
 <span data-ttu-id="cf185-131">В следующем примере настраивается приложение для использования четырех подключений к серверу `www.contoso.com` и двух подключений ко всем остальным серверам.</span><span class="sxs-lookup"><span data-stu-id="cf185-131">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cf185-132">См. также</span><span class="sxs-lookup"><span data-stu-id="cf185-132">See Also</span></span>  
 <xref:System.Net.ServicePoint>  
 <xref:System.Net.ServicePointManager>  
 [<span data-ttu-id="cf185-133">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="cf185-133">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
