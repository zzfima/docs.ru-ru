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
ms.openlocfilehash: 17b380b12977423669fd413132d69a3082daca41
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698359"
---
# <a name="clear-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="a8d43-102">Элемент > @no__t 0clear для элемент connectionManagement (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="a8d43-102">\<clear> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="a8d43-103">Очищает список управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="a8d43-103">Clears the connection management list.</span></span>  
  
[<span data-ttu-id="a8d43-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="a8d43-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="a8d43-105">&nbsp; @ no__t-1[ **@no__t -4system. NET >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="a8d43-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="a8d43-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<connectionManagement >** ](connectionmanagement-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="a8d43-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)</span></span>  
<span data-ttu-id="a8d43-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="a8d43-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8d43-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8d43-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8d43-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a8d43-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a8d43-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a8d43-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8d43-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a8d43-111">Attributes</span></span>  
 <span data-ttu-id="a8d43-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="a8d43-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a8d43-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a8d43-113">Child Elements</span></span>  
 <span data-ttu-id="a8d43-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="a8d43-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a8d43-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a8d43-115">Parent Elements</span></span>  
  
|<span data-ttu-id="a8d43-116">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="a8d43-116">**Element**</span></span>|<span data-ttu-id="a8d43-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a8d43-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a8d43-118">Элемент connectionManagement</span><span class="sxs-lookup"><span data-stu-id="a8d43-118">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="a8d43-119">Задает максимальное число подключений к сетевому узлу.</span><span class="sxs-lookup"><span data-stu-id="a8d43-119">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8d43-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="a8d43-120">Remarks</span></span>  
 <span data-ttu-id="a8d43-121">Элемент `clear` удаляет все записи из списка управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="a8d43-121">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a8d43-122">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="a8d43-122">Configuration Files</span></span>  
 <span data-ttu-id="a8d43-123">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="a8d43-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8d43-124">Пример</span><span class="sxs-lookup"><span data-stu-id="a8d43-124">Example</span></span>  
 <span data-ttu-id="a8d43-125">В следующем примере очищается список управления подключениями, а затем добавляются новые записи управления подключениями для сервера `www.contoso.com` и всех остальных сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="a8d43-125">The following example clears the connection management list and then adds new connection management entries for the server `www.contoso.com` and all other network hosts.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a8d43-126">См. также</span><span class="sxs-lookup"><span data-stu-id="a8d43-126">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="a8d43-127">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="a8d43-127">Network Settings Schema</span></span>](index.md)
