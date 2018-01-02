---
title: '&lt;exposedMethod&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e9e5c9f61d67850d249d54ed5adfc08bf40bad47
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltexposedmethodgt"></a><span data-ttu-id="10a2f-102">&lt;exposedMethod&gt;</span><span class="sxs-lookup"><span data-stu-id="10a2f-102">&lt;exposedMethod&gt;</span></span>
<span data-ttu-id="10a2f-103">Представляет метод COM+, предоставляемый, когда интерфейс компонента COM+ предоставляется как веб-служба.</span><span class="sxs-lookup"><span data-stu-id="10a2f-103">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
 <span data-ttu-id="10a2f-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="10a2f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="10a2f-105">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="10a2f-105">\<comContracts></span></span>  
<span data-ttu-id="10a2f-106">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="10a2f-106">\<comContract></span></span>  
<span data-ttu-id="10a2f-107">\<методы ></span><span class="sxs-lookup"><span data-stu-id="10a2f-107">\<methods></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10a2f-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10a2f-108">Syntax</span></span>  
  
```xml  
<comContracts>  
  <comContract>  
      <exposedMethods>  
         <exposedMethod name="string" />  
      </exposedMethods>  
  </comContract>  
</comContracts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10a2f-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="10a2f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="10a2f-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="10a2f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10a2f-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="10a2f-111">Attributes</span></span>  
  
|<span data-ttu-id="10a2f-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="10a2f-112">Attribute</span></span>|<span data-ttu-id="10a2f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="10a2f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="10a2f-114">имя</span><span class="sxs-lookup"><span data-stu-id="10a2f-114">name</span></span>|<span data-ttu-id="10a2f-115">Строка, которая содержит метод COM+, предоставляемый, когда интерфейс компонента COM+ предоставляется как веб-служба.</span><span class="sxs-lookup"><span data-stu-id="10a2f-115">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="10a2f-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="10a2f-116">Child Elements</span></span>  
 <span data-ttu-id="10a2f-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="10a2f-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="10a2f-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="10a2f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="10a2f-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="10a2f-119">Element</span></span>|<span data-ttu-id="10a2f-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="10a2f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="10a2f-121">\<exposedMethods ></span><span class="sxs-lookup"><span data-stu-id="10a2f-121">\<exposedMethods></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethods.md)|<span data-ttu-id="10a2f-122">Коллекция [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="10a2f-122">A collection of [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10a2f-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="10a2f-123">Remarks</span></span>  
 <span data-ttu-id="10a2f-124">Средство конфигурации интеграции COM+ (ComSvcConfig.exe) может применяться для добавления определенных методов COM-интерфейса для использования в созданном контракте службы.</span><span class="sxs-lookup"><span data-stu-id="10a2f-124">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="10a2f-125">Например, для добавления в созданный контракт службы трех именованных методов из COM-интерфейса `IFinances` компонента `ItemOrders`.Financial можно использовать приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="10a2f-125">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="10a2f-126">При выполнении ComSvcConfig.exe, оно создает следующий контракт службы, указанные выше методы перечисляются как перечисление [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="10a2f-126">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}" name="IFinances" namespace="http://contoso.com/services/financial">  
    <exposedMethod name="TransferFunds"/>  
    <exposedMethod name="AddFunds"/>  
    <exposedMethod name="RemoveFunds"/>  
</comContract>  
```  
  
 <span data-ttu-id="10a2f-127">Во время инициализации службы среда выполнения пытается создать контракт службы, отображая и добавляя только те методы, которые включены в список [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="10a2f-127">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span> <span data-ttu-id="10a2f-128">Для каждого метода интерфейса, который не включен в контракт службы, создается трассировка.</span><span class="sxs-lookup"><span data-stu-id="10a2f-128">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10a2f-129">См. также</span><span class="sxs-lookup"><span data-stu-id="10a2f-129">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComMethodElementCollection>  
 <xref:System.ServiceModel.Configuration.ComMethodElement>  
 [<span data-ttu-id="10a2f-130">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="10a2f-130">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="10a2f-131">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="10a2f-131">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="10a2f-132">Практическое руководство. Настройка параметров службы COM+</span><span class="sxs-lookup"><span data-stu-id="10a2f-132">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
