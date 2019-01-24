---
title: '&lt;serviceActivations&gt;'
ms.date: 03/30/2017
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
ms.openlocfilehash: 5da05c7b6a9685b9e34b3181ce8e0bd31ccd052b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54704960"
---
# <a name="ltserviceactivationsgt"></a><span data-ttu-id="aa5dc-102">&lt;serviceActivations&gt;</span><span class="sxs-lookup"><span data-stu-id="aa5dc-102">&lt;serviceActivations&gt;</span></span>
<span data-ttu-id="aa5dc-103">Элемент конфигурации, позволяющий добавлять параметры, определяющие параметры активации виртуальной службы, которые сопоставляются с типами службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="aa5dc-103">A configuration element that allows you to add settings that define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="aa5dc-104">Это позволяет активировать службы, расположенные в WAS/IIS, без SVC-файла.</span><span class="sxs-lookup"><span data-stu-id="aa5dc-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>  
  
 <span data-ttu-id="aa5dc-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="aa5dc-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="aa5dc-106">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="aa5dc-106">\<serviceHostingEnvironment></span></span>  
<span data-ttu-id="aa5dc-107">\<serviceActivations ></span><span class="sxs-lookup"><span data-stu-id="aa5dc-107">\<serviceActivations></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa5dc-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa5dc-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa5dc-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="aa5dc-109">Attributes and Elements</span></span>  
 <span data-ttu-id="aa5dc-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="aa5dc-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa5dc-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aa5dc-111">Attributes</span></span>  
 <span data-ttu-id="aa5dc-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="aa5dc-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="aa5dc-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="aa5dc-113">Child Elements</span></span>  
  
|<span data-ttu-id="aa5dc-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="aa5dc-114">Element</span></span>|<span data-ttu-id="aa5dc-115">Описание</span><span class="sxs-lookup"><span data-stu-id="aa5dc-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa5dc-116">\<add></span><span class="sxs-lookup"><span data-stu-id="aa5dc-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-serviceactivations.md)|<span data-ttu-id="aa5dc-117">Добавляет элемент конфигурации, который задает активацию приложения службы.</span><span class="sxs-lookup"><span data-stu-id="aa5dc-117">Adds a configuration element that specifies the activation of a service application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aa5dc-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="aa5dc-118">Parent Elements</span></span>  
  
|<span data-ttu-id="aa5dc-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="aa5dc-119">Element</span></span>|<span data-ttu-id="aa5dc-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="aa5dc-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa5dc-121">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="aa5dc-121">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="aa5dc-122">Определяет, какой тип среда размещения служб создает для конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="aa5dc-122">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa5dc-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="aa5dc-123">Remarks</span></span>  
 <span data-ttu-id="aa5dc-124">В следующем примере показано, как настроить параметры активации в файле web.config.</span><span class="sxs-lookup"><span data-stu-id="aa5dc-124">The following example shows how to configure activation settings within your web.config file.</span></span>  
  
```xml  
<configuration>
  <system.serviceModel>
    <serviceHostingEnvironment>
      <serviceActivations>
        <add service="GreetingService" />
      </serviceActivations>
    </serviceHostingEnvironment>
  </system.serviceModel>
</configuration>
```  
  
 <span data-ttu-id="aa5dc-125">Использование этой конфигурации позволяет активировать GreetingService без SVC-файла.</span><span class="sxs-lookup"><span data-stu-id="aa5dc-125">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>  
  
 <span data-ttu-id="aa5dc-126">Следует отметить, что `<serviceHostingEnvironment>` является конфигурацией на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="aa5dc-126">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="aa5dc-127">Необходимо разместить файл `web.config`, содержащий конфигурацию в корневом каталоге виртуального приложения.</span><span class="sxs-lookup"><span data-stu-id="aa5dc-127">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="aa5dc-128">Помимо этого, `serviceHostingEnvironment` является наследуемым разделом machinetoApplication.</span><span class="sxs-lookup"><span data-stu-id="aa5dc-128">In addition, `serviceHostingEnvironment` is a machinetoApplication inheritable section.</span></span> <span data-ttu-id="aa5dc-129">Если зарегистрировать одну службу в корневом каталоге компьютера, каждая служба в приложении унаследует эту службу.</span><span class="sxs-lookup"><span data-stu-id="aa5dc-129">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>  
  
 <span data-ttu-id="aa5dc-130">Активация на основе конфигурации поддерживает активацию как по протоколу HTTP, так и по протоколу, отличному от HTTP.</span><span class="sxs-lookup"><span data-stu-id="aa5dc-130">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="aa5dc-131">Требует расширений в relatativeAddress, т.е. SVC, XOML или XAMLX.</span><span class="sxs-lookup"><span data-stu-id="aa5dc-131">It requires extensions in the relatativeAddress i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="aa5dc-132">Можно сопоставить пользовательские расширения с известными поставщиками buildProvider, что впоследствии позволит активировать службу через любое расширение.</span><span class="sxs-lookup"><span data-stu-id="aa5dc-132">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="aa5dc-133">При возникновении конфликта раздел `<serviceActivations>` переопределяет записи в SVC-файле.</span><span class="sxs-lookup"><span data-stu-id="aa5dc-133">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa5dc-134">См. также</span><span class="sxs-lookup"><span data-stu-id="aa5dc-134">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
