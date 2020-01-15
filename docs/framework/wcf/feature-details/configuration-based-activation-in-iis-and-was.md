---
title: Активация на основе конфигурации в IIS и WAS
ms.date: 03/30/2017
ms.assetid: 6a927e1f-b905-4ee5-ad0f-78265da38238
ms.openlocfilehash: 6515d6621798a9dab67aa7b73a39b9481c1779fc
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2020
ms.locfileid: "75963488"
---
# <a name="configuration-based-activation-in-iis-and-was"></a><span data-ttu-id="fda6b-102">Активация на основе конфигурации в IIS и WAS</span><span class="sxs-lookup"><span data-stu-id="fda6b-102">Configuration-Based Activation in IIS and WAS</span></span>

<span data-ttu-id="fda6b-103">Обычно при размещении службы Windows Communication Foundation (WCF) в службы IIS (IIS) или службе активации Windows (WAS) необходимо предоставить SVC-файл.</span><span class="sxs-lookup"><span data-stu-id="fda6b-103">Normally when hosting a Windows Communication Foundation (WCF) service under Internet Information Services (IIS) or Windows Process Activation Service (WAS), you must provide a .svc file.</span></span> <span data-ttu-id="fda6b-104">SVC-файл содержит имя службы, а также дополнительную пользовательскую фабрику узла службы.</span><span class="sxs-lookup"><span data-stu-id="fda6b-104">The .svc file contains the name of the service and an optional custom service host factory.</span></span> <span data-ttu-id="fda6b-105">С помощью этого дополнительного файла добавляются служебные данные по управлению.</span><span class="sxs-lookup"><span data-stu-id="fda6b-105">This additional file adds manageability overhead.</span></span> <span data-ttu-id="fda6b-106">Возможность активации на основе конфигурации снимает требование по наличию SVC-файла и, следовательно, по наличию связанных служебных данных.</span><span class="sxs-lookup"><span data-stu-id="fda6b-106">The configuration-based activation feature removes the requirement to have a .svc file and therefore the associated overhead.</span></span>

## <a name="configuration-based-activation"></a><span data-ttu-id="fda6b-107">Активация на основе конфигурации</span><span class="sxs-lookup"><span data-stu-id="fda6b-107">Configuration-Based Activation</span></span>

<span data-ttu-id="fda6b-108">Активация на основе конфигурации принимает метаданные, которые используются для размещения в SVC-файле, и помещает их в файл Web.config.</span><span class="sxs-lookup"><span data-stu-id="fda6b-108">Configuration-based activation takes the metadata that used to be placed in the .svc file and places it in the Web.config file.</span></span> <span data-ttu-id="fda6b-109">В элементе > <`serviceHostingEnvironment`имеется элемент <`serviceActivations`>.</span><span class="sxs-lookup"><span data-stu-id="fda6b-109">Within the<`serviceHostingEnvironment`> element there is a <`serviceActivations`> element.</span></span> <span data-ttu-id="fda6b-110">В <`serviceActivations`элемент > — один или несколько элементов <`add`>, по одному для каждой размещенной службы.</span><span class="sxs-lookup"><span data-stu-id="fda6b-110">Within the <`serviceActivations`> element are one or more <`add`> elements, one for each hosted service.</span></span> <span data-ttu-id="fda6b-111">Элемент <`add`> содержит атрибуты, позволяющие задать относительный адрес для службы, а также тип службы или фабрику узла службы.</span><span class="sxs-lookup"><span data-stu-id="fda6b-111">The <`add`> element contains attributes that let you set the relative address for the service and the service type or a service host factory.</span></span> <span data-ttu-id="fda6b-112">В следующем примере конфигурации показано, каким образом используется этот раздел.</span><span class="sxs-lookup"><span data-stu-id="fda6b-112">The following configuration example code shows how this section is used.</span></span>

> [!NOTE]
> <span data-ttu-id="fda6b-113">Каждый <`add`элемент > должен указывать атрибут Service или Factory.</span><span class="sxs-lookup"><span data-stu-id="fda6b-113">Each <`add`> element must specify a service or a factory attribute.</span></span> <span data-ttu-id="fda6b-114">Можно указать и атрибут службы, и атрибут фабрики.</span><span class="sxs-lookup"><span data-stu-id="fda6b-114">Specifying both service and factory attributes is allowed.</span></span>

