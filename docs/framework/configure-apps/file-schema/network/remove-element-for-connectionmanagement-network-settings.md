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
ms.openlocfilehash: 287e36dce65be7a002499d2cd22481018a1f4742
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089169"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="04b97-102">\<удалить элемент > для элемент connectionManagement (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="04b97-102">\<remove> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="04b97-103">Удаляет IP-адрес или DNS-имя из списка управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="04b97-103">Removes an IP address or DNS name from the connection management list.</span></span>  

<span data-ttu-id="04b97-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="04b97-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="04b97-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="04b97-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="04b97-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<элемент connectionmanagement >** ](connectionmanagement-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="04b97-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)</span></span>\
<span data-ttu-id="04b97-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<удалить >**</span><span class="sxs-lookup"><span data-stu-id="04b97-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="04b97-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04b97-108">Syntax</span></span>  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04b97-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="04b97-109">Attributes and Elements</span></span>  
 <span data-ttu-id="04b97-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="04b97-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04b97-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="04b97-111">Attributes</span></span>  
  
|<span data-ttu-id="04b97-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="04b97-112">**Attribute**</span></span>|<span data-ttu-id="04b97-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="04b97-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="04b97-114">IP-адрес или имя DNS.</span><span class="sxs-lookup"><span data-stu-id="04b97-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="04b97-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="04b97-115">Child Elements</span></span>  
 <span data-ttu-id="04b97-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="04b97-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="04b97-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="04b97-117">Parent Elements</span></span>  
  
|<span data-ttu-id="04b97-118">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="04b97-118">**Element**</span></span>|<span data-ttu-id="04b97-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="04b97-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="04b97-120">Элемент connectionManagement</span><span class="sxs-lookup"><span data-stu-id="04b97-120">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="04b97-121">Задает максимальное число подключений к сетевому узлу.</span><span class="sxs-lookup"><span data-stu-id="04b97-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04b97-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="04b97-122">Remarks</span></span>  
 <span data-ttu-id="04b97-123">Элемент `remove` удаляет запись списка управления подключениями для указанного сервера.</span><span class="sxs-lookup"><span data-stu-id="04b97-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="04b97-124">Значение атрибута `address` должно быть допустимым IP-адресом или именем узла.</span><span class="sxs-lookup"><span data-stu-id="04b97-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="04b97-125">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="04b97-125">Configuration Files</span></span>  
 <span data-ttu-id="04b97-126">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="04b97-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="04b97-127">Пример</span><span class="sxs-lookup"><span data-stu-id="04b97-127">Example</span></span>  
 <span data-ttu-id="04b97-128">В следующем примере удаляются все записи списка управления подключениями для сервера `www.adventure-works.com` а затем настраивается использование четырех подключений к серверу `www.contoso.com` и двух подключений ко всем остальным серверам.</span><span class="sxs-lookup"><span data-stu-id="04b97-128">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="04b97-129">См. также</span><span class="sxs-lookup"><span data-stu-id="04b97-129">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="04b97-130">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="04b97-130">Network Settings Schema</span></span>](index.md)
