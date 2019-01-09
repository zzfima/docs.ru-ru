---
title: '&lt;add&gt; для &lt;serviceActivations&gt;'
ms.date: 03/30/2017
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
ms.openlocfilehash: b40127d531926f103f3e367c8721e8f5ff8e1a99
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151544"
---
# <a name="ltaddgt-of-ltserviceactivationsgt"></a><span data-ttu-id="7f841-102">&lt;add&gt; для &lt;serviceActivations&gt;</span><span class="sxs-lookup"><span data-stu-id="7f841-102">&lt;add&gt; of &lt;serviceActivations&gt;</span></span>
<span data-ttu-id="7f841-103">Элемент конфигурации, можно задать параметры активации виртуальной службы, сопоставленные с типами службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="7f841-103">A configuration element that allows you to define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="7f841-104">Это позволяет активировать службы, расположенные в WAS/IIS, без SVC-файла.</span><span class="sxs-lookup"><span data-stu-id="7f841-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>  
  
 <span data-ttu-id="7f841-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7f841-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="7f841-106">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="7f841-106">\<ServiceHostingEnvironment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f841-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7f841-107">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
    <serviceActivations>
      <add factory="String"
           service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f841-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7f841-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7f841-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7f841-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f841-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7f841-110">Attributes</span></span>  
  
|<span data-ttu-id="7f841-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7f841-111">Attribute</span></span>|<span data-ttu-id="7f841-112">Описание</span><span class="sxs-lookup"><span data-stu-id="7f841-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7f841-113">factory</span><span class="sxs-lookup"><span data-stu-id="7f841-113">factory</span></span>|<span data-ttu-id="7f841-114">Строка, задающая имя типа CLR фабрики, которая формирует элемент активации службы.</span><span class="sxs-lookup"><span data-stu-id="7f841-114">A string that specifies the CLR type name of the factory that generates a service activation element.</span></span>|  
|<span data-ttu-id="7f841-115">service</span><span class="sxs-lookup"><span data-stu-id="7f841-115">service</span></span>|<span data-ttu-id="7f841-116">ServiceType, реализующий службу (либо полное, либо короткое имя типа) (когда оно размещено в папке App_Code).</span><span class="sxs-lookup"><span data-stu-id="7f841-116">The ServiceType that implements the service (either the full qualified Typename or the short Typename (when it is placed in the App_Code folder).</span></span>|  
|<span data-ttu-id="7f841-117">relativeAddress</span><span class="sxs-lookup"><span data-stu-id="7f841-117">relativeAddress</span></span>|<span data-ttu-id="7f841-118">Относительный адрес в текущем приложении IIS (например, «Service.svc»).</span><span class="sxs-lookup"><span data-stu-id="7f841-118">The relative address within the current IIS application - for example "Service.svc".</span></span> <span data-ttu-id="7f841-119">В WCF 4.0 этот относительный адрес должен содержать одно из известных расширений файлов (SVC, XAMLX и т. д.). Ни один физический файл не должен существовать по адресу relativeUrl</span><span class="sxs-lookup"><span data-stu-id="7f841-119">In WCF 4.0 this relative address has to contain one of the known file extensions (.svc, .xamlx, ...). No physical file has to exist for the relativeUrl</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7f841-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7f841-120">Child Elements</span></span>  
 <span data-ttu-id="7f841-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7f841-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7f841-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7f841-122">Parent Elements</span></span>  
  
|<span data-ttu-id="7f841-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="7f841-123">Element</span></span>|<span data-ttu-id="7f841-124">Описание</span><span class="sxs-lookup"><span data-stu-id="7f841-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f841-125">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="7f841-125">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="7f841-126">Раздел конфигурации, в котором описываются параметры активации.</span><span class="sxs-lookup"><span data-stu-id="7f841-126">A configuration section that describes activation settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f841-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="7f841-127">Remarks</span></span>  
 <span data-ttu-id="7f841-128">В следующем примере показано, как настроить параметры активации в файле web.config.</span><span class="sxs-lookup"><span data-stu-id="7f841-128">The following example shows how to configure activation settings within your web.config file.</span></span>  
  
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
  
 <span data-ttu-id="7f841-129">Использование этой конфигурации позволяет активировать GreetingService без SVC-файла.</span><span class="sxs-lookup"><span data-stu-id="7f841-129">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>  
  
 <span data-ttu-id="7f841-130">Следует отметить, что `<serviceHostingEnvironment>` является конфигурацией на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="7f841-130">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="7f841-131">Необходимо разместить файл `web.config`, содержащий конфигурацию в корневом каталоге виртуального приложения.</span><span class="sxs-lookup"><span data-stu-id="7f841-131">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="7f841-132">Помимо этого, `serviceHostingEnvironment` является наследуемым разделом machinetoApplication.</span><span class="sxs-lookup"><span data-stu-id="7f841-132">In addition, `serviceHostingEnvironment` is a machinetoApplication inheritable section.</span></span> <span data-ttu-id="7f841-133">Если зарегистрировать одну службу в корневом каталоге компьютера, каждая служба в приложении унаследует эту службу.</span><span class="sxs-lookup"><span data-stu-id="7f841-133">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>  
  
 <span data-ttu-id="7f841-134">Активация на основе конфигурации поддерживает активацию как по протоколу HTTP, так и по протоколу, отличному от HTTP.</span><span class="sxs-lookup"><span data-stu-id="7f841-134">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="7f841-135">Требует расширений в relatativeAddress, т.е. SVC, XOML или XAMLX.</span><span class="sxs-lookup"><span data-stu-id="7f841-135">It requires extensions in the relatativeAddress, i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="7f841-136">Можно сопоставить пользовательские расширения с известными поставщиками buildProvider, что впоследствии позволит активировать службу через любое расширение.</span><span class="sxs-lookup"><span data-stu-id="7f841-136">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="7f841-137">При возникновении конфликта раздел `<serviceActivations>` переопределяет записи в SVC-файле.</span><span class="sxs-lookup"><span data-stu-id="7f841-137">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f841-138">См. также</span><span class="sxs-lookup"><span data-stu-id="7f841-138">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceActivationElement>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>
