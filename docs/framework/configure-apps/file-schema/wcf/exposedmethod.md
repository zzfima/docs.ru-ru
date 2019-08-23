---
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 032139b714aa11079c7ee8610c332e404b3981ac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918999"
---
# <a name="exposedmethod"></a><span data-ttu-id="f3944-101">\<exposedMethod ></span><span class="sxs-lookup"><span data-stu-id="f3944-101">\<exposedMethod></span></span>
<span data-ttu-id="f3944-102">Представляет метод COM+, предоставляемый, когда интерфейс компонента COM+ предоставляется как веб-служба.</span><span class="sxs-lookup"><span data-stu-id="f3944-102">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
 <span data-ttu-id="f3944-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f3944-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="f3944-104">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="f3944-104">\<comContracts></span></span>  
<span data-ttu-id="f3944-105">\<Комконтракт ></span><span class="sxs-lookup"><span data-stu-id="f3944-105">\<comContract></span></span>  
<span data-ttu-id="f3944-106">\<методы ></span><span class="sxs-lookup"><span data-stu-id="f3944-106">\<methods></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3944-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3944-107">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3944-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f3944-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f3944-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f3944-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3944-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f3944-110">Attributes</span></span>  
  
|<span data-ttu-id="f3944-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f3944-111">Attribute</span></span>|<span data-ttu-id="f3944-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f3944-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f3944-113">имя</span><span class="sxs-lookup"><span data-stu-id="f3944-113">name</span></span>|<span data-ttu-id="f3944-114">Строка, которая содержит метод COM+, предоставляемый, когда интерфейс компонента COM+ предоставляется как веб-служба.</span><span class="sxs-lookup"><span data-stu-id="f3944-114">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f3944-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f3944-115">Child Elements</span></span>  
 <span data-ttu-id="f3944-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="f3944-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f3944-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f3944-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f3944-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="f3944-118">Element</span></span>|<span data-ttu-id="f3944-119">Описание</span><span class="sxs-lookup"><span data-stu-id="f3944-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f3944-120">\<Експоседмесодс ></span><span class="sxs-lookup"><span data-stu-id="f3944-120">\<exposedMethods></span></span>](exposedmethods.md)|<span data-ttu-id="f3944-121">[ Коллекция\<элементов > exposedMethod](exposedmethod.md) .</span><span class="sxs-lookup"><span data-stu-id="f3944-121">A collection of [\<exposedMethod>](exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3944-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="f3944-122">Remarks</span></span>  
 <span data-ttu-id="f3944-123">Средство конфигурации интеграции COM+ (ComSvcConfig.exe) может применяться для добавления определенных методов COM-интерфейса для использования в созданном контракте службы.</span><span class="sxs-lookup"><span data-stu-id="f3944-123">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="f3944-124">Например, для добавления в созданный контракт службы трех именованных методов из COM-интерфейса `IFinances` компонента `ItemOrders`.Financial можно использовать приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="f3944-124">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="f3944-125">При запуске файла ComSvcConfig. exe он создает следующий контракт службы с перечнем упомянутых выше методов как [ \<exposedMethod >](exposedmethod.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="f3944-125">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 <span data-ttu-id="f3944-126">Во время инициализации службы среда выполнения пытается создать контракт службы, отражая и добавляя только методы, входящие в список [ \<элементов exposedMethod >](exposedmethod.md) .</span><span class="sxs-lookup"><span data-stu-id="f3944-126">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](exposedmethod.md) elements.</span></span> <span data-ttu-id="f3944-127">Для каждого метода интерфейса, который не включен в контракт службы, создается трассировка.</span><span class="sxs-lookup"><span data-stu-id="f3944-127">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3944-128">См. также</span><span class="sxs-lookup"><span data-stu-id="f3944-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [<span data-ttu-id="f3944-129">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="f3944-129">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="f3944-130">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="f3944-130">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="f3944-131">Практическое руководство. Настройка параметров службы COM+</span><span class="sxs-lookup"><span data-stu-id="f3944-131">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
