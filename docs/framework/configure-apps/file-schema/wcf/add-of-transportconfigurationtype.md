---
title: <add> из <transportConfigurationType>
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: 483ede53df13c896b88171910031dbe9793d66dc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920036"
---
# <a name="add-of-transportconfigurationtype"></a><span data-ttu-id="ad72f-102">\<Добавление > \<> транспортконфигуратионтипе</span><span class="sxs-lookup"><span data-stu-id="ad72f-102">\<add> of \<transportConfigurationType></span></span>
<span data-ttu-id="ad72f-103">Данный элемент представляет собой пару ключ/значение, которая идентифицирует тип конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="ad72f-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
 <span data-ttu-id="ad72f-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ad72f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ad72f-105">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="ad72f-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="ad72f-106">\<Транспортконфигуратионтипес ></span><span class="sxs-lookup"><span data-stu-id="ad72f-106">\<transportConfigurationTypes></span></span>  
<span data-ttu-id="ad72f-107">\<add></span><span class="sxs-lookup"><span data-stu-id="ad72f-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad72f-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad72f-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad72f-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ad72f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ad72f-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ad72f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad72f-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ad72f-111">Attributes</span></span>  
  
|<span data-ttu-id="ad72f-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ad72f-112">Attribute</span></span>|<span data-ttu-id="ad72f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="ad72f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ad72f-114">имя</span><span class="sxs-lookup"><span data-stu-id="ad72f-114">name</span></span>|<span data-ttu-id="ad72f-115">Обязательный строковый атрибут.</span><span class="sxs-lookup"><span data-stu-id="ad72f-115">Required String attribute.</span></span><br /><br /> <span data-ttu-id="ad72f-116">Содержит ключ, определяемый пользователем, который является уникальным идентификатором типа транспорта.</span><span class="sxs-lookup"><span data-stu-id="ad72f-116">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="ad72f-117">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="ad72f-117">transportConfigurationType</span></span>|<span data-ttu-id="ad72f-118">Строка, содержащая тип, реализующий конкретный транспорт.</span><span class="sxs-lookup"><span data-stu-id="ad72f-118">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ad72f-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ad72f-119">Child Elements</span></span>  
 <span data-ttu-id="ad72f-120">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="ad72f-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ad72f-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ad72f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ad72f-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="ad72f-122">Element</span></span>|<span data-ttu-id="ad72f-123">Описание</span><span class="sxs-lookup"><span data-stu-id="ad72f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ad72f-124">\<Транспортконфигуратионтипес ></span><span class="sxs-lookup"><span data-stu-id="ad72f-124">\<transportConfigurationTypes></span></span>](transportconfigurationtypes.md)|<span data-ttu-id="ad72f-125">Коллекция типов, реализующих конкретный транспорт.</span><span class="sxs-lookup"><span data-stu-id="ad72f-125">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ad72f-126">Пример</span><span class="sxs-lookup"><span data-stu-id="ad72f-126">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="ad72f-127">См. также</span><span class="sxs-lookup"><span data-stu-id="ad72f-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="ad72f-128">Размещение</span><span class="sxs-lookup"><span data-stu-id="ad72f-128">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
