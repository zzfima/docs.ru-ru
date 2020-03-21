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
ms.openlocfilehash: 39ce85c3c15a2d4bdfce801a35e9ca088bd5091b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154742"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="7c212-102">\<удалить элемент> для управления подключением (Настройки сети)</span><span class="sxs-lookup"><span data-stu-id="7c212-102">\<remove> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="7c212-103">Удаляет IP-адрес или имя DNS из списка управления подключением.</span><span class="sxs-lookup"><span data-stu-id="7c212-103">Removes an IP address or DNS name from the connection management list.</span></span>  

<span data-ttu-id="7c212-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7c212-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7c212-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="7c212-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="7c212-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<подключениеУправление>**](connectionmanagement-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="7c212-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)</span></span>\
<span data-ttu-id="7c212-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<удалить>**</span><span class="sxs-lookup"><span data-stu-id="7c212-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="7c212-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7c212-108">Syntax</span></span>  
  
```xml  
<remove
  address="server name or IP address"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7c212-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7c212-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7c212-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7c212-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7c212-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7c212-111">Attributes</span></span>  
  
|<span data-ttu-id="7c212-112">**Атрибут**</span><span class="sxs-lookup"><span data-stu-id="7c212-112">**Attribute**</span></span>|<span data-ttu-id="7c212-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7c212-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="7c212-114">IP-адрес или имя DNS.</span><span class="sxs-lookup"><span data-stu-id="7c212-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7c212-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7c212-115">Child Elements</span></span>  
 <span data-ttu-id="7c212-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="7c212-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7c212-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7c212-117">Parent Elements</span></span>  
  
|<span data-ttu-id="7c212-118">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="7c212-118">**Element**</span></span>|<span data-ttu-id="7c212-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7c212-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="7c212-120">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="7c212-120">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="7c212-121">Задает максимальное число подключений к сетевому узлу.</span><span class="sxs-lookup"><span data-stu-id="7c212-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c212-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="7c212-122">Remarks</span></span>  
 <span data-ttu-id="7c212-123">Элемент `remove` удаляет запись списка управления подключением для указанного сервера.</span><span class="sxs-lookup"><span data-stu-id="7c212-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="7c212-124">Значение атрибута `address` должно быть действительным IP-адресом или именем хоста.</span><span class="sxs-lookup"><span data-stu-id="7c212-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="7c212-125">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="7c212-125">Configuration Files</span></span>  
 <span data-ttu-id="7c212-126">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="7c212-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c212-127">Пример</span><span class="sxs-lookup"><span data-stu-id="7c212-127">Example</span></span>  
 <span data-ttu-id="7c212-128">Следующий пример удаляет любые записи списка `www.adventure-works.com` управления подключением для сервера, а `www.contoso.com` затем настраивает приложение на использование четырех подключений к серверу и двух подключений ко всем другим серверам.</span><span class="sxs-lookup"><span data-stu-id="7c212-128">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7c212-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7c212-129">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="7c212-130">Схема настройки сети</span><span class="sxs-lookup"><span data-stu-id="7c212-130">Network Settings Schema</span></span>](index.md)
