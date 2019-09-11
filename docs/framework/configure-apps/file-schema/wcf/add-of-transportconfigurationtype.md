---
title: <add> из <transportConfigurationType>
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: adf4cd7f02db6535c5950443d09476a9a5ff63fb
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850316"
---
# <a name="add-of-transportconfigurationtype"></a><span data-ttu-id="e0039-102">\<Добавление > \<> транспортконфигуратионтипе</span><span class="sxs-lookup"><span data-stu-id="e0039-102">\<add> of \<transportConfigurationType></span></span>
<span data-ttu-id="e0039-103">Данный элемент представляет собой пару ключ/значение, которая идентифицирует тип конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="e0039-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
<span data-ttu-id="e0039-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e0039-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e0039-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e0039-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e0039-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceHostingEnvironment >** ](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="e0039-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="e0039-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Транспортконфигуратионтипес >** ](transportconfigurationtypes.md)</span><span class="sxs-lookup"><span data-stu-id="e0039-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<transportConfigurationTypes>**](transportconfigurationtypes.md)</span></span>\
<span data-ttu-id="e0039-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Добавить >**</span><span class="sxs-lookup"><span data-stu-id="e0039-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0039-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e0039-109">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0039-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e0039-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e0039-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e0039-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0039-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e0039-112">Attributes</span></span>  
  
|<span data-ttu-id="e0039-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e0039-113">Attribute</span></span>|<span data-ttu-id="e0039-114">Описание</span><span class="sxs-lookup"><span data-stu-id="e0039-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e0039-115">имя</span><span class="sxs-lookup"><span data-stu-id="e0039-115">name</span></span>|<span data-ttu-id="e0039-116">Обязательный строковый атрибут.</span><span class="sxs-lookup"><span data-stu-id="e0039-116">Required String attribute.</span></span><br /><br /> <span data-ttu-id="e0039-117">Содержит ключ, определяемый пользователем, который является уникальным идентификатором типа транспорта.</span><span class="sxs-lookup"><span data-stu-id="e0039-117">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="e0039-118">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="e0039-118">transportConfigurationType</span></span>|<span data-ttu-id="e0039-119">Строка, содержащая тип, реализующий конкретный транспорт.</span><span class="sxs-lookup"><span data-stu-id="e0039-119">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e0039-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e0039-120">Child Elements</span></span>  
 <span data-ttu-id="e0039-121">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="e0039-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e0039-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e0039-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e0039-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="e0039-123">Element</span></span>|<span data-ttu-id="e0039-124">Описание</span><span class="sxs-lookup"><span data-stu-id="e0039-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e0039-125">\<Транспортконфигуратионтипес ></span><span class="sxs-lookup"><span data-stu-id="e0039-125">\<transportConfigurationTypes></span></span>](transportconfigurationtypes.md)|<span data-ttu-id="e0039-126">Коллекция типов, реализующих конкретный транспорт.</span><span class="sxs-lookup"><span data-stu-id="e0039-126">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e0039-127">Пример</span><span class="sxs-lookup"><span data-stu-id="e0039-127">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="e0039-128">См. также</span><span class="sxs-lookup"><span data-stu-id="e0039-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="e0039-129">Размещение</span><span class="sxs-lookup"><span data-stu-id="e0039-129">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