```xml
<serviceHostingEnvironment>
  <serviceActivations>
    <add relativeAddress="MyServiceAddress" service="Service" factory="MyServiceHostFactory"/>
  </serviceActivations>
</serviceHostingEnvironment>
```

 <span data-ttu-id="fda6b-115">Такой код, показанный в файле Web.config, позволяет поместить исходный код службы в каталог App_Code приложения или откомпилированную сборку в каталог Bin приложения.</span><span class="sxs-lookup"><span data-stu-id="fda6b-115">With this in the Web.config file, you can place the service source code in the App_Code directory of the application or a complied assembly in the Bin directory of the application.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="fda6b-116">При использовании активации на основе конфигурации, встроенный программный код в SVC-файлах не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="fda6b-116">When using configuration-based activation, inline code in .svc files is not supported.</span></span>
> - <span data-ttu-id="fda6b-117">Для атрибута `relativeAddress` необходимо задать относительный адрес, например "\<подкаталог >/сервице.СВК" или "~/\<суб-директори/Service. svc".</span><span class="sxs-lookup"><span data-stu-id="fda6b-117">The `relativeAddress` attribute must be set to a relative address such as "\<sub-directory>/service.svc" or "~/\<sub-directory/service.svc".</span></span>
> - <span data-ttu-id="fda6b-118">Если зарегистрирован относительный адрес, который не содержит известного расширения имени, связанного с WCF, то будет создано исключение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fda6b-118">A configuration exception is thrown if you register a relative address that does not have a known extension associated with WCF.</span></span>
> - <span data-ttu-id="fda6b-119">Относительный адрес указывается относительно корневого каталога виртуального приложения.</span><span class="sxs-lookup"><span data-stu-id="fda6b-119">The relative address specified is relative to the root of the virtual application.</span></span>
> - <span data-ttu-id="fda6b-120">Поскольку модель конфигурации имеет иерархическую структуру, относительный адрес, который зарегистрирован на уровне компьютера и узла, наследуется виртуальными приложениями.</span><span class="sxs-lookup"><span data-stu-id="fda6b-120">Due to the hierarchical model of configuration, the registered relative addresses at machine and site level are inherited by virtual applications.</span></span>
> - <span data-ttu-id="fda6b-121">Регистрация в файле конфигурации имеет более высокий приоритет, чем параметры в SVC-файле, XAMLX-файле, XOML-файле и других файлах.</span><span class="sxs-lookup"><span data-stu-id="fda6b-121">Registrations in a configuration file take precedence over settings in a .svc, .xamlx, .xoml, or other file.</span></span>
> - <span data-ttu-id="fda6b-122">Все символы обратной косой черты «\» в URI, отправляемых в IIS/WAS, автоматически преобразуются в символы косой черты «/».</span><span class="sxs-lookup"><span data-stu-id="fda6b-122">Any ‘\’ (backslashes) in a URI sent to IIS/WAS are automatically converted to a ‘/’ (forward slash).</span></span> <span data-ttu-id="fda6b-123">Если добавляемый относительный адрес содержит символ «\», а в IIS отправлен URI, который использует относительный адрес, то символ обратной косой черты преобразуется в символ косой черты и IIS не может сопоставить его с относительным адресом.</span><span class="sxs-lookup"><span data-stu-id="fda6b-123">If a relative address is added that contains a ‘\’ and you send IIS a URI that uses the relative address, the backslash is converted to a forward slash and IIS cannot match it to the relative address.</span></span> <span data-ttu-id="fda6b-124">Службы IIS отправляют сведения трассировки, которые указывают, что соответствие не найдено.</span><span class="sxs-lookup"><span data-stu-id="fda6b-124">IIS sends out trace information that indicates that there are no matches found.</span></span>

## <a name="see-also"></a><span data-ttu-id="fda6b-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="fda6b-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection.ServiceActivations%2A>
- [<span data-ttu-id="fda6b-126">Размещение служб</span><span class="sxs-lookup"><span data-stu-id="fda6b-126">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
- [<span data-ttu-id="fda6b-127">Общие сведения о размещении служб рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="fda6b-127">Hosting Workflow Services Overview</span></span>](../../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md)
- [<span data-ttu-id="fda6b-128">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="fda6b-128">\<serviceHostingEnvironment></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)
- <span data-ttu-id="fda6b-129">[Функции размещения Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="fda6b-129">[Windows Server App Fabric Hosting Features](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
