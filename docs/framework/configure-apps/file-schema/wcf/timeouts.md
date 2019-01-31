---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: 8a8a352380fe6eedb41ead089405e7b79fad29fe
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55272787"
---
# <a name="timeouts"></a><span data-ttu-id="8fb98-101">\<время ожидания ></span><span class="sxs-lookup"><span data-stu-id="8fb98-101">\<timeOuts></span></span>
<span data-ttu-id="8fb98-102">Элемент конфигурации, который задает допустимый интервал времени для открытия или закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="8fb98-102">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="8fb98-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8fb98-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="8fb98-104">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="8fb98-104">\<client></span></span>  
<span data-ttu-id="8fb98-105">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="8fb98-105">\<endpoint></span></span>  
<span data-ttu-id="8fb98-106">\<узел ></span><span class="sxs-lookup"><span data-stu-id="8fb98-106">\<host></span></span>  
<span data-ttu-id="8fb98-107">\<время ожидания ></span><span class="sxs-lookup"><span data-stu-id="8fb98-107">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fb98-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8fb98-108">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8fb98-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8fb98-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8fb98-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8fb98-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8fb98-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8fb98-111">Attributes</span></span>  
  
|<span data-ttu-id="8fb98-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8fb98-112">Attribute</span></span>|<span data-ttu-id="8fb98-113">Описание</span><span class="sxs-lookup"><span data-stu-id="8fb98-113">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="8fb98-114">Значение <xref:System.TimeSpan>, которое задает временной интервал, выделенный для операции закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="8fb98-114">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="8fb98-115">Значение <xref:System.TimeSpan>, которое задает временной интервал, выделенный для операции открытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="8fb98-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8fb98-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8fb98-116">Child Elements</span></span>  
 <span data-ttu-id="8fb98-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8fb98-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8fb98-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8fb98-118">Parent Elements</span></span>  
  
|<span data-ttu-id="8fb98-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="8fb98-119">Element</span></span>|<span data-ttu-id="8fb98-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="8fb98-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8fb98-121">\<узел ></span><span class="sxs-lookup"><span data-stu-id="8fb98-121">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="8fb98-122">Элемент конфигурации, который задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="8fb98-122">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8fb98-123">См. также</span><span class="sxs-lookup"><span data-stu-id="8fb98-123">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="8fb98-124">Размещение</span><span class="sxs-lookup"><span data-stu-id="8fb98-124">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
