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
ms.openlocfilehash: 899d64633447223fffc5a9c7323a9baa7d040297
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702552"
---
# <a name="ltremovegt-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="1e789-102">&lt;Удалить&gt; элемент для connectionManagement (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="1e789-102">&lt;remove&gt; Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="1e789-103">Удаляет IP-адрес или DNS-имя из списка управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="1e789-103">Removes an IP address or DNS name from the connection management list.</span></span>  
  
 <span data-ttu-id="1e789-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1e789-104">\<configuration></span></span>  
<span data-ttu-id="1e789-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="1e789-105">\<system.net></span></span>  
<span data-ttu-id="1e789-106">\<connectionManagement ></span><span class="sxs-lookup"><span data-stu-id="1e789-106">\<connectionManagement></span></span>  
<span data-ttu-id="1e789-107">\<Удалить ></span><span class="sxs-lookup"><span data-stu-id="1e789-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e789-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e789-108">Syntax</span></span>  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e789-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1e789-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1e789-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1e789-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e789-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1e789-111">Attributes</span></span>  
  
|<span data-ttu-id="1e789-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="1e789-112">**Attribute**</span></span>|<span data-ttu-id="1e789-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="1e789-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="1e789-114">IP-адрес или DNS-имя.</span><span class="sxs-lookup"><span data-stu-id="1e789-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1e789-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1e789-115">Child Elements</span></span>  
 <span data-ttu-id="1e789-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1e789-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1e789-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1e789-117">Parent Elements</span></span>  
  
|<span data-ttu-id="1e789-118">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="1e789-118">**Element**</span></span>|<span data-ttu-id="1e789-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="1e789-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1e789-120">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="1e789-120">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="1e789-121">Задает максимальное число подключений к сетевому узлу.</span><span class="sxs-lookup"><span data-stu-id="1e789-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e789-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="1e789-122">Remarks</span></span>  
 <span data-ttu-id="1e789-123">`remove` Элемент удаляет запись списка управления подключением для указанного сервера.</span><span class="sxs-lookup"><span data-stu-id="1e789-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="1e789-124">Значение `address` атрибут должен быть допустимым IP-адресом или именем.</span><span class="sxs-lookup"><span data-stu-id="1e789-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="1e789-125">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="1e789-125">Configuration Files</span></span>  
 <span data-ttu-id="1e789-126">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="1e789-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e789-127">Пример</span><span class="sxs-lookup"><span data-stu-id="1e789-127">Example</span></span>  
 <span data-ttu-id="1e789-128">В следующем примере удаляются все записи списка управления подключением для сервера `www.adventure-works.com` , а затем настраивает приложение для использования четырех подключений к серверу `www.contoso.com` и двух подключений ко всем остальным серверам.</span><span class="sxs-lookup"><span data-stu-id="1e789-128">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1e789-129">См. также</span><span class="sxs-lookup"><span data-stu-id="1e789-129">See also</span></span>
- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="1e789-130">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="1e789-130">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
