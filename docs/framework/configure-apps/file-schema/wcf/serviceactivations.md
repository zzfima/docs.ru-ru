---
title: <serviceActivations>
ms.date: 03/30/2017
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
ms.openlocfilehash: 7506cce61966a4a4650ff591cd6106dfd4a33b67
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670369"
---
# <a name="serviceactivations"></a><span data-ttu-id="d35d0-101">\<serviceActivations ></span><span class="sxs-lookup"><span data-stu-id="d35d0-101">\<serviceActivations></span></span>

<span data-ttu-id="d35d0-102">Элемент конфигурации, позволяющий добавлять параметры, определяющие параметры активации виртуальной службы, которые сопоставляются с типами службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="d35d0-102">A configuration element that allows you to add settings that define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="d35d0-103">Это позволяет активировать службы, расположенные в WAS/IIS, без SVC-файла.</span><span class="sxs-lookup"><span data-stu-id="d35d0-103">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

<span data-ttu-id="d35d0-104">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="d35d0-104">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="d35d0-105">\<serviceHostingEnvironment > \\</span><span class="sxs-lookup"><span data-stu-id="d35d0-105">\<serviceHostingEnvironment>\\</span></span>
<span data-ttu-id="d35d0-106">\<serviceActivations ></span><span class="sxs-lookup"><span data-stu-id="d35d0-106">\<serviceActivations></span></span>

## <a name="syntax"></a><span data-ttu-id="d35d0-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d35d0-107">Syntax</span></span>

```xml
<serviceHostingEnvironment>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d35d0-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d35d0-108">Attributes and Elements</span></span>

<span data-ttu-id="d35d0-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d35d0-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d35d0-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d35d0-110">Attributes</span></span>

<span data-ttu-id="d35d0-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d35d0-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d35d0-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d35d0-112">Child Elements</span></span>

|<span data-ttu-id="d35d0-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="d35d0-113">Element</span></span>|<span data-ttu-id="d35d0-114">Описание</span><span class="sxs-lookup"><span data-stu-id="d35d0-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d35d0-115">\<add></span><span class="sxs-lookup"><span data-stu-id="d35d0-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-serviceactivations.md)|<span data-ttu-id="d35d0-116">Добавляет элемент конфигурации, который задает активацию приложения службы.</span><span class="sxs-lookup"><span data-stu-id="d35d0-116">Adds a configuration element that specifies the activation of a service application.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d35d0-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d35d0-117">Parent Elements</span></span>

|<span data-ttu-id="d35d0-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="d35d0-118">Element</span></span>|<span data-ttu-id="d35d0-119">Описание</span><span class="sxs-lookup"><span data-stu-id="d35d0-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d35d0-120">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="d35d0-120">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="d35d0-121">Определяет, какой тип среда размещения служб создает для конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="d35d0-121">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d35d0-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="d35d0-122">Remarks</span></span>

<span data-ttu-id="d35d0-123">В следующем примере показано, как настроить параметры активации в файле web.config.</span><span class="sxs-lookup"><span data-stu-id="d35d0-123">The following example shows how to configure activation settings within your web.config file.</span></span>

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

<span data-ttu-id="d35d0-124">Использование этой конфигурации позволяет активировать GreetingService без SVC-файла.</span><span class="sxs-lookup"><span data-stu-id="d35d0-124">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="d35d0-125">Следует отметить, что `<serviceHostingEnvironment>` является конфигурацией на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="d35d0-125">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="d35d0-126">Необходимо разместить файл `web.config`, содержащий конфигурацию в корневом каталоге виртуального приложения.</span><span class="sxs-lookup"><span data-stu-id="d35d0-126">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="d35d0-127">Кроме того `serviceHostingEnvironment` является наследуемым разделом machineToApplication.</span><span class="sxs-lookup"><span data-stu-id="d35d0-127">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="d35d0-128">Если зарегистрировать одну службу в корневом каталоге компьютера, каждая служба в приложении унаследует эту службу.</span><span class="sxs-lookup"><span data-stu-id="d35d0-128">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="d35d0-129">Активация на основе конфигурации поддерживает активацию как по протоколу HTTP, так и по протоколу, отличному от HTTP.</span><span class="sxs-lookup"><span data-stu-id="d35d0-129">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="d35d0-130">Требует расширений в relativeAddress, т. е. .svc XOML- и .xamlx.</span><span class="sxs-lookup"><span data-stu-id="d35d0-130">It requires extensions in the relativeAddress i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="d35d0-131">Можно сопоставить пользовательские расширения с известными поставщиками buildProvider, что впоследствии позволит активировать службу через любое расширение.</span><span class="sxs-lookup"><span data-stu-id="d35d0-131">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="d35d0-132">При возникновении конфликта раздел `<serviceActivations>` переопределяет записи в SVC-файле.</span><span class="sxs-lookup"><span data-stu-id="d35d0-132">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="d35d0-133">См. также</span><span class="sxs-lookup"><span data-stu-id="d35d0-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
