---
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 91eafa46aa73b5e6d359fcbe48f098f9f8a4d0f0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61644320"
---
# <a name="exposedmethod"></a><span data-ttu-id="ae3a7-101">\<exposedMethod ></span><span class="sxs-lookup"><span data-stu-id="ae3a7-101">\<exposedMethod></span></span>
<span data-ttu-id="ae3a7-102">Представляет метод COM+, предоставляемый, когда интерфейс компонента COM+ предоставляется как веб-служба.</span><span class="sxs-lookup"><span data-stu-id="ae3a7-102">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
 <span data-ttu-id="ae3a7-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ae3a7-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="ae3a7-104">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="ae3a7-104">\<comContracts></span></span>  
<span data-ttu-id="ae3a7-105">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="ae3a7-105">\<comContract></span></span>  
<span data-ttu-id="ae3a7-106">\<методы ></span><span class="sxs-lookup"><span data-stu-id="ae3a7-106">\<methods></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae3a7-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ae3a7-107">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae3a7-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ae3a7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ae3a7-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ae3a7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae3a7-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ae3a7-110">Attributes</span></span>  
  
|<span data-ttu-id="ae3a7-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ae3a7-111">Attribute</span></span>|<span data-ttu-id="ae3a7-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ae3a7-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ae3a7-113">имя</span><span class="sxs-lookup"><span data-stu-id="ae3a7-113">name</span></span>|<span data-ttu-id="ae3a7-114">Строка, которая содержит метод COM+, предоставляемый, когда интерфейс компонента COM+ предоставляется как веб-служба.</span><span class="sxs-lookup"><span data-stu-id="ae3a7-114">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ae3a7-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ae3a7-115">Child Elements</span></span>  
 <span data-ttu-id="ae3a7-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ae3a7-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ae3a7-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ae3a7-117">Parent Elements</span></span>  
  
|<span data-ttu-id="ae3a7-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="ae3a7-118">Element</span></span>|<span data-ttu-id="ae3a7-119">Описание</span><span class="sxs-lookup"><span data-stu-id="ae3a7-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae3a7-120">\<exposedMethods ></span><span class="sxs-lookup"><span data-stu-id="ae3a7-120">\<exposedMethods></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethods.md)|<span data-ttu-id="ae3a7-121">Коллекция [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="ae3a7-121">A collection of [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae3a7-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="ae3a7-122">Remarks</span></span>  
 <span data-ttu-id="ae3a7-123">Средство конфигурации интеграции COM+ (ComSvcConfig.exe) может применяться для добавления определенных методов COM-интерфейса для использования в созданном контракте службы.</span><span class="sxs-lookup"><span data-stu-id="ae3a7-123">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="ae3a7-124">Например, для добавления в созданный контракт службы трех именованных методов из COM-интерфейса `IFinances` компонента `ItemOrders`.Financial можно использовать приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="ae3a7-124">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="ae3a7-125">При запуске ComSvcConfig.exe также создается следующий контракт службы, в котором указанные выше методы как [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="ae3a7-125">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 <span data-ttu-id="ae3a7-126">Во время инициализации службы среда выполнения пытается создать контракт службы, отображая и добавляя только те методы, которые включены в список [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="ae3a7-126">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span> <span data-ttu-id="ae3a7-127">Для каждого метода интерфейса, который не включен в контракт службы, создается трассировка.</span><span class="sxs-lookup"><span data-stu-id="ae3a7-127">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae3a7-128">См. также</span><span class="sxs-lookup"><span data-stu-id="ae3a7-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [<span data-ttu-id="ae3a7-129">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="ae3a7-129">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="ae3a7-130">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="ae3a7-130">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="ae3a7-131">Практическое руководство. Настройка параметров службы COM +</span><span class="sxs-lookup"><span data-stu-id="ae3a7-131">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
