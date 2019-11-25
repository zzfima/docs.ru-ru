---
title: Элемент <clear> для connectionManagement (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, connectionManagement
- connectionManagement, clear element
- clear element, connectionManagement
- <connectionManagement>, clear element
ms.assetid: fb259282-84c4-4dc4-a226-78d904a6edc3
ms.openlocfilehash: a76df48a9de084e1121a5e96b22edf7aa3acba23
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088483"
---
# <a name="clear-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="4db28-102">\<Clear > элемента для элемент connectionManagement (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="4db28-102">\<clear> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="4db28-103">Очищает список управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="4db28-103">Clears the connection management list.</span></span>  

<span data-ttu-id="4db28-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4db28-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4db28-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4db28-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="4db28-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<элемент connectionmanagement >** ](connectionmanagement-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4db28-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)</span></span>\
<span data-ttu-id="4db28-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="4db28-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="4db28-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4db28-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4db28-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4db28-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4db28-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4db28-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4db28-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4db28-111">Attributes</span></span>  
 <span data-ttu-id="4db28-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4db28-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4db28-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4db28-113">Child Elements</span></span>  
 <span data-ttu-id="4db28-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4db28-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4db28-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4db28-115">Parent Elements</span></span>  
  
|<span data-ttu-id="4db28-116">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="4db28-116">**Element**</span></span>|<span data-ttu-id="4db28-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="4db28-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4db28-118">Элемент connectionManagement</span><span class="sxs-lookup"><span data-stu-id="4db28-118">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="4db28-119">Задает максимальное число подключений к сетевому узлу.</span><span class="sxs-lookup"><span data-stu-id="4db28-119">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4db28-120">Заметки</span><span class="sxs-lookup"><span data-stu-id="4db28-120">Remarks</span></span>  
 <span data-ttu-id="4db28-121">Элемент `clear` удаляет все записи из списка управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="4db28-121">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4db28-122">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="4db28-122">Configuration Files</span></span>  
 <span data-ttu-id="4db28-123">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="4db28-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4db28-124">Пример</span><span class="sxs-lookup"><span data-stu-id="4db28-124">Example</span></span>  
 <span data-ttu-id="4db28-125">В следующем примере очищается список управления подключениями, а затем добавляются новые записи управления подключениями для сервера `www.contoso.com` и всех остальных сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="4db28-125">The following example clears the connection management list and then adds new connection management entries for the server `www.contoso.com` and all other network hosts.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4db28-126">См. также</span><span class="sxs-lookup"><span data-stu-id="4db28-126">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="4db28-127">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="4db28-127">Network Settings Schema</span></span>](index.md)
