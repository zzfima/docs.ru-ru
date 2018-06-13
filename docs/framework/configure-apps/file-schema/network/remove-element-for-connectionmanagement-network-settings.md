---
title: '&lt;Удалить&gt; элемент для connectionManagement (параметры сети)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- connectionManagement, remove element
- <remove> element, connectionManagement
- <connectionManagement>, remove element
- remove element, connectionManagement
ms.assetid: 94b81775-5a22-4975-8c47-8620c40c3f35
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 8d503e06139fc6ce14f4d2c50c46e4bcfeb1b860
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754484"
---
# <a name="ltremovegt-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="989f0-102">&lt;Удалить&gt; элемент для connectionManagement (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="989f0-102">&lt;remove&gt; Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="989f0-103">Удаляет IP-адрес или DNS-имя из списка управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="989f0-103">Removes an IP address or DNS name from the connection management list.</span></span>  
  
 <span data-ttu-id="989f0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="989f0-104">\<configuration></span></span>  
<span data-ttu-id="989f0-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="989f0-105">\<system.net></span></span>  
<span data-ttu-id="989f0-106">\<connectionManagement ></span><span class="sxs-lookup"><span data-stu-id="989f0-106">\<connectionManagement></span></span>  
<span data-ttu-id="989f0-107">\<Удалите ></span><span class="sxs-lookup"><span data-stu-id="989f0-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="989f0-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="989f0-108">Syntax</span></span>  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="989f0-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="989f0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="989f0-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="989f0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="989f0-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="989f0-111">Attributes</span></span>  
  
|<span data-ttu-id="989f0-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="989f0-112">**Attribute**</span></span>|<span data-ttu-id="989f0-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="989f0-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="989f0-114">IP-адрес или DNS-имя.</span><span class="sxs-lookup"><span data-stu-id="989f0-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="989f0-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="989f0-115">Child Elements</span></span>  
 <span data-ttu-id="989f0-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="989f0-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="989f0-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="989f0-117">Parent Elements</span></span>  
  
|<span data-ttu-id="989f0-118">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="989f0-118">**Element**</span></span>|<span data-ttu-id="989f0-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="989f0-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="989f0-120">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="989f0-120">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="989f0-121">Задает максимальное число подключений к сетевому узлу.</span><span class="sxs-lookup"><span data-stu-id="989f0-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="989f0-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="989f0-122">Remarks</span></span>  
 <span data-ttu-id="989f0-123">`remove` Элемент удаляет запись списка управления подключением для указанного сервера.</span><span class="sxs-lookup"><span data-stu-id="989f0-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="989f0-124">Значение `address` атрибут должен иметь допустимый IP-адрес или имя.</span><span class="sxs-lookup"><span data-stu-id="989f0-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="989f0-125">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="989f0-125">Configuration Files</span></span>  
 <span data-ttu-id="989f0-126">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="989f0-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="989f0-127">Пример</span><span class="sxs-lookup"><span data-stu-id="989f0-127">Example</span></span>  
 <span data-ttu-id="989f0-128">Следующий пример удаляет все записи списка управления подключением www.adventure-works.com сервера и затем приложение настраивается для использования четырех подключений к серверу www.contoso.com и двух подключений ко всем другим серверам.</span><span class="sxs-lookup"><span data-stu-id="989f0-128">The following example removes any connection management list entries for the server www.adventure-works.com and then configures an application to use four connections to the server www.contoso.com and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <remove address="http://www.adventure-works.com" />  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="989f0-129">См. также</span><span class="sxs-lookup"><span data-stu-id="989f0-129">See Also</span></span>  
 <xref:System.Net.ServicePoint>  
 <xref:System.Net.ServicePointManager>  
 [<span data-ttu-id="989f0-130">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="989f0-130">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
