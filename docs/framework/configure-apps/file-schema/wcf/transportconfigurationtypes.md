---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: b3683a198ec403fb9966bb902c936108fd043bfa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083651"
---
# <a name="transportconfigurationtypes"></a><span data-ttu-id="058b8-101">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="058b8-101">\<transportConfigurationTypes></span></span>
<span data-ttu-id="058b8-102">Представляет коллекцию элементов конфигурации, которые определяют тип конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="058b8-102">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="058b8-103">Может использоваться для добавления пользовательских протоколов WAS.</span><span class="sxs-lookup"><span data-stu-id="058b8-103">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="058b8-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="058b8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="058b8-105">\<ServiceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="058b8-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="058b8-106">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="058b8-106">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="058b8-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="058b8-107">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="058b8-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="058b8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="058b8-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="058b8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="058b8-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="058b8-110">Attributes</span></span>  
  
|<span data-ttu-id="058b8-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="058b8-111">Attribute</span></span>|<span data-ttu-id="058b8-112">Описание</span><span class="sxs-lookup"><span data-stu-id="058b8-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="058b8-113">имя</span><span class="sxs-lookup"><span data-stu-id="058b8-113">name</span></span>|<span data-ttu-id="058b8-114">Имя транспорта</span><span class="sxs-lookup"><span data-stu-id="058b8-114">The name of the transport</span></span>|  
|<span data-ttu-id="058b8-115">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="058b8-115">transportConfigurationType</span></span>|<span data-ttu-id="058b8-116">Тип, реализующий транспорт</span><span class="sxs-lookup"><span data-stu-id="058b8-116">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="058b8-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="058b8-117">Child Elements</span></span>  
  
|<span data-ttu-id="058b8-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="058b8-118">Element</span></span>|<span data-ttu-id="058b8-119">Описание</span><span class="sxs-lookup"><span data-stu-id="058b8-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="058b8-120">\<add></span><span class="sxs-lookup"><span data-stu-id="058b8-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|<span data-ttu-id="058b8-121">Добавляет элемент конфигурации, который определяет тип конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="058b8-121">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="058b8-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="058b8-122">Parent Elements</span></span>  
  
|<span data-ttu-id="058b8-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="058b8-123">Element</span></span>|<span data-ttu-id="058b8-124">Описание</span><span class="sxs-lookup"><span data-stu-id="058b8-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="058b8-125">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="058b8-125">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="058b8-126">Определяет, какой тип среда размещения служб создает для конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="058b8-126">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="058b8-127">См. также</span><span class="sxs-lookup"><span data-stu-id="058b8-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="058b8-128">Размещение</span><span class="sxs-lookup"><span data-stu-id="058b8-128">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
