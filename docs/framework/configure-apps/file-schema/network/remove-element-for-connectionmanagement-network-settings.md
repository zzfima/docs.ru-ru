---
title: Элемент <remove> для connectionManagement (параметры сети)
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
ms.openlocfilehash: cbafd29be6855cbb95d17388791ba152230295cc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697846"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="b1ec0-102">Элемент > @no__t 0remove для элемент connectionManagement (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="b1ec0-102">\<remove> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="b1ec0-103">Удаляет IP-адрес или DNS-имя из списка управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="b1ec0-103">Removes an IP address or DNS name from the connection management list.</span></span>  
  
[<span data-ttu-id="b1ec0-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="b1ec0-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="b1ec0-105">&nbsp; @ no__t-1[ **@no__t -4system. NET >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b1ec0-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="b1ec0-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<connectionManagement >** ](connectionmanagement-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b1ec0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)</span></span>  
<span data-ttu-id="b1ec0-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<remove >**</span><span class="sxs-lookup"><span data-stu-id="b1ec0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1ec0-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b1ec0-108">Syntax</span></span>  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b1ec0-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b1ec0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b1ec0-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b1ec0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b1ec0-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b1ec0-111">Attributes</span></span>  
  
|<span data-ttu-id="b1ec0-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="b1ec0-112">**Attribute**</span></span>|<span data-ttu-id="b1ec0-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b1ec0-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="b1ec0-114">IP-адрес или имя DNS.</span><span class="sxs-lookup"><span data-stu-id="b1ec0-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b1ec0-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b1ec0-115">Child Elements</span></span>  
 <span data-ttu-id="b1ec0-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="b1ec0-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b1ec0-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b1ec0-117">Parent Elements</span></span>  
  
|<span data-ttu-id="b1ec0-118">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="b1ec0-118">**Element**</span></span>|<span data-ttu-id="b1ec0-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b1ec0-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b1ec0-120">Элемент connectionManagement</span><span class="sxs-lookup"><span data-stu-id="b1ec0-120">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="b1ec0-121">Задает максимальное число подключений к сетевому узлу.</span><span class="sxs-lookup"><span data-stu-id="b1ec0-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1ec0-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="b1ec0-122">Remarks</span></span>  
 <span data-ttu-id="b1ec0-123">Элемент `remove` удаляет запись списка управления подключениями для указанного сервера.</span><span class="sxs-lookup"><span data-stu-id="b1ec0-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="b1ec0-124">Значение атрибута `address` должно быть допустимым IP-адресом или именем узла.</span><span class="sxs-lookup"><span data-stu-id="b1ec0-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b1ec0-125">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="b1ec0-125">Configuration Files</span></span>  
 <span data-ttu-id="b1ec0-126">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="b1ec0-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1ec0-127">Пример</span><span class="sxs-lookup"><span data-stu-id="b1ec0-127">Example</span></span>  
 <span data-ttu-id="b1ec0-128">В следующем примере удаляются все записи списка управления подключениями для сервера `www.adventure-works.com`, а затем приложение настраивается для использования четырех подключений к серверу `www.contoso.com` и двух подключений ко всем остальным серверам.</span><span class="sxs-lookup"><span data-stu-id="b1ec0-128">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b1ec0-129">См. также</span><span class="sxs-lookup"><span data-stu-id="b1ec0-129">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="b1ec0-130">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="b1ec0-130">Network Settings Schema</span></span>](index.md)
