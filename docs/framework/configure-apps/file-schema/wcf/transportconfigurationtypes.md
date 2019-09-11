---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: 4be08f780c1095b0016bd130b5719a2a7307d019
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854924"
---
# <a name="transportconfigurationtypes"></a><span data-ttu-id="6320a-101">\<Транспортконфигуратионтипес ></span><span class="sxs-lookup"><span data-stu-id="6320a-101">\<transportConfigurationTypes></span></span>
<span data-ttu-id="6320a-102">Представляет коллекцию элементов конфигурации, которые определяют тип конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="6320a-102">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="6320a-103">Может использоваться для добавления пользовательских протоколов WAS.</span><span class="sxs-lookup"><span data-stu-id="6320a-103">This can be used to add custom WAS protocols.</span></span>  
  
<span data-ttu-id="6320a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6320a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6320a-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="6320a-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6320a-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceHostingEnvironment >** ](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="6320a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="6320a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Транспортконфигуратионтипес >**</span><span class="sxs-lookup"><span data-stu-id="6320a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transportConfigurationTypes>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6320a-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6320a-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6320a-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6320a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6320a-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6320a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6320a-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6320a-111">Attributes</span></span>  
  
|<span data-ttu-id="6320a-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6320a-112">Attribute</span></span>|<span data-ttu-id="6320a-113">Описание</span><span class="sxs-lookup"><span data-stu-id="6320a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6320a-114">имя</span><span class="sxs-lookup"><span data-stu-id="6320a-114">name</span></span>|<span data-ttu-id="6320a-115">Имя транспорта</span><span class="sxs-lookup"><span data-stu-id="6320a-115">The name of the transport</span></span>|  
|<span data-ttu-id="6320a-116">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="6320a-116">transportConfigurationType</span></span>|<span data-ttu-id="6320a-117">Тип, реализующий транспорт</span><span class="sxs-lookup"><span data-stu-id="6320a-117">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6320a-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6320a-118">Child Elements</span></span>  
  
|<span data-ttu-id="6320a-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="6320a-119">Element</span></span>|<span data-ttu-id="6320a-120">Описание</span><span class="sxs-lookup"><span data-stu-id="6320a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6320a-121">\<add></span><span class="sxs-lookup"><span data-stu-id="6320a-121">\<add></span></span>](add-of-transportconfigurationtype.md)|<span data-ttu-id="6320a-122">Добавляет элемент конфигурации, который определяет тип конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="6320a-122">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6320a-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6320a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="6320a-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="6320a-124">Element</span></span>|<span data-ttu-id="6320a-125">Описание</span><span class="sxs-lookup"><span data-stu-id="6320a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6320a-126">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="6320a-126">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="6320a-127">Определяет, какой тип среда размещения служб создает для конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="6320a-127">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6320a-128">См. также</span><span class="sxs-lookup"><span data-stu-id="6320a-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="6320a-129">Размещение</span><span class="sxs-lookup"><span data-stu-id="6320a-129">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
