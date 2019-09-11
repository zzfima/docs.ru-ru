---
title: <serviceActivations>
ms.date: 03/30/2017
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
ms.openlocfilehash: 64ae0bfd90ae941fc78515c7936c998201c87485
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855132"
---
# <a name="serviceactivations"></a><span data-ttu-id="78f34-101">\<serviceActivations ></span><span class="sxs-lookup"><span data-stu-id="78f34-101">\<serviceActivations></span></span>

<span data-ttu-id="78f34-102">Элемент конфигурации, позволяющий добавлять параметры, определяющие параметры активации виртуальной службы, сопоставленные с типами служб Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="78f34-102">A configuration element that allows you to add settings that define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="78f34-103">Это позволяет активировать службы, расположенные в WAS/IIS, без SVC-файла.</span><span class="sxs-lookup"><span data-stu-id="78f34-103">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

<span data-ttu-id="78f34-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="78f34-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="78f34-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="78f34-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="78f34-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceHostingEnvironment >** ](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="78f34-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="78f34-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceActivations >**</span><span class="sxs-lookup"><span data-stu-id="78f34-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceActivations>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="78f34-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78f34-108">Syntax</span></span>

```xml
<serviceHostingEnvironment>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="78f34-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="78f34-109">Attributes and Elements</span></span>

<span data-ttu-id="78f34-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="78f34-110">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="78f34-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="78f34-111">Attributes</span></span>

<span data-ttu-id="78f34-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="78f34-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="78f34-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="78f34-113">Child Elements</span></span>

|<span data-ttu-id="78f34-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="78f34-114">Element</span></span>|<span data-ttu-id="78f34-115">Описание</span><span class="sxs-lookup"><span data-stu-id="78f34-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="78f34-116">\<add></span><span class="sxs-lookup"><span data-stu-id="78f34-116">\<add></span></span>](add-of-serviceactivations.md)|<span data-ttu-id="78f34-117">Добавляет элемент конфигурации, который задает активацию приложения службы.</span><span class="sxs-lookup"><span data-stu-id="78f34-117">Adds a configuration element that specifies the activation of a service application.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="78f34-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="78f34-118">Parent Elements</span></span>

|<span data-ttu-id="78f34-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="78f34-119">Element</span></span>|<span data-ttu-id="78f34-120">Описание</span><span class="sxs-lookup"><span data-stu-id="78f34-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="78f34-121">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="78f34-121">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="78f34-122">Определяет, какой тип среда размещения служб создает для конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="78f34-122">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|

## <a name="remarks"></a><span data-ttu-id="78f34-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="78f34-123">Remarks</span></span>

<span data-ttu-id="78f34-124">В следующем примере показано, как настроить параметры активации в файле web.config.</span><span class="sxs-lookup"><span data-stu-id="78f34-124">The following example shows how to configure activation settings within your web.config file.</span></span>

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

<span data-ttu-id="78f34-125">Использование этой конфигурации позволяет активировать GreetingService без SVC-файла.</span><span class="sxs-lookup"><span data-stu-id="78f34-125">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="78f34-126">Следует отметить, что `<serviceHostingEnvironment>` является конфигурацией на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="78f34-126">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="78f34-127">Необходимо разместить файл `web.config`, содержащий конфигурацию в корневом каталоге виртуального приложения.</span><span class="sxs-lookup"><span data-stu-id="78f34-127">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="78f34-128">Кроме того, `serviceHostingEnvironment` является machineToApplication наследуемым разделом.</span><span class="sxs-lookup"><span data-stu-id="78f34-128">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="78f34-129">Если зарегистрировать одну службу в корневом каталоге компьютера, каждая служба в приложении унаследует эту службу.</span><span class="sxs-lookup"><span data-stu-id="78f34-129">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="78f34-130">Активация на основе конфигурации поддерживает активацию как по протоколу HTTP, так и по протоколу, отличному от HTTP.</span><span class="sxs-lookup"><span data-stu-id="78f34-130">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="78f34-131">Для этого требуются расширения в Релативеаддресс, например. svc,. XOML или. xamlx.</span><span class="sxs-lookup"><span data-stu-id="78f34-131">It requires extensions in the relativeAddress i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="78f34-132">Можно сопоставить пользовательские расширения с известными поставщиками buildProvider, что впоследствии позволит активировать службу через любое расширение.</span><span class="sxs-lookup"><span data-stu-id="78f34-132">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="78f34-133">При возникновении конфликта раздел `<serviceActivations>` переопределяет записи в SVC-файле.</span><span class="sxs-lookup"><span data-stu-id="78f34-133">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="78f34-134">См. также</span><span class="sxs-lookup"><span data-stu-id="78f34-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
