---
title: Элемент <add> для connectionManagement (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/add
helpviewer_keywords:
- <add> element, connectionManagement
- <connectionManagement>, add element
- add element, connectionManagement
- connectionManagement, add element
ms.assetid: 856bf57d-1c63-46c7-a178-03d97b0a4149
ms.openlocfilehash: 093b68d31e03094bedefa96a2f2d53eb3d84edf0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155015"
---
# <a name="add-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="d8735-102">\<добавить элемент> для управления подключением (Настройки сети)</span><span class="sxs-lookup"><span data-stu-id="d8735-102">\<add> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="d8735-103">Добавляет IP-адрес или DNS-имя в список управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="d8735-103">Adds an IP address or DNS name to the connection management list.</span></span>  

<span data-ttu-id="d8735-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d8735-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d8735-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d8735-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="d8735-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<подключениеУправление>**](connectionmanagement-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d8735-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)</span></span>\
<span data-ttu-id="d8735-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<добавить>**</span><span class="sxs-lookup"><span data-stu-id="d8735-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d8735-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d8735-108">Syntax</span></span>  
  
```xml  
<add
  address="address expression"
  maxconnection="integer"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8735-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d8735-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d8735-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d8735-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8735-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d8735-111">Attributes</span></span>  
  
|<span data-ttu-id="d8735-112">**Атрибут**</span><span class="sxs-lookup"><span data-stu-id="d8735-112">**Attribute**</span></span>|<span data-ttu-id="d8735-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d8735-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="d8735-114">Строка, описывающая IP-адрес или DNS-имя.</span><span class="sxs-lookup"><span data-stu-id="d8735-114">A string describing an IP address or DNS name.</span></span>|  
|`maxconnection`|<span data-ttu-id="d8735-115">Максимальное число разрешенных подключений к серверу.</span><span class="sxs-lookup"><span data-stu-id="d8735-115">The maximum number of connections allowed to a server.</span></span> <span data-ttu-id="d8735-116">Если значение не предоставлено, используется значение по умолчанию 2.</span><span class="sxs-lookup"><span data-stu-id="d8735-116">If not supplied, the default is 2.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d8735-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d8735-117">Child Elements</span></span>  
 <span data-ttu-id="d8735-118">Нет.</span><span class="sxs-lookup"><span data-stu-id="d8735-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d8735-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d8735-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d8735-120">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="d8735-120">**Element**</span></span>|<span data-ttu-id="d8735-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d8735-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d8735-122">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="d8735-122">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="d8735-123">Задает максимальное число подключений к сетевому узлу.</span><span class="sxs-lookup"><span data-stu-id="d8735-123">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8735-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="d8735-124">Remarks</span></span>  
 <span data-ttu-id="d8735-125">В качестве значения атрибута `address` должна быть задана либо звездочка, указывающая все подключения, либо строка в форме `<schema>://<idn_hostname>[:<port>]`.</span><span class="sxs-lookup"><span data-stu-id="d8735-125">The value of the `address` attribute should be either an asterisk to indicate all connections, or a string of the form `<schema>://<idn_hostname>[:<port>]`.</span></span>  
  
 <span data-ttu-id="d8735-126">Если URI, переданный в какие-либо API HTTP, содержит символы Юникода, то имя будет преобразовано внутренним образом с помощью свойства <xref:System.Uri.DnsSafeHost%2A>, которое может возвращать строку Punycode (поведение, зависящее от текущей конфигурации IDN).</span><span class="sxs-lookup"><span data-stu-id="d8735-126">If the URI passed to any HTTP APIs contains Unicode, the name will be converted internally using <xref:System.Uri.DnsSafeHost%2A> which might return a punicode string (behavior dependent on the current IDN configuration).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="d8735-127">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="d8735-127">Configuration Files</span></span>  
 <span data-ttu-id="d8735-128">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="d8735-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8735-129">Пример</span><span class="sxs-lookup"><span data-stu-id="d8735-129">Example</span></span>  
 <span data-ttu-id="d8735-130">Следующий пример настраивает приложение на использование `www.contoso.com` четырех подключений к серверу и двух подключений ко всем другим серверам.</span><span class="sxs-lookup"><span data-stu-id="d8735-130">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d8735-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d8735-131">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="d8735-132">Схема настройки сети</span><span class="sxs-lookup"><span data-stu-id="d8735-132">Network Settings Schema</span></span>](index.md)
