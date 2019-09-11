---
title: <add> из <serviceActivations>
ms.date: 03/30/2017
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
ms.openlocfilehash: a0f68717f765482f53e675458fae63d1a374d6fb
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850326"
---
# <a name="add-of-serviceactivations"></a><span data-ttu-id="7f2bf-102">\<Добавление > \<> serviceActivations</span><span class="sxs-lookup"><span data-stu-id="7f2bf-102">\<add> of \<serviceActivations></span></span>

<span data-ttu-id="7f2bf-103">Элемент конфигурации, позволяющий определить параметры активации виртуальной службы, которые сопоставляются с типами служб Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="7f2bf-103">A configuration element that allows you to define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="7f2bf-104">Это позволяет активировать службы, расположенные в WAS/IIS, без SVC-файла.</span><span class="sxs-lookup"><span data-stu-id="7f2bf-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

<span data-ttu-id="7f2bf-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7f2bf-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7f2bf-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7f2bf-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7f2bf-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceHostingEnvironment >** ](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="7f2bf-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="7f2bf-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceActivations >** ](serviceactivations.md)</span><span class="sxs-lookup"><span data-stu-id="7f2bf-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceActivations>**](serviceactivations.md)</span></span>\
<span data-ttu-id="7f2bf-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Добавить >**</span><span class="sxs-lookup"><span data-stu-id="7f2bf-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="7f2bf-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7f2bf-110">Syntax</span></span>

```xml
<serviceHostingEnvironment>
    <serviceActivations>
      <add factory="String"
           service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7f2bf-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7f2bf-111">Attributes and Elements</span></span>

<span data-ttu-id="7f2bf-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7f2bf-112">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="7f2bf-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7f2bf-113">Attributes</span></span>

|<span data-ttu-id="7f2bf-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7f2bf-114">Attribute</span></span>|<span data-ttu-id="7f2bf-115">Описание</span><span class="sxs-lookup"><span data-stu-id="7f2bf-115">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="7f2bf-116">фабрика</span><span class="sxs-lookup"><span data-stu-id="7f2bf-116">factory</span></span>|<span data-ttu-id="7f2bf-117">Строка, задающая имя типа CLR фабрики, которая формирует элемент активации службы.</span><span class="sxs-lookup"><span data-stu-id="7f2bf-117">A string that specifies the CLR type name of the factory that generates a service activation element.</span></span>|
|<span data-ttu-id="7f2bf-118">служба</span><span class="sxs-lookup"><span data-stu-id="7f2bf-118">service</span></span>|<span data-ttu-id="7f2bf-119">ServiceType, реализующий службу (либо полное, либо короткое имя типа) (когда оно размещено в папке App_Code).</span><span class="sxs-lookup"><span data-stu-id="7f2bf-119">The ServiceType that implements the service (either the full qualified Typename or the short Typename (when it is placed in the App_Code folder).</span></span>|
|<span data-ttu-id="7f2bf-120">relativeAddress</span><span class="sxs-lookup"><span data-stu-id="7f2bf-120">relativeAddress</span></span>|<span data-ttu-id="7f2bf-121">Относительный адрес в текущем приложении IIS (например, «Service.svc»).</span><span class="sxs-lookup"><span data-stu-id="7f2bf-121">The relative address within the current IIS application - for example "Service.svc".</span></span> <span data-ttu-id="7f2bf-122">В WCF 4.0 этот относительный адрес должен содержать одно из известных расширений файлов (SVC, XAMLX и т. д.). Ни один физический файл не должен существовать по адресу relativeUrl</span><span class="sxs-lookup"><span data-stu-id="7f2bf-122">In WCF 4.0 this relative address has to contain one of the known file extensions (.svc, .xamlx, ...). No physical file has to exist for the relativeUrl</span></span>|

### <a name="child-elements"></a><span data-ttu-id="7f2bf-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7f2bf-123">Child Elements</span></span>

<span data-ttu-id="7f2bf-124">Нет.</span><span class="sxs-lookup"><span data-stu-id="7f2bf-124">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7f2bf-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7f2bf-125">Parent Elements</span></span>

|<span data-ttu-id="7f2bf-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="7f2bf-126">Element</span></span>|<span data-ttu-id="7f2bf-127">Описание</span><span class="sxs-lookup"><span data-stu-id="7f2bf-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7f2bf-128">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="7f2bf-128">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="7f2bf-129">Раздел конфигурации, в котором описываются параметры активации.</span><span class="sxs-lookup"><span data-stu-id="7f2bf-129">A configuration section that describes activation settings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7f2bf-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="7f2bf-130">Remarks</span></span>

<span data-ttu-id="7f2bf-131">В следующем примере показано, как настроить параметры активации в файле web.config.</span><span class="sxs-lookup"><span data-stu-id="7f2bf-131">The following example shows how to configure activation settings within your web.config file.</span></span>

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

<span data-ttu-id="7f2bf-132">Использование этой конфигурации позволяет активировать GreetingService без SVC-файла.</span><span class="sxs-lookup"><span data-stu-id="7f2bf-132">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="7f2bf-133">Следует отметить, что `<serviceHostingEnvironment>` является конфигурацией на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="7f2bf-133">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="7f2bf-134">Необходимо разместить файл `web.config`, содержащий конфигурацию в корневом каталоге виртуального приложения.</span><span class="sxs-lookup"><span data-stu-id="7f2bf-134">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="7f2bf-135">Кроме того, `serviceHostingEnvironment` является machineToApplication наследуемым разделом.</span><span class="sxs-lookup"><span data-stu-id="7f2bf-135">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="7f2bf-136">Если зарегистрировать одну службу в корневом каталоге компьютера, каждая служба в приложении унаследует эту службу.</span><span class="sxs-lookup"><span data-stu-id="7f2bf-136">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="7f2bf-137">Активация на основе конфигурации поддерживает активацию как по протоколу HTTP, так и по протоколу, отличному от HTTP.</span><span class="sxs-lookup"><span data-stu-id="7f2bf-137">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="7f2bf-138">Для этого требуются расширения в Релативеаддресс, например. svc,. XOML или. xamlx.</span><span class="sxs-lookup"><span data-stu-id="7f2bf-138">It requires extensions in the relativeAddress, i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="7f2bf-139">Можно сопоставить пользовательские расширения с известными поставщиками buildProvider, что впоследствии позволит активировать службу через любое расширение.</span><span class="sxs-lookup"><span data-stu-id="7f2bf-139">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="7f2bf-140">При возникновении конфликта раздел `<serviceActivations>` переопределяет записи в SVC-файле.</span><span class="sxs-lookup"><span data-stu-id="7f2bf-140">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f2bf-141">См. также</span><span class="sxs-lookup"><span data-stu-id="7f2bf-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
