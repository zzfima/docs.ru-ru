---
title: Элемент <connectionManagement> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement
- http://schemas.microsoft.com/.NetConfiguration/v2.0#connectionManagement
helpviewer_keywords:
- <connectionManagement> element
- connectionManagement element
ms.assetid: bedccaab-12a2-4511-8f67-e961f249aec6
ms.openlocfilehash: b769dd8d3ed0c617d0d8f908e7ef516615da09a7
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088460"
---
# <a name="connectionmanagement-element-network-settings"></a><span data-ttu-id="f7e77-102">Элемент \<элемент connectionManagement > (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="f7e77-102">\<connectionManagement> Element (Network Settings)</span></span>
<span data-ttu-id="f7e77-103">Задает максимальное число подключений к сетевому узлу.</span><span class="sxs-lookup"><span data-stu-id="f7e77-103">Specifies the maximum number of connections to a network host.</span></span>  

<span data-ttu-id="f7e77-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f7e77-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f7e77-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f7e77-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="f7e77-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<элемент connectionmanagement >**</span><span class="sxs-lookup"><span data-stu-id="f7e77-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionManagement>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f7e77-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f7e77-107">Syntax</span></span>  
  
```xml  
<connectionManagement>   
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7e77-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f7e77-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f7e77-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f7e77-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7e77-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f7e77-110">Attributes</span></span>  
 <span data-ttu-id="f7e77-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f7e77-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f7e77-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f7e77-112">Child Elements</span></span>  
  
|<span data-ttu-id="f7e77-113">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="f7e77-113">**Element**</span></span>|<span data-ttu-id="f7e77-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f7e77-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f7e77-115">add</span><span class="sxs-lookup"><span data-stu-id="f7e77-115">add</span></span>](add-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="f7e77-116">Добавляет IP-адрес или DNS-имя в список управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="f7e77-116">Adds an IP address or DNS name to the connection management list.</span></span>|  
|[<span data-ttu-id="f7e77-117">clear</span><span class="sxs-lookup"><span data-stu-id="f7e77-117">clear</span></span>](clear-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="f7e77-118">Очищает список управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="f7e77-118">Clears the connection management list.</span></span>|  
|[<span data-ttu-id="f7e77-119">remove</span><span class="sxs-lookup"><span data-stu-id="f7e77-119">remove</span></span>](remove-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="f7e77-120">Удаляет IP-адрес или DNS-имя из списка управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="f7e77-120">Removes an IP address or DNS name from the connection management list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f7e77-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f7e77-121">Parent Elements</span></span>  
  
|<span data-ttu-id="f7e77-122">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="f7e77-122">**Element**</span></span>|<span data-ttu-id="f7e77-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f7e77-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f7e77-124">system.net</span><span class="sxs-lookup"><span data-stu-id="f7e77-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="f7e77-125">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="f7e77-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7e77-126">Заметки</span><span class="sxs-lookup"><span data-stu-id="f7e77-126">Remarks</span></span>  
 <span data-ttu-id="f7e77-127">Элемент `connectionManagement` определяет максимальное число подключений к серверу или группе серверов.</span><span class="sxs-lookup"><span data-stu-id="f7e77-127">The `connectionManagement` element defines the maximum number of connections to a server or group of servers.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f7e77-128">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="f7e77-128">Configuration Files</span></span>  
 <span data-ttu-id="f7e77-129">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="f7e77-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7e77-130">Пример</span><span class="sxs-lookup"><span data-stu-id="f7e77-130">Example</span></span>  
 <span data-ttu-id="f7e77-131">В следующем примере приложение настраивается для использования четырех подключений к серверу `www.contoso.com` и двух подключений ко всем остальным серверам.</span><span class="sxs-lookup"><span data-stu-id="f7e77-131">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f7e77-132">См. также</span><span class="sxs-lookup"><span data-stu-id="f7e77-132">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="f7e77-133">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="f7e77-133">Network Settings Schema</span></span>](index.md)
