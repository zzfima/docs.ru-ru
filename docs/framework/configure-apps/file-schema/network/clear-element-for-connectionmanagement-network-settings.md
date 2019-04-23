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
ms.openlocfilehash: 733c70b0575de7e2635afaab58ad48591f035fc0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59124999"
---
# <a name="clear-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="6bcaa-102">\<Очистить > элемент для connectionManagement (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="6bcaa-102">\<clear> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="6bcaa-103">Очищает список управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="6bcaa-103">Clears the connection management list.</span></span>  
  
 <span data-ttu-id="6bcaa-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6bcaa-104">\<configuration></span></span>  
<span data-ttu-id="6bcaa-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="6bcaa-105">\<system.net></span></span>  
<span data-ttu-id="6bcaa-106">\<connectionManagement ></span><span class="sxs-lookup"><span data-stu-id="6bcaa-106">\<connectionManagement></span></span>  
<span data-ttu-id="6bcaa-107">\<Очистить ></span><span class="sxs-lookup"><span data-stu-id="6bcaa-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bcaa-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6bcaa-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6bcaa-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6bcaa-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6bcaa-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6bcaa-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6bcaa-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6bcaa-111">Attributes</span></span>  
 <span data-ttu-id="6bcaa-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6bcaa-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6bcaa-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6bcaa-113">Child Elements</span></span>  
 <span data-ttu-id="6bcaa-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6bcaa-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6bcaa-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6bcaa-115">Parent Elements</span></span>  
  
|<span data-ttu-id="6bcaa-116">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="6bcaa-116">**Element**</span></span>|<span data-ttu-id="6bcaa-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6bcaa-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="6bcaa-118">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="6bcaa-118">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="6bcaa-119">Задает максимальное число подключений к сетевому узлу.</span><span class="sxs-lookup"><span data-stu-id="6bcaa-119">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6bcaa-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="6bcaa-120">Remarks</span></span>  
 <span data-ttu-id="6bcaa-121">`clear` Элемент удаляет все записи из списка управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="6bcaa-121">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="6bcaa-122">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="6bcaa-122">Configuration Files</span></span>  
 <span data-ttu-id="6bcaa-123">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="6bcaa-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6bcaa-124">Пример</span><span class="sxs-lookup"><span data-stu-id="6bcaa-124">Example</span></span>  
 <span data-ttu-id="6bcaa-125">Следующий пример очищает список управления подключениями и добавляет новые записи управления подключением для сервера `www.contoso.com` и всем другим узлам сети.</span><span class="sxs-lookup"><span data-stu-id="6bcaa-125">The following example clears the connection management list and then adds new connection management entries for the server `www.contoso.com` and all other network hosts.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6bcaa-126">См. также</span><span class="sxs-lookup"><span data-stu-id="6bcaa-126">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="6bcaa-127">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="6bcaa-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
