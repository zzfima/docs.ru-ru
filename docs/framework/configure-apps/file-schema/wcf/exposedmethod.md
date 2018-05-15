---
title: '&lt;exposedMethod&gt;'
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 2a26ca90f6a66592c246cc9e5aef50cfa53b4bdd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltexposedmethodgt"></a><span data-ttu-id="03202-102">&lt;exposedMethod&gt;</span><span class="sxs-lookup"><span data-stu-id="03202-102">&lt;exposedMethod&gt;</span></span>
<span data-ttu-id="03202-103">Представляет метод COM+, предоставляемый, когда интерфейс компонента COM+ предоставляется как веб-служба.</span><span class="sxs-lookup"><span data-stu-id="03202-103">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
 <span data-ttu-id="03202-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="03202-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="03202-105">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="03202-105">\<comContracts></span></span>  
<span data-ttu-id="03202-106">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="03202-106">\<comContract></span></span>  
<span data-ttu-id="03202-107">\<методы ></span><span class="sxs-lookup"><span data-stu-id="03202-107">\<methods></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03202-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="03202-108">Syntax</span></span>  
  
```xml  
<comContracts>  
  <comContract>  
      <exposedMethods>  
         <exposedMethod name="string" />  
      </exposedMethods>  
  </comContract>  
</comContracts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03202-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="03202-109">Attributes and Elements</span></span>  
 <span data-ttu-id="03202-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="03202-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03202-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="03202-111">Attributes</span></span>  
  
|<span data-ttu-id="03202-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="03202-112">Attribute</span></span>|<span data-ttu-id="03202-113">Описание</span><span class="sxs-lookup"><span data-stu-id="03202-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="03202-114">имя</span><span class="sxs-lookup"><span data-stu-id="03202-114">name</span></span>|<span data-ttu-id="03202-115">Строка, которая содержит метод COM+, предоставляемый, когда интерфейс компонента COM+ предоставляется как веб-служба.</span><span class="sxs-lookup"><span data-stu-id="03202-115">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="03202-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="03202-116">Child Elements</span></span>  
 <span data-ttu-id="03202-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="03202-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="03202-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="03202-118">Parent Elements</span></span>  
  
|<span data-ttu-id="03202-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="03202-119">Element</span></span>|<span data-ttu-id="03202-120">Описание</span><span class="sxs-lookup"><span data-stu-id="03202-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03202-121">\<exposedMethods ></span><span class="sxs-lookup"><span data-stu-id="03202-121">\<exposedMethods></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethods.md)|<span data-ttu-id="03202-122">Коллекция [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="03202-122">A collection of [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03202-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="03202-123">Remarks</span></span>  
 <span data-ttu-id="03202-124">Средство конфигурации интеграции COM+ (ComSvcConfig.exe) может применяться для добавления определенных методов COM-интерфейса для использования в созданном контракте службы.</span><span class="sxs-lookup"><span data-stu-id="03202-124">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="03202-125">Например, для добавления в созданный контракт службы трех именованных методов из COM-интерфейса `IFinances` компонента `ItemOrders`.Financial можно использовать приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="03202-125">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="03202-126">При выполнении ComSvcConfig.exe, оно создает следующий контракт службы, указанные выше методы перечисляются как перечисление [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="03202-126">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}" name="IFinances" namespace="http://contoso.com/services/financial">  
    <exposedMethod name="TransferFunds"/>  
    <exposedMethod name="AddFunds"/>  
    <exposedMethod name="RemoveFunds"/>  
</comContract>  
```  
  
 <span data-ttu-id="03202-127">Во время инициализации службы среда выполнения пытается создать контракт службы, отображая и добавляя только те методы, которые включены в список [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="03202-127">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span> <span data-ttu-id="03202-128">Для каждого метода интерфейса, который не включен в контракт службы, создается трассировка.</span><span class="sxs-lookup"><span data-stu-id="03202-128">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03202-129">См. также</span><span class="sxs-lookup"><span data-stu-id="03202-129">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComMethodElementCollection>  
 <xref:System.ServiceModel.Configuration.ComMethodElement>  
 [<span data-ttu-id="03202-130">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="03202-130">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="03202-131">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="03202-131">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="03202-132">Практическое руководство. Настройка параметров службы COM+</span><span class="sxs-lookup"><span data-stu-id="03202-132">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
