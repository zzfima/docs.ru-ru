---
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 46f2872fb289c2793c356ea179deb3ce52e6d65e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855306"
---
# <a name="exposedmethod"></a><span data-ttu-id="67421-101">\<exposedMethod ></span><span class="sxs-lookup"><span data-stu-id="67421-101">\<exposedMethod></span></span>
<span data-ttu-id="67421-102">Представляет метод COM+, предоставляемый, когда интерфейс компонента COM+ предоставляется как веб-служба.</span><span class="sxs-lookup"><span data-stu-id="67421-102">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
<span data-ttu-id="67421-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="67421-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="67421-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="67421-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="67421-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comContracts >** ](comcontracts.md)</span><span class="sxs-lookup"><span data-stu-id="67421-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)</span></span>\
<span data-ttu-id="67421-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Комконтракт >** ](comcontract.md)</span><span class="sxs-lookup"><span data-stu-id="67421-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)</span></span>\
<span data-ttu-id="67421-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Експоседмесодс >** ](exposedmethods.md)</span><span class="sxs-lookup"><span data-stu-id="67421-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<exposedMethods>**](exposedmethods.md)</span></span>\
<span data-ttu-id="67421-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<exposedMethod >**</span><span class="sxs-lookup"><span data-stu-id="67421-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<exposedMethod>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67421-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67421-109">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="67421-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="67421-110">Attributes and Elements</span></span>  
 <span data-ttu-id="67421-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="67421-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="67421-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="67421-112">Attributes</span></span>  
  
|<span data-ttu-id="67421-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="67421-113">Attribute</span></span>|<span data-ttu-id="67421-114">Описание</span><span class="sxs-lookup"><span data-stu-id="67421-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="67421-115">имя</span><span class="sxs-lookup"><span data-stu-id="67421-115">name</span></span>|<span data-ttu-id="67421-116">Строка, которая содержит метод COM+, предоставляемый, когда интерфейс компонента COM+ предоставляется как веб-служба.</span><span class="sxs-lookup"><span data-stu-id="67421-116">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="67421-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="67421-117">Child Elements</span></span>  
 <span data-ttu-id="67421-118">Нет.</span><span class="sxs-lookup"><span data-stu-id="67421-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="67421-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="67421-119">Parent Elements</span></span>  
  
|<span data-ttu-id="67421-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="67421-120">Element</span></span>|<span data-ttu-id="67421-121">Описание</span><span class="sxs-lookup"><span data-stu-id="67421-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="67421-122">\<Експоседмесодс ></span><span class="sxs-lookup"><span data-stu-id="67421-122">\<exposedMethods></span></span>](exposedmethods.md)|<span data-ttu-id="67421-123">[ Коллекция\<элементов > exposedMethod](exposedmethod.md) .</span><span class="sxs-lookup"><span data-stu-id="67421-123">A collection of [\<exposedMethod>](exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67421-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="67421-124">Remarks</span></span>  
 <span data-ttu-id="67421-125">Средство конфигурации интеграции COM+ (ComSvcConfig.exe) может применяться для добавления определенных методов COM-интерфейса для использования в созданном контракте службы.</span><span class="sxs-lookup"><span data-stu-id="67421-125">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="67421-126">Например, для добавления в созданный контракт службы трех именованных методов из COM-интерфейса `IFinances` компонента `ItemOrders`.Financial можно использовать приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="67421-126">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="67421-127">При запуске файла ComSvcConfig. exe он создает следующий контракт службы с перечнем упомянутых выше методов как [ \<exposedMethod >](exposedmethod.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="67421-127">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 <span data-ttu-id="67421-128">Во время инициализации службы среда выполнения пытается создать контракт службы, отражая и добавляя только методы, входящие в список [ \<элементов exposedMethod >](exposedmethod.md) .</span><span class="sxs-lookup"><span data-stu-id="67421-128">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](exposedmethod.md) elements.</span></span> <span data-ttu-id="67421-129">Для каждого метода интерфейса, который не включен в контракт службы, создается трассировка.</span><span class="sxs-lookup"><span data-stu-id="67421-129">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67421-130">См. также</span><span class="sxs-lookup"><span data-stu-id="67421-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [<span data-ttu-id="67421-131">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="67421-131">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="67421-132">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="67421-132">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="67421-133">Практическое руководство. Настройка параметров службы COM+</span><span class="sxs-lookup"><span data-stu-id="67421-133">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
