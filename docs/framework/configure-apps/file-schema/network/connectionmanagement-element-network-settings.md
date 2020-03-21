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
ms.openlocfilehash: 9f1e382bbbaad2cb95e2c33bbbdfb4c505378c9e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154898"
---
# <a name="connectionmanagement-element-network-settings"></a><span data-ttu-id="1f54b-102">\<Элемент connectionManagement> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="1f54b-102">\<connectionManagement> Element (Network Settings)</span></span>
<span data-ttu-id="1f54b-103">Задает максимальное число подключений к сетевому узлу.</span><span class="sxs-lookup"><span data-stu-id="1f54b-103">Specifies the maximum number of connections to a network host.</span></span>  

<span data-ttu-id="1f54b-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1f54b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1f54b-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="1f54b-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="1f54b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<подключениеУправление>**</span><span class="sxs-lookup"><span data-stu-id="1f54b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionManagement>**</span></span>

## <a name="syntax"></a><span data-ttu-id="1f54b-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1f54b-107">Syntax</span></span>  
  
```xml  
<connectionManagement>
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1f54b-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1f54b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1f54b-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1f54b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1f54b-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1f54b-110">Attributes</span></span>  
 <span data-ttu-id="1f54b-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="1f54b-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1f54b-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1f54b-112">Child Elements</span></span>  
  
|<span data-ttu-id="1f54b-113">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="1f54b-113">**Element**</span></span>|<span data-ttu-id="1f54b-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="1f54b-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1f54b-115">добавление</span><span class="sxs-lookup"><span data-stu-id="1f54b-115">add</span></span>](add-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="1f54b-116">Добавляет IP-адрес или DNS-имя в список управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="1f54b-116">Adds an IP address or DNS name to the connection management list.</span></span>|  
|[<span data-ttu-id="1f54b-117">Ясно</span><span class="sxs-lookup"><span data-stu-id="1f54b-117">clear</span></span>](clear-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="1f54b-118">Очищает список управления подключением.</span><span class="sxs-lookup"><span data-stu-id="1f54b-118">Clears the connection management list.</span></span>|  
|[<span data-ttu-id="1f54b-119">удаление</span><span class="sxs-lookup"><span data-stu-id="1f54b-119">remove</span></span>](remove-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="1f54b-120">Удаляет IP-адрес или имя DNS из списка управления подключением.</span><span class="sxs-lookup"><span data-stu-id="1f54b-120">Removes an IP address or DNS name from the connection management list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1f54b-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1f54b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="1f54b-122">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="1f54b-122">**Element**</span></span>|<span data-ttu-id="1f54b-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="1f54b-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1f54b-124">system.net</span><span class="sxs-lookup"><span data-stu-id="1f54b-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="1f54b-125">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="1f54b-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f54b-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="1f54b-126">Remarks</span></span>  
 <span data-ttu-id="1f54b-127">Элемент `connectionManagement` определяет максимальное количество подключений к серверу или группе серверов.</span><span class="sxs-lookup"><span data-stu-id="1f54b-127">The `connectionManagement` element defines the maximum number of connections to a server or group of servers.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="1f54b-128">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="1f54b-128">Configuration Files</span></span>  
 <span data-ttu-id="1f54b-129">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="1f54b-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f54b-130">Пример</span><span class="sxs-lookup"><span data-stu-id="1f54b-130">Example</span></span>  
 <span data-ttu-id="1f54b-131">Следующий пример настраивает приложение на использование `www.contoso.com` четырех подключений к серверу и двух подключений ко всем другим серверам.</span><span class="sxs-lookup"><span data-stu-id="1f54b-131">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1f54b-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1f54b-132">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="1f54b-133">Схема настройки сети</span><span class="sxs-lookup"><span data-stu-id="1f54b-133">Network Settings Schema</span></span>](index.md)
