---
title: Управление версиями обнаружения
ms.date: 03/30/2017
ms.assetid: f91c6d0a-3af2-45c5-9a5c-e75390619836
ms.openlocfilehash: 4a1ca07fc6773ce6f883d654abfedab4986341e1
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425254"
---
# <a name="discovery-versioning"></a><span data-ttu-id="79bfc-102">Управление версиями обнаружения</span><span class="sxs-lookup"><span data-stu-id="79bfc-102">Discovery Versioning</span></span>

<span data-ttu-id="79bfc-103">В этом разделе приведены общие сведения о реализации некоторых новых возможностей обнаружения.</span><span class="sxs-lookup"><span data-stu-id="79bfc-103">This topic provides a brief overview of the implementation of some new discovery features.</span></span> <span data-ttu-id="79bfc-104">Также приводятся общие сведения о выборе версии обнаружения.</span><span class="sxs-lookup"><span data-stu-id="79bfc-104">It also gives an overview on how to select the discovery version to use.</span></span>

## <a name="discovery-versioning"></a><span data-ttu-id="79bfc-105">Управление версиями обнаружения</span><span class="sxs-lookup"><span data-stu-id="79bfc-105">Discovery Versioning</span></span>

<span data-ttu-id="79bfc-106">Возможность обнаружения поддерживает три версии протокола обнаружения WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="79bfc-106">The discovery feature includes support for three versions of the WS_Discovery protocol.</span></span> <span data-ttu-id="79bfc-107">API обнаружения позволяют выбирать используемую версию протокола.</span><span class="sxs-lookup"><span data-stu-id="79bfc-107">The discovery APIs allow you to select which version of the protocol you want to use.</span></span> <span data-ttu-id="79bfc-108">В этом документе кратко описаны параметры, связанные с версиями.</span><span class="sxs-lookup"><span data-stu-id="79bfc-108">This document briefly describes the versioning-related settings.</span></span>

<span data-ttu-id="79bfc-109">У следующих классов Discovery теперь имеется свойство <xref:System.ServiceModel.Discovery.DiscoveryVersion>, их конструкторы также принимают аргумент <xref:System.ServiceModel.Discovery.DiscoveryVersion>:</span><span class="sxs-lookup"><span data-stu-id="79bfc-109">The following Discovery classes now have a <xref:System.ServiceModel.Discovery.DiscoveryVersion> property and take a <xref:System.ServiceModel.Discovery.DiscoveryVersion> argument in their constructors:</span></span>

- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>

- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>

- <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>

- <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>

### <a name="discoveryversionwsdiscoveryapril2005"></a><span data-ttu-id="79bfc-110">DiscoveryVersion.WSDiscoveryApril2005</span><span class="sxs-lookup"><span data-stu-id="79bfc-110">DiscoveryVersion.WSDiscoveryApril2005</span></span>

<span data-ttu-id="79bfc-111">Предоставляя <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryApril2005> как конструктор делает реализация будет использовать April2005 версию протокола WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="79bfc-111">Providing <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryApril2005> as a constructor parameter makes the implementation use the April2005 version of the WS-Discovery protocol.</span></span> <span data-ttu-id="79bfc-112">Эта версия соответствует опубликованной версии спецификации протокола WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="79bfc-112">This version corresponds to the published version of the WS-Discovery protocol specification.</span></span> <span data-ttu-id="79bfc-113">Эту версию следует использовать для взаимодействия с приложениями прежних версий, использующими версию протокола WS-Discovery от апреля 2005 г.</span><span class="sxs-lookup"><span data-stu-id="79bfc-113">This version should be used to interoperate with legacy application utilizing the April2005 version of WS-Discovery.</span></span>

### <a name="discoveryversionwsdiscovery11"></a><span data-ttu-id="79bfc-114">DiscoveryVersion.WSDiscovery11</span><span class="sxs-lookup"><span data-stu-id="79bfc-114">DiscoveryVersion.WSDiscovery11</span></span>

<span data-ttu-id="79bfc-115">Версия обнаружения по умолчанию, используемые интерфейсы API — <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscovery11>.</span><span class="sxs-lookup"><span data-stu-id="79bfc-115">The default discovery version used by the APIs is <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscovery11>.</span></span> <span data-ttu-id="79bfc-116">Эта версия протокола обнаружения WS-Discovery на данный момент является стандартной.</span><span class="sxs-lookup"><span data-stu-id="79bfc-116">This is the current standardized version of the WS-Discovery protocol.</span></span>

## <a name="discoveryversionwsdiscoverycd1"></a><span data-ttu-id="79bfc-117">DiscoveryVersion.WSDiscoveryCD1</span><span class="sxs-lookup"><span data-stu-id="79bfc-117">DiscoveryVersion.WSDiscoveryCD1</span></span>

<span data-ttu-id="79bfc-118">При указании параметра конструктора <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryCD1> реализация будет использовать рассматриваемый соответствующим комитетом проект 1 версии протокола WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="79bfc-118">Providing <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryCD1> as a constructor parameter makes the implementation use the committee draft 1 version of the WS-Discovery protocol.</span></span> <span data-ttu-id="79bfc-119">Эту версию протокола следует использовать для взаимодействия с реализациями, в которых применяется версия CD1 протокола WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="79bfc-119">This version of the protocol should be used to interoperate with implementations running the CD1 version of the WS-Discovery protocol.</span></span>

## <a name="supporting-multiple-udp-discovery-endpoints-for-different-discovery-versions-on-a-single-service-host"></a><span data-ttu-id="79bfc-120">Поддержка нескольких конечных точек обнаружения UDP с различными версиями обнаружения на одном узле службы</span><span class="sxs-lookup"><span data-stu-id="79bfc-120">Supporting Multiple UDP Discovery Endpoints for Different Discovery Versions on a Single Service Host</span></span>

<span data-ttu-id="79bfc-121">Может потребоваться предоставление доступа к нескольким конечным точкам обнаружения UDP с различными версиями обнаружения на одном узле службы.</span><span class="sxs-lookup"><span data-stu-id="79bfc-121">You may want to expose multiple UDP Discovery Endpoints for different discovery versions on a single service host.</span></span> <span data-ttu-id="79bfc-122">Для этого необходимо задать для каждой из конечных точек обнаружения UDP уникальный адрес.</span><span class="sxs-lookup"><span data-stu-id="79bfc-122">To do this you must specify a unique address for each UDP discovery endpoint.</span></span> <span data-ttu-id="79bfc-123">Следующий пример показывает, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="79bfc-123">The following example shows how to do this.</span></span>

```csharp
UdpDiscoveryEndpoint newVersionUdpEndpoint = new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscovery11);
UdpDiscoveryEndpoint oldVersionUdpEndpoint = new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);

newVersionUdpEndpoint.Address = new EndpointAddress(newVersionUdpEndpoint.Address.Uri.ToString() + "/version11");
oldVersionUdpEndpoint.Address = new EndpointAddress(oldVersionUdpEndpoint.Address.Uri.ToString() + "/versionApril2005");

serviceHost.AddServiceEndpoint(newVersionUdpEndpoint);
serviceHost.AddServiceEndpoint(oldVersionUdpEndpoint);
```
