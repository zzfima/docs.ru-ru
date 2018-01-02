---
title: "&lt;Очистить&gt; элемент для connectionManagement (параметры сети)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, connectionManagement
- connectionManagement, clear element
- clear element, connectionManagement
- <connectionManagement>, clear element
ms.assetid: fb259282-84c4-4dc4-a226-78d904a6edc3
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 97eab03079ac7881e69ba69d324287d287eb4ecf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltcleargt-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="72ba9-102">&lt;Очистить&gt; элемент для connectionManagement (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="72ba9-102">&lt;clear&gt; Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="72ba9-103">Очищает список управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="72ba9-103">Clears the connection management list.</span></span>  
  
 <span data-ttu-id="72ba9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="72ba9-104">\<configuration></span></span>  
<span data-ttu-id="72ba9-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="72ba9-105">\<system.net></span></span>  
<span data-ttu-id="72ba9-106">\<connectionManagement ></span><span class="sxs-lookup"><span data-stu-id="72ba9-106">\<connectionManagement></span></span>  
<span data-ttu-id="72ba9-107">\<Очистить ></span><span class="sxs-lookup"><span data-stu-id="72ba9-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72ba9-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72ba9-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72ba9-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="72ba9-109">Attributes and Elements</span></span>  
 <span data-ttu-id="72ba9-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="72ba9-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72ba9-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="72ba9-111">Attributes</span></span>  
 <span data-ttu-id="72ba9-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="72ba9-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="72ba9-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="72ba9-113">Child Elements</span></span>  
 <span data-ttu-id="72ba9-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="72ba9-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="72ba9-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="72ba9-115">Parent Elements</span></span>  
  
|<span data-ttu-id="72ba9-116">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="72ba9-116">**Element**</span></span>|<span data-ttu-id="72ba9-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="72ba9-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="72ba9-118">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="72ba9-118">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="72ba9-119">Задает максимальное число подключений к сетевому узлу.</span><span class="sxs-lookup"><span data-stu-id="72ba9-119">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72ba9-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="72ba9-120">Remarks</span></span>  
 <span data-ttu-id="72ba9-121">`clear` Элемент удаляет все записи из списка управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="72ba9-121">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="72ba9-122">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="72ba9-122">Configuration Files</span></span>  
 <span data-ttu-id="72ba9-123">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="72ba9-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="72ba9-124">Пример</span><span class="sxs-lookup"><span data-stu-id="72ba9-124">Example</span></span>  
 <span data-ttu-id="72ba9-125">В следующем примере очищает список управления подключениями и затем добавляет новые записи управления подключением к серверу www.contoso.com и всем другим сетевым узлам.</span><span class="sxs-lookup"><span data-stu-id="72ba9-125">The following example clears the connection management list and then adds new connection management entries for the server www.contoso.com and all other network hosts.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <clear/>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="72ba9-126">См. также</span><span class="sxs-lookup"><span data-stu-id="72ba9-126">See Also</span></span>  
 <xref:System.Net.ServicePoint>  
 <xref:System.Net.ServicePointManager>  
 [<span data-ttu-id="72ba9-127">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="72ba9-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
