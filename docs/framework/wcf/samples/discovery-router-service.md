---
title: Служба обнаружения маршрутизатора
ms.date: 03/30/2017
ms.assetid: 3d30af47-b24f-40e5-833a-24d77125c9e6
ms.openlocfilehash: 09309b23d2a3cc672811c2f617e6fb81a2b4e021
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74712291"
---
# <a name="discovery-router-service"></a><span data-ttu-id="8d249-102">Служба обнаружения маршрутизатора</span><span class="sxs-lookup"><span data-stu-id="8d249-102">Discovery Router Service</span></span>
<span data-ttu-id="8d249-103">В этом образце показаны способы направления сообщений обнаружения другой конечной точке.</span><span class="sxs-lookup"><span data-stu-id="8d249-103">This sample demonstrates how to forward discovery messages to another endpoint.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="8d249-104">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="8d249-104">Demonstrates</span></span>  
 <span data-ttu-id="8d249-105">Маршрутизация обнаружения</span><span class="sxs-lookup"><span data-stu-id="8d249-105">Discovery Routing</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="8d249-106">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="8d249-106">Discussion</span></span>  
 <span data-ttu-id="8d249-107">Маршрутизация обнаружения используется в случаях, когда клиент выполняет поиск службы с использованием прокси-сервера и этот прокси-сервер не имеет данных об этой службе, но обладает сведениями о другом прокси-сервере.</span><span class="sxs-lookup"><span data-stu-id="8d249-107">Discovery routing is useful in a scenario in which a client is looking for a service using a proxy and the proxy is unaware of such a service, but knows of another proxy.</span></span> <span data-ttu-id="8d249-108">Этот прокси-сервер может направлять пакет обнаружения от этого клиента второму прокси-серверу.</span><span class="sxs-lookup"><span data-stu-id="8d249-108">This proxy can forward the discovery packet from this client to the second proxy.</span></span> <span data-ttu-id="8d249-109">Второй прокси-сервер может выполнить поиск службы и вернуть ответы исходному клиенту.</span><span class="sxs-lookup"><span data-stu-id="8d249-109">The second proxy can look for the service and return the responses to the original client.</span></span>  
  
 <span data-ttu-id="8d249-110">В этом образце клиент отправляет сообщение компоненту маршрутизации обнаружения.</span><span class="sxs-lookup"><span data-stu-id="8d249-110">In this sample, a client sends a message to a discovery routing component.</span></span> <span data-ttu-id="8d249-111">Это сообщение отправляется определенной конечной точке на маршрутизаторе обнаружения.</span><span class="sxs-lookup"><span data-stu-id="8d249-111">This message is sent to a specific endpoint on the discovery router.</span></span> <span data-ttu-id="8d249-112">Затем маршрутизатор перенаправляет сообщение по многоадресной рассылке конечной точке определяемой пользователем процедуре.</span><span class="sxs-lookup"><span data-stu-id="8d249-112">The router then forwards the message to a UDP multicast endpoint.</span></span> <span data-ttu-id="8d249-113">Сообщение зонда передается по многоадресной рассылке конечной точке, а служба, прослушивающая адрес многоадресной рассылки определяемой пользователем процедуры, реагирует на маршрутизатор обнаружения.</span><span class="sxs-lookup"><span data-stu-id="8d249-113">The probe message goes out to the multicast endpoint and a service listening on a UDP multicast address responds to that discovery router.</span></span> <span data-ttu-id="8d249-114">Маршрутизатор обнаружения выполняет сбор ответов и отправляет их обратно клиенту.</span><span class="sxs-lookup"><span data-stu-id="8d249-114">The discovery router collects the responses and sends them back to the client.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8d249-115">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="8d249-115">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="8d249-116">Постройте образец.</span><span class="sxs-lookup"><span data-stu-id="8d249-116">Build the sample.</span></span>  
  
2. <span data-ttu-id="8d249-117">Запустите исполняемый файл DiscoveryRouter.</span><span class="sxs-lookup"><span data-stu-id="8d249-117">Run the DiscoveryRouter executable.</span></span>  
  
3. <span data-ttu-id="8d249-118">Выполните исполняемый файл службы из каталога сборки.</span><span class="sxs-lookup"><span data-stu-id="8d249-118">Run the service executable from the build directory.</span></span>  
  
4. <span data-ttu-id="8d249-119">Выполните исполняемый файл клиента.</span><span class="sxs-lookup"><span data-stu-id="8d249-119">Run the client executable.</span></span> <span data-ttu-id="8d249-120">Обратите внимание, что клиент нашел службу.</span><span class="sxs-lookup"><span data-stu-id="8d249-120">Note that the client locates the service.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8d249-121">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="8d249-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8d249-122">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="8d249-122">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="8d249-123">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="8d249-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8d249-124">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="8d249-124">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryRouter`
