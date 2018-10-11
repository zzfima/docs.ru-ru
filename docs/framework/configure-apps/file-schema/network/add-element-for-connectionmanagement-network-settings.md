---
title: '&lt;Добавление&gt; элемент для connectionManagement (параметры сети)'
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
author: mcleblanc
ms.author: markl
ms.openlocfilehash: cdc7e8501f7cf3f5cff4c29ca5b2d004ce7cd5c6
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/11/2018
ms.locfileid: "49086184"
---
# <a name="ltaddgt-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="82838-102">&lt;Добавление&gt; элемент для connectionManagement (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="82838-102">&lt;add&gt; Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="82838-103">Добавляет IP-адрес или DNS-имя в список управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="82838-103">Adds an IP address or DNS name to the connection management list.</span></span>  
  
 <span data-ttu-id="82838-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="82838-104">\<configuration></span></span>  
<span data-ttu-id="82838-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="82838-105">\<system.net></span></span>  
<span data-ttu-id="82838-106">\<connectionManagement ></span><span class="sxs-lookup"><span data-stu-id="82838-106">\<connectionManagement></span></span>  
<span data-ttu-id="82838-107">\<add></span><span class="sxs-lookup"><span data-stu-id="82838-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82838-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82838-108">Syntax</span></span>  
  
```xml  
<add   
  address="address expression"   
  maxconnection="integer"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82838-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="82838-109">Attributes and Elements</span></span>  
 <span data-ttu-id="82838-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="82838-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82838-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="82838-111">Attributes</span></span>  
  
|<span data-ttu-id="82838-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="82838-112">**Attribute**</span></span>|<span data-ttu-id="82838-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="82838-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="82838-114">Строка, описывающая IP-адрес или DNS-имя.</span><span class="sxs-lookup"><span data-stu-id="82838-114">A string describing an IP address or DNS name.</span></span>|  
|`maxconnection`|<span data-ttu-id="82838-115">Максимальное число разрешенных подключений к серверу.</span><span class="sxs-lookup"><span data-stu-id="82838-115">The maximum number of connections allowed to a server.</span></span> <span data-ttu-id="82838-116">Если значение не предоставлено, используется значение по умолчанию 2.</span><span class="sxs-lookup"><span data-stu-id="82838-116">If not supplied, the default is 2.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="82838-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="82838-117">Child Elements</span></span>  
 <span data-ttu-id="82838-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="82838-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="82838-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="82838-119">Parent Elements</span></span>  
  
|<span data-ttu-id="82838-120">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="82838-120">**Element**</span></span>|<span data-ttu-id="82838-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="82838-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="82838-122">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="82838-122">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="82838-123">Задает максимальное число подключений к сетевому узлу.</span><span class="sxs-lookup"><span data-stu-id="82838-123">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82838-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="82838-124">Remarks</span></span>  
 <span data-ttu-id="82838-125">В качестве значения атрибута `address` должна быть задана либо звездочка, указывающая все подключения, либо строка в форме `<schema>://<idn_hostname>[:<port>]`.</span><span class="sxs-lookup"><span data-stu-id="82838-125">The value of the `address` attribute should be either an asterisk to indicate all connections, or a string of the form `<schema>://<idn_hostname>[:<port>]`.</span></span>  
  
 <span data-ttu-id="82838-126">Если URI, переданный в какие-либо API HTTP, содержит символы Юникода, то имя будет преобразовано внутренним образом с помощью свойства <xref:System.Uri.DnsSafeHost%2A>, которое может возвращать строку Punycode (поведение, зависящее от текущей конфигурации IDN).</span><span class="sxs-lookup"><span data-stu-id="82838-126">If the URI passed to any HTTP APIs contains Unicode, the name will be converted internally using <xref:System.Uri.DnsSafeHost%2A> which might return a punicode string (behavior dependent on the current IDN configuration).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="82838-127">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="82838-127">Configuration Files</span></span>  
 <span data-ttu-id="82838-128">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="82838-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="82838-129">Пример</span><span class="sxs-lookup"><span data-stu-id="82838-129">Example</span></span>  
 <span data-ttu-id="82838-130">Следующий пример настраивает приложение для использования четырех подключений к серверу www.contoso.com и двух подключений ко всем остальным серверам.</span><span class="sxs-lookup"><span data-stu-id="82838-130">The following example configures an application to use four connections to the server www.contoso.com and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="82838-131">См. также</span><span class="sxs-lookup"><span data-stu-id="82838-131">See Also</span></span>  
 <xref:System.Net.ServicePoint>  
 <xref:System.Net.ServicePointManager>  
 [<span data-ttu-id="82838-132">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="82838-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
