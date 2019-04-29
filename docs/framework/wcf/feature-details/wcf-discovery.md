---
title: Обнаружение WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], discovery
- Windows Communication Foundation [WCF], discovery
- discovery [WCF]
ms.assetid: 462c4913-f388-45a9-9042-28ae96a4e735
ms.openlocfilehash: 175f79096d2bbda81a602d38e027d5a6d871fa12
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768697"
---
# <a name="wcf-discovery"></a><span data-ttu-id="e121d-102">Обнаружение WCF</span><span class="sxs-lookup"><span data-stu-id="e121d-102">WCF Discovery</span></span>
<span data-ttu-id="e121d-103">Windows Communication Foundation (WCF) предоставляет поддержку для включения служб для обнаружения во время выполнения совместимым способом с помощью протокола WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="e121d-103">Windows Communication Foundation (WCF) provides support to enable services to be discoverable at runtime in an interoperable way using the WS-Discovery protocol.</span></span> <span data-ttu-id="e121d-104">Службы WCF можно объявлять свою доступность сети, с помощью многоадресной рассылки сообщения или на прокси-сервере обнаружения.</span><span class="sxs-lookup"><span data-stu-id="e121d-104">WCF services can announce their availability to the network using a multicast message or to a discovery proxy server.</span></span> <span data-ttu-id="e121d-105">Клиентские приложения могут осуществлять поиск служб, отвечающих набору указанных критериев, в сети или на прокси-сервере обнаружения.</span><span class="sxs-lookup"><span data-stu-id="e121d-105">Client applications can search the network or a discovery proxy server to find services that meet a set of criteria.</span></span> <span data-ttu-id="e121d-106">В подразделах этого раздела представлены общие сведения и описание модели программирования данной функции.</span><span class="sxs-lookup"><span data-stu-id="e121d-106">The topics in this section provide an overview and describe the programming model for this feature in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e121d-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="e121d-107">In This Section</span></span>  
 [<span data-ttu-id="e121d-108">Общие сведения об обнаружении WCF</span><span class="sxs-lookup"><span data-stu-id="e121d-108">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 <span data-ttu-id="e121d-109">Общие сведения о WS-Discovery, предоставляемый платформой WCF.</span><span class="sxs-lookup"><span data-stu-id="e121d-109">Provides an overview of WS-Discovery support provided by WCF.</span></span>  
  
 [<span data-ttu-id="e121d-110">Объектная модель обнаружения WCF</span><span class="sxs-lookup"><span data-stu-id="e121d-110">WCF Discovery Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)  
 <span data-ttu-id="e121d-111">Содержит описание классов объектной модели и расширяемости поддержки WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="e121d-111">Describes the classes in the object model and extensibility of WS-Discovery support.</span></span>  
  
 [<span data-ttu-id="e121d-112">Практическое руководство. Программно добавьте возможность обнаружения к службе и клиенту WCF</span><span class="sxs-lookup"><span data-stu-id="e121d-112">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 <span data-ttu-id="e121d-113">Показано, как сделать доступным для обнаружения службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e121d-113">Shows how to make a Windows Communication Foundation (WCF) service discoverable.</span></span>  
  
 [<span data-ttu-id="e121d-114">Реализация прокси-сервера обнаружения</span><span class="sxs-lookup"><span data-stu-id="e121d-114">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  
 <span data-ttu-id="e121d-115">Содержит описание шагов, необходимых для реализации прокси-сервера обнаружения, службы, доступной для обнаружения, которая регистрируется на прокси-сервере обнаружения, и клиента, использующего прокси-сервер обнаружения для поиска этой службы.</span><span class="sxs-lookup"><span data-stu-id="e121d-115">Describes the steps required to implement a discovery proxy, a discoverable service that registers with the discovery proxy, and a client that uses the discovery proxy to find the discoverable service.</span></span>  
  
 [<span data-ttu-id="e121d-116">Управление версиями обнаружения</span><span class="sxs-lookup"><span data-stu-id="e121d-116">Discovery Versioning</span></span>](../../../../docs/framework/wcf/feature-details/discovery-versioning.md)  
 <span data-ttu-id="e121d-117">Содержит общие сведения о реализации прототипа некоторых новых функций обнаружения.</span><span class="sxs-lookup"><span data-stu-id="e121d-117">Provides a brief overview of a prototype implementation of some new discovery features.</span></span> <span data-ttu-id="e121d-118">Также приводятся общие сведения о выборе версии обнаружения.</span><span class="sxs-lookup"><span data-stu-id="e121d-118">It also gives an overview on how to select the discovery version to use.</span></span>  
  
 [<span data-ttu-id="e121d-119">Настройка обнаружения в файле конфигурации</span><span class="sxs-lookup"><span data-stu-id="e121d-119">Configuring Discovery in a Configuration File</span></span>](../../../../docs/framework/wcf/feature-details/configuring-discovery-in-a-configuration-file.md)  
 <span data-ttu-id="e121d-120">Настройка обнаружения в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e121d-120">Shows how to configure Discovery in configuration.</span></span>  
  
 [<span data-ttu-id="e121d-121">Использование клиентского канала обнаружения</span><span class="sxs-lookup"><span data-stu-id="e121d-121">Using the Discovery Client Channel</span></span>](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)  
 <span data-ttu-id="e121d-122">Показано использование клиентского канала обнаружения при написании клиентского приложения WCF.</span><span class="sxs-lookup"><span data-stu-id="e121d-122">Shows how to use a Discovery Client Channel when writing a WCF client application.</span></span>
