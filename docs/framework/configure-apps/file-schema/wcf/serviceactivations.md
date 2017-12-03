---
title: '&lt;serviceActivations&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 43461f23476d1c387cec06f9aee893defa634201
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltserviceactivationsgt"></a><span data-ttu-id="e3d1c-102">&lt;serviceActivations&gt;</span><span class="sxs-lookup"><span data-stu-id="e3d1c-102">&lt;serviceActivations&gt;</span></span>
<span data-ttu-id="e3d1c-103">Элемент конфигурации, позволяющий добавлять настройки, которые определяют параметры активации виртуальной службы, сопоставляющиеся с типами служб [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3d1c-103">A configuration element that allows you to add settings that define virtual service activation settings that map to your [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service types.</span></span> <span data-ttu-id="e3d1c-104">Это позволяет активировать службы, расположенные в WAS/IIS, без SVC-файла.</span><span class="sxs-lookup"><span data-stu-id="e3d1c-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>  
  
 <span data-ttu-id="e3d1c-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e3d1c-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="e3d1c-106">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="e3d1c-106">\<serviceHostingEnvironment></span></span>  
<span data-ttu-id="e3d1c-107">\<serviceActivations ></span><span class="sxs-lookup"><span data-stu-id="e3d1c-107">\<serviceActivations></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3d1c-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3d1c-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <serviceActivations>  
      <add factory="String"  
           service="String"/>  
   </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3d1c-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e3d1c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e3d1c-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e3d1c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3d1c-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e3d1c-111">Attributes</span></span>  
 <span data-ttu-id="e3d1c-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e3d1c-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e3d1c-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e3d1c-113">Child Elements</span></span>  
  
|<span data-ttu-id="e3d1c-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="e3d1c-114">Element</span></span>|<span data-ttu-id="e3d1c-115">Описание</span><span class="sxs-lookup"><span data-stu-id="e3d1c-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3d1c-116">\<add></span><span class="sxs-lookup"><span data-stu-id="e3d1c-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-serviceactivations.md)|<span data-ttu-id="e3d1c-117">Добавляет элемент конфигурации, который задает активацию приложения службы.</span><span class="sxs-lookup"><span data-stu-id="e3d1c-117">Adds a configuration element that specifies the activation of a service application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e3d1c-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e3d1c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e3d1c-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="e3d1c-119">Element</span></span>|<span data-ttu-id="e3d1c-120">Описание</span><span class="sxs-lookup"><span data-stu-id="e3d1c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3d1c-121">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="e3d1c-121">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="e3d1c-122">Определяет, какой тип среда размещения служб создает для конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="e3d1c-122">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3d1c-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="e3d1c-123">Remarks</span></span>  
 <span data-ttu-id="e3d1c-124">В следующем примере показано, как настроить параметры активации в файле web.config.</span><span class="sxs-lookup"><span data-stu-id="e3d1c-124">The following example shows how to configure activation settings within your web.config file.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <serviceHostingEnvironment>  
      <serviceActivations>  
        <add service="GreetingService"/>  
      </serviceActivations>  
    </serviceHostingEnvironment>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="e3d1c-125">Использование этой конфигурации позволяет активировать GreetingService без SVC-файла.</span><span class="sxs-lookup"><span data-stu-id="e3d1c-125">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>  
  
 <span data-ttu-id="e3d1c-126">Следует отметить, что `<serviceHostingEnvironment>` является конфигурацией на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="e3d1c-126">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="e3d1c-127">Необходимо разместить файл `web.config`, содержащий конфигурацию в корневом каталоге виртуального приложения.</span><span class="sxs-lookup"><span data-stu-id="e3d1c-127">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="e3d1c-128">Помимо этого, `serviceHostingEnvironment` является наследуемым разделом machinetoApplication.</span><span class="sxs-lookup"><span data-stu-id="e3d1c-128">In addition, `serviceHostingEnvironment` is a machinetoApplication inheritable section.</span></span> <span data-ttu-id="e3d1c-129">Если зарегистрировать одну службу в корневом каталоге компьютера, каждая служба в приложении унаследует эту службу.</span><span class="sxs-lookup"><span data-stu-id="e3d1c-129">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>  
  
 <span data-ttu-id="e3d1c-130">Активация на основе конфигурации поддерживает активацию как по протоколу HTTP, так и по протоколу, отличному от HTTP.</span><span class="sxs-lookup"><span data-stu-id="e3d1c-130">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="e3d1c-131">Требует расширений в relatativeAddress, т.е. SVC, XOML или XAMLX.</span><span class="sxs-lookup"><span data-stu-id="e3d1c-131">It requires extensions in the relatativeAddress i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="e3d1c-132">Можно сопоставить пользовательские расширения с известными поставщиками buildProvider, что впоследствии позволит активировать службу через любое расширение.</span><span class="sxs-lookup"><span data-stu-id="e3d1c-132">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="e3d1c-133">При возникновении конфликта раздел `<serviceActivations>` переопределяет записи в SVC-файле.</span><span class="sxs-lookup"><span data-stu-id="e3d1c-133">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3d1c-134">См. также</span><span class="sxs-lookup"><span data-stu-id="e3d1c-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>
