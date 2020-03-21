---
title: Служба обнаружения маршрутизатора
ms.date: 03/30/2017
ms.assetid: 3d30af47-b24f-40e5-833a-24d77125c9e6
ms.openlocfilehash: 149dd69cdd1972465f4b7cb48ab657492d3f21d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183726"
---
# <a name="discovery-router-service"></a><span data-ttu-id="adca5-102">Служба обнаружения маршрутизатора</span><span class="sxs-lookup"><span data-stu-id="adca5-102">Discovery Router Service</span></span>
<span data-ttu-id="adca5-103">В этом образце показаны способы направления сообщений обнаружения другой конечной точке.</span><span class="sxs-lookup"><span data-stu-id="adca5-103">This sample demonstrates how to forward discovery messages to another endpoint.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="adca5-104">Что демонстрирует</span><span class="sxs-lookup"><span data-stu-id="adca5-104">Demonstrates</span></span>  
 <span data-ttu-id="adca5-105">Маршрутизация обнаружения</span><span class="sxs-lookup"><span data-stu-id="adca5-105">Discovery Routing</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="adca5-106">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="adca5-106">Discussion</span></span>  
 <span data-ttu-id="adca5-107">Маршрутизация обнаружения используется в случаях, когда клиент выполняет поиск службы с использованием прокси-сервера и этот прокси-сервер не имеет данных об этой службе, но обладает сведениями о другом прокси-сервере.</span><span class="sxs-lookup"><span data-stu-id="adca5-107">Discovery routing is useful in a scenario in which a client is looking for a service using a proxy and the proxy is unaware of such a service, but knows of another proxy.</span></span> <span data-ttu-id="adca5-108">Этот прокси-сервер может направлять пакет обнаружения от этого клиента второму прокси-серверу.</span><span class="sxs-lookup"><span data-stu-id="adca5-108">This proxy can forward the discovery packet from this client to the second proxy.</span></span> <span data-ttu-id="adca5-109">Второй прокси-сервер может выполнить поиск службы и вернуть ответы исходному клиенту.</span><span class="sxs-lookup"><span data-stu-id="adca5-109">The second proxy can look for the service and return the responses to the original client.</span></span>  
  
 <span data-ttu-id="adca5-110">В этом образце клиент отправляет сообщение компоненту маршрутизации обнаружения.</span><span class="sxs-lookup"><span data-stu-id="adca5-110">In this sample, a client sends a message to a discovery routing component.</span></span> <span data-ttu-id="adca5-111">Это сообщение отправляется определенной конечной точке на маршрутизаторе обнаружения.</span><span class="sxs-lookup"><span data-stu-id="adca5-111">This message is sent to a specific endpoint on the discovery router.</span></span> <span data-ttu-id="adca5-112">Затем маршрутизатор перенаправляет сообщение по многоадресной рассылке конечной точке определяемой пользователем процедуре.</span><span class="sxs-lookup"><span data-stu-id="adca5-112">The router then forwards the message to a UDP multicast endpoint.</span></span> <span data-ttu-id="adca5-113">Сообщение зонда передается по многоадресной рассылке конечной точке, а служба, прослушивающая адрес многоадресной рассылки определяемой пользователем процедуры, реагирует на маршрутизатор обнаружения.</span><span class="sxs-lookup"><span data-stu-id="adca5-113">The probe message goes out to the multicast endpoint and a service listening on a UDP multicast address responds to that discovery router.</span></span> <span data-ttu-id="adca5-114">Маршрутизатор обнаружения выполняет сбор ответов и отправляет их обратно клиенту.</span><span class="sxs-lookup"><span data-stu-id="adca5-114">The discovery router collects the responses and sends them back to the client.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="adca5-115">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="adca5-115">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="adca5-116">Выполните сборку примера.</span><span class="sxs-lookup"><span data-stu-id="adca5-116">Build the sample.</span></span>  
  
2. <span data-ttu-id="adca5-117">Запустите исполняемый файл DiscoveryRouter.</span><span class="sxs-lookup"><span data-stu-id="adca5-117">Run the DiscoveryRouter executable.</span></span>  
  
3. <span data-ttu-id="adca5-118">Выполните исполняемый файл службы из каталога сборки.</span><span class="sxs-lookup"><span data-stu-id="adca5-118">Run the service executable from the build directory.</span></span>  
  
4. <span data-ttu-id="adca5-119">Выполните исполняемый файл клиента.</span><span class="sxs-lookup"><span data-stu-id="adca5-119">Run the client executable.</span></span> <span data-ttu-id="adca5-120">Обратите внимание, что клиент нашел службу.</span><span class="sxs-lookup"><span data-stu-id="adca5-120">Note that the client locates the service.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="adca5-121">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="adca5-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="adca5-122">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="adca5-122">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="adca5-123">Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы.</span><span class="sxs-lookup"><span data-stu-id="adca5-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="adca5-124">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="adca5-124">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryRouter`
