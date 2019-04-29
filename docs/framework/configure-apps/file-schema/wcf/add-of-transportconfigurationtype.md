---
title: <add> из <transportConfigurationType>
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: c71a58b13e89bedb5eed24d784c82fb1525f7625
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701441"
---
# <a name="add-of-transportconfigurationtype"></a><span data-ttu-id="68ac2-102">\<Добавить > из \<transportConfigurationType ></span><span class="sxs-lookup"><span data-stu-id="68ac2-102">\<add> of \<transportConfigurationType></span></span>
<span data-ttu-id="68ac2-103">Данный элемент представляет собой пару ключ/значение, которая идентифицирует тип конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="68ac2-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
 <span data-ttu-id="68ac2-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="68ac2-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="68ac2-105">\<ServiceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="68ac2-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="68ac2-106">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="68ac2-106">\<transportConfigurationTypes></span></span>  
<span data-ttu-id="68ac2-107">\<add></span><span class="sxs-lookup"><span data-stu-id="68ac2-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68ac2-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="68ac2-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="68ac2-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="68ac2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="68ac2-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="68ac2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="68ac2-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="68ac2-111">Attributes</span></span>  
  
|<span data-ttu-id="68ac2-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="68ac2-112">Attribute</span></span>|<span data-ttu-id="68ac2-113">Описание</span><span class="sxs-lookup"><span data-stu-id="68ac2-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="68ac2-114">имя</span><span class="sxs-lookup"><span data-stu-id="68ac2-114">name</span></span>|<span data-ttu-id="68ac2-115">Обязательный строковый атрибут.</span><span class="sxs-lookup"><span data-stu-id="68ac2-115">Required String attribute.</span></span><br /><br /> <span data-ttu-id="68ac2-116">Содержит ключ, определяемый пользователем, который является уникальным идентификатором типа транспорта.</span><span class="sxs-lookup"><span data-stu-id="68ac2-116">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="68ac2-117">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="68ac2-117">transportConfigurationType</span></span>|<span data-ttu-id="68ac2-118">Строка, содержащая тип, реализующий конкретный транспорт.</span><span class="sxs-lookup"><span data-stu-id="68ac2-118">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="68ac2-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="68ac2-119">Child Elements</span></span>  
 <span data-ttu-id="68ac2-120">Нет</span><span class="sxs-lookup"><span data-stu-id="68ac2-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="68ac2-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="68ac2-121">Parent Elements</span></span>  
  
|<span data-ttu-id="68ac2-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="68ac2-122">Element</span></span>|<span data-ttu-id="68ac2-123">Описание</span><span class="sxs-lookup"><span data-stu-id="68ac2-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68ac2-124">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="68ac2-124">\<transportConfigurationTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|<span data-ttu-id="68ac2-125">Коллекция типов, реализующих конкретный транспорт.</span><span class="sxs-lookup"><span data-stu-id="68ac2-125">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="68ac2-126">Пример</span><span class="sxs-lookup"><span data-stu-id="68ac2-126">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="68ac2-127">См. также</span><span class="sxs-lookup"><span data-stu-id="68ac2-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="68ac2-128">Размещение</span><span class="sxs-lookup"><span data-stu-id="68ac2-128">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
