---
title: "Обнаружение WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF [WCF], discovery
- Windows Communication Foundation [WCF], discovery
- discovery [WCF]
ms.assetid: 462c4913-f388-45a9-9042-28ae96a4e735
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fda50f14d9003b81f93840571b8b27f874f7730b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="wcf-discovery"></a><span data-ttu-id="8dd2b-102">Обнаружение WCF</span><span class="sxs-lookup"><span data-stu-id="8dd2b-102">WCF Discovery</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="8dd2b-103"> предоставляет поддержку для включения обнаружения служб во время выполнения совместимым способом с помощью протокола WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="8dd2b-103"> provides support to enable services to be discoverable at runtime in an interoperable way using the WS-Discovery protocol.</span></span> <span data-ttu-id="8dd2b-104">Службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] могут сообщать о своей доступности компьютерам в сети с помощью многоадресного сообщения либо передавать сообщение прокси-серверу обнаружения.</span><span class="sxs-lookup"><span data-stu-id="8dd2b-104">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services can announce their availability to the network using a multicast message or to a discovery proxy server.</span></span> <span data-ttu-id="8dd2b-105">Клиентские приложения могут осуществлять поиск служб, отвечающих набору указанных критериев, в сети или на прокси-сервере обнаружения.</span><span class="sxs-lookup"><span data-stu-id="8dd2b-105">Client applications can search the network or a discovery proxy server to find services that meet a set of criteria.</span></span> <span data-ttu-id="8dd2b-106">В подразделах этого раздела представлены общие сведения и описание модели программирования данной возможности.</span><span class="sxs-lookup"><span data-stu-id="8dd2b-106">The topics in this section provide an overview and describe the programming model for this feature in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8dd2b-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="8dd2b-107">In This Section</span></span>  
 [<span data-ttu-id="8dd2b-108">Общие сведения об обнаружении WCF</span><span class="sxs-lookup"><span data-stu-id="8dd2b-108">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 <span data-ttu-id="8dd2b-109">Общие сведения о поддержке WS-Discovery в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8dd2b-109">Provides an overview of WS-Discovery support provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="8dd2b-110">Модель объектов обнаружения WCF</span><span class="sxs-lookup"><span data-stu-id="8dd2b-110">WCF Discovery Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)  
 <span data-ttu-id="8dd2b-111">Содержит описание классов объектной модели и расширяемости поддержки WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="8dd2b-111">Describes the classes in the object model and extensibility of WS-Discovery support.</span></span>  
  
 [<span data-ttu-id="8dd2b-112">Как: программно добавить возможность обнаружения службы WCF и клиент</span><span class="sxs-lookup"><span data-stu-id="8dd2b-112">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 <span data-ttu-id="8dd2b-113">Показано, как сделать службу [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] доступной для обнаружения.</span><span class="sxs-lookup"><span data-stu-id="8dd2b-113">Shows how to make a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service discoverable.</span></span>  
  
 [<span data-ttu-id="8dd2b-114">Реализация прокси-сервера обнаружения</span><span class="sxs-lookup"><span data-stu-id="8dd2b-114">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  
 <span data-ttu-id="8dd2b-115">Содержит описание шагов, необходимых для реализации прокси-сервера обнаружения, службы, доступной для обнаружения, которая регистрируется на прокси-сервере обнаружения, и клиента, использующего прокси-сервер обнаружения для поиска этой службы.</span><span class="sxs-lookup"><span data-stu-id="8dd2b-115">Describes the steps required to implement a discovery proxy, a discoverable service that registers with the discovery proxy, and a client that uses the discovery proxy to find the discoverable service.</span></span>  
  
 [<span data-ttu-id="8dd2b-116">Управление версиями обнаружения</span><span class="sxs-lookup"><span data-stu-id="8dd2b-116">Discovery Versioning</span></span>](../../../../docs/framework/wcf/feature-details/discovery-versioning.md)  
 <span data-ttu-id="8dd2b-117">Содержит общие сведения о реализации прототипа некоторых новых возможностей обнаружения.</span><span class="sxs-lookup"><span data-stu-id="8dd2b-117">Provides a brief overview of a prototype implementation of some new discovery features.</span></span> <span data-ttu-id="8dd2b-118">Также приводятся общие сведения о выборе версии обнаружения.</span><span class="sxs-lookup"><span data-stu-id="8dd2b-118">It also gives an overview on how to select the discovery version to use.</span></span>  
  
 [<span data-ttu-id="8dd2b-119">Настройка обнаружения в файле конфигурации</span><span class="sxs-lookup"><span data-stu-id="8dd2b-119">Configuring Discovery in a Configuration File</span></span>](../../../../docs/framework/wcf/feature-details/configuring-discovery-in-a-configuration-file.md)  
 <span data-ttu-id="8dd2b-120">Настройка обнаружения в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8dd2b-120">Shows how to configure Discovery in configuration.</span></span>  
  
 [<span data-ttu-id="8dd2b-121">Использование клиентского канала обнаружения</span><span class="sxs-lookup"><span data-stu-id="8dd2b-121">Using the Discovery Client Channel</span></span>](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)  
 <span data-ttu-id="8dd2b-122">Демонстрирует процесс использования клиентского канала обнаружения при записи клиентского приложения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8dd2b-122">Shows how to use a Discovery Client Channel when writing a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client application.</span></span>
