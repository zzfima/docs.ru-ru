---
title: "Надежный защищенный профиль"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 921edc41-e91b-40f9-bde9-b6148b633e61
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 89a6d5c2e485699a55c77797c34eaca2c9848c40
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="reliable-secure-profile"></a><span data-ttu-id="917df-102">Надежный защищенный профиль</span><span class="sxs-lookup"><span data-stu-id="917df-102">Reliable Secure Profile</span></span>
<span data-ttu-id="917df-103">В этом примере показано, как составлять [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и [надежному защищенному профилю](http://go.microsoft.com/fwlink/?LinkId=178140) (RSP).</span><span class="sxs-lookup"><span data-stu-id="917df-103">This sample demonstrates how to compose [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and [Reliable Secure Profile](http://go.microsoft.com/fwlink/?LinkId=178140) (RSP).</span></span> <span data-ttu-id="917df-104">Этот образец демонстрирует реализацию [Создание подключения](http://go.microsoft.com/fwlink/?LinkId=178141) канала, который может формироваться вместе с надежного обмена сообщениями и при необходимости безопасного канала для создания надежных защищенную привязку на основе RSP спецификации.</span><span class="sxs-lookup"><span data-stu-id="917df-104">This sample demonstrates the implementation of a [Make Connection](http://go.microsoft.com/fwlink/?LinkId=178141) channel which can be composed together with Reliable Messaging and optionally a secure channel to create a Reliable Secure Binding based on the RSP specification.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="917df-105">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="917df-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="917df-106">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="917df-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="917df-107">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="917df-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="917df-108">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="917df-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\ReliableSecureProfile`  
  
## <a name="discussion"></a><span data-ttu-id="917df-109">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="917df-109">Discussion</span></span>  
 <span data-ttu-id="917df-110">В этом образце показан сценарий с надежным двусторонним асинхронным обменом сообщениями.</span><span class="sxs-lookup"><span data-stu-id="917df-110">This sample demonstrates a reliable asynchronous two-way message exchange scenario.</span></span> <span data-ttu-id="917df-111">Служба имеет дуплексный контракт, а в клиенте реализован дуплексный контракт обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="917df-111">The service has a duplex contract and the client implements the duplex callback contract.</span></span> <span data-ttu-id="917df-112">Клиент создает запрос к службе, а ответ ожидается по отдельному соединению.</span><span class="sxs-lookup"><span data-stu-id="917df-112">The client initiates a request to a service, for which a response is expected on a separate connection.</span></span> <span data-ttu-id="917df-113">Сообщение запроса отправляется надежным образом.</span><span class="sxs-lookup"><span data-stu-id="917df-113">The request message is sent reliably.</span></span> <span data-ttu-id="917df-114">Клиент не открывает со своей стороны конечную точку прослушивания.</span><span class="sxs-lookup"><span data-stu-id="917df-114">The client does not want to open a listening endpoint at its end.</span></span> <span data-ttu-id="917df-115">Поэтому он отправляет службе запросы «Make Connection», чтобы служба отправляла ответ по обратному каналу для таких запросов.</span><span class="sxs-lookup"><span data-stu-id="917df-115">Thus, it polls the service with ‘Make Connection’ requests for the service to send back the response on the back channel of this ‘Make Connection’ request.</span></span> <span data-ttu-id="917df-116">В этом образце показано, как организовать защищенную надежную дуплексную связь по HTTP без предоставления конечной точки прослушивания на клиенте (и без создания исключения брандмауэра).</span><span class="sxs-lookup"><span data-stu-id="917df-116">This sample demonstrates how to have secure reliable duplex communication over HTTP without the client exposing a listening endpoint (and creating a firewall exception).</span></span>  
  
## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="917df-117">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="917df-117">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="917df-118">Откройте **ReliableSecureProfile** решения.</span><span class="sxs-lookup"><span data-stu-id="917df-118">Open the **ReliableSecureProfile** solution.</span></span>  
  
2.  <span data-ttu-id="917df-119">Щелкните правой кнопкой мыши **службы** проекта в **обозревателе решений**выберите **отладки**, **запустить новый экземпляр** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="917df-119">Right click the **Service** project in **Solution Explorer**, select **Debug**, **Start new instance** from the context menu.</span></span> <span data-ttu-id="917df-120">Запустится узел службы.</span><span class="sxs-lookup"><span data-stu-id="917df-120">This starts up the service host.</span></span>  
  
3.  <span data-ttu-id="917df-121">Щелкните правой кнопкой мыши **клиента** проекта в **обозревателе решений**выберите **отладки**, **запустить новый экземпляр** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="917df-121">Right click the **Client** project in **Solution Explorer**, select **Debug**, **Start new instance** from the context menu.</span></span> <span data-ttu-id="917df-122">Запустится клиент.</span><span class="sxs-lookup"><span data-stu-id="917df-122">This starts up the client.</span></span>  
  
4.  <span data-ttu-id="917df-123">Введите в окне консоли клиента любую строку и нажмите клавишу ВВОД. Введенная строка отправится в службу, которая вычислит для нее хэш.</span><span class="sxs-lookup"><span data-stu-id="917df-123">Type in any string in the prompt on the client console window and click ENTER.This sends the input string to the service, which computes a hash of this string.</span></span>  
  
5.  <span data-ttu-id="917df-124">Просмотрите результат в окне клиента, когда служба выполняет обратный вызов дуплексной операции контракта, чтобы вывести результат в окно консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="917df-124">View the result on the client windows when the service calls back the duplex callback contract operation to display the result on the client console window.</span></span> <span data-ttu-id="917df-125">Со стороны службы специально реализована задержка, имитирующая продолжительную операцию по обработке данных.</span><span class="sxs-lookup"><span data-stu-id="917df-125">There is an intentional delay on the service to simulate a long running operation of processing the data.</span></span>  
  
6.  <span data-ttu-id="917df-126">Наблюдение за HTTP-трафиком (в любом из средств оперативного наблюдения за сетью, например сетевом мониторе, Fiddler и т. п.) показывает, что последовательность связи устанавливается между клиентом и службой согласно надежному защищенному профилю, а клиент отправляет службе запросы «Make Connection».</span><span class="sxs-lookup"><span data-stu-id="917df-126">Monitoring the HTTP traffic (by any of the online network monitoring tools like Network Monitor, Fiddler and so on) shows that a sequence for communication is established between the client and the service as laid down by the Reliable Secure Profile, and how the client polls the service with ‘Make Connection’ requests.</span></span> <span data-ttu-id="917df-127">Когда служба готова к отправке обработанного ответа, она использует для отправки результатов обратный канал последнего запроса «Make Connection».</span><span class="sxs-lookup"><span data-stu-id="917df-127">When the service gets ready to send back the processed response, it uses the back channel of the last ‘Make Connection’ request to send back the results.</span></span>  
  
7.  <span data-ttu-id="917df-128">Нажмите в окне консоли службы клавишу ВВОД, чтобы закрыть службу.</span><span class="sxs-lookup"><span data-stu-id="917df-128">Press ENTER on the service console window to close the service.</span></span> <span data-ttu-id="917df-129">Нажмите клавишу ВВОД в окне консоли клиента, чтобы закрыть клиент.</span><span class="sxs-lookup"><span data-stu-id="917df-129">Press ENTER on the client console window to close the client.</span></span>
