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
ms.openlocfilehash: 86a7a0ab402c8c40ec3b824402a1dba984412b68
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659446"
---
# <a name="clear-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="ba432-102">\<Очистка элемента > для элемент connectionManagement (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="ba432-102">\<clear> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="ba432-103">Очищает список управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="ba432-103">Clears the connection management list.</span></span>  
  
 <span data-ttu-id="ba432-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ba432-104">\<configuration></span></span>  
<span data-ttu-id="ba432-105">\<> System. NET</span><span class="sxs-lookup"><span data-stu-id="ba432-105">\<system.net></span></span>  
<span data-ttu-id="ba432-106">\<Элемент connectionManagement ></span><span class="sxs-lookup"><span data-stu-id="ba432-106">\<connectionManagement></span></span>  
<span data-ttu-id="ba432-107">\<очистить ></span><span class="sxs-lookup"><span data-stu-id="ba432-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba432-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba432-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba432-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ba432-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ba432-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ba432-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba432-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ba432-111">Attributes</span></span>  
 <span data-ttu-id="ba432-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="ba432-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ba432-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ba432-113">Child Elements</span></span>  
 <span data-ttu-id="ba432-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="ba432-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ba432-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ba432-115">Parent Elements</span></span>  
  
|<span data-ttu-id="ba432-116">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="ba432-116">**Element**</span></span>|<span data-ttu-id="ba432-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ba432-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ba432-118">Элемент connectionManagement</span><span class="sxs-lookup"><span data-stu-id="ba432-118">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="ba432-119">Задает максимальное число подключений к сетевому узлу.</span><span class="sxs-lookup"><span data-stu-id="ba432-119">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba432-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="ba432-120">Remarks</span></span>  
 <span data-ttu-id="ba432-121">`clear` Элемент удаляет все записи из списка управления подключениями.</span><span class="sxs-lookup"><span data-stu-id="ba432-121">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ba432-122">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="ba432-122">Configuration Files</span></span>  
 <span data-ttu-id="ba432-123">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="ba432-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba432-124">Пример</span><span class="sxs-lookup"><span data-stu-id="ba432-124">Example</span></span>  
 <span data-ttu-id="ba432-125">В следующем примере очищается список управления подключениями, а затем добавляются новые записи управления подключениями `www.contoso.com` для сервера и всех остальных сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="ba432-125">The following example clears the connection management list and then adds new connection management entries for the server `www.contoso.com` and all other network hosts.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ba432-126">См. также</span><span class="sxs-lookup"><span data-stu-id="ba432-126">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="ba432-127">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="ba432-127">Network Settings Schema</span></span>](index.md)
