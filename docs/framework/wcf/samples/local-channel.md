---
title: Локальный канал
ms.date: 03/30/2017
ms.assetid: fa1917a4-f701-4e82-a439-14a16282c7cc
ms.openlocfilehash: 2473704c751ad0ea2d2a00bf7f3ea43d6e39498f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="local-channel"></a><span data-ttu-id="43c60-102">Локальный канал</span><span class="sxs-lookup"><span data-stu-id="43c60-102">Local Channel</span></span>
<span data-ttu-id="43c60-103">Локальный канал находится канал транспорта Windows Communication Foundation (WCF), используемый для обмена данными в том же домене приложения.</span><span class="sxs-lookup"><span data-stu-id="43c60-103">Local Channel is a Windows Communication Foundation (WCF) transport channel that is used for communication within the same application domain.</span></span> <span data-ttu-id="43c60-104">Это полезно в случаях, когда клиент и служба работают на одном домене приложения и требуется избежать увеличения расхода ресурсов типичного WCF-канала (сериализация и десериализация сообщений).</span><span class="sxs-lookup"><span data-stu-id="43c60-104">This is useful for scenarios where the client and the service are running in the same application domain and the overhead of the typical WCF channel stack (serialization and deserialization of messages) must be avoided.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="43c60-105">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="43c60-105">Demonstrates</span></span>  
 <span data-ttu-id="43c60-106">Локальный канал</span><span class="sxs-lookup"><span data-stu-id="43c60-106">Local Channel</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="43c60-107">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="43c60-107">Discussion</span></span>  
 <span data-ttu-id="43c60-108">Образец состоит из двух файлов проектов:</span><span class="sxs-lookup"><span data-stu-id="43c60-108">The sample consists of two project files:</span></span>  
  
-   <span data-ttu-id="43c60-109">**LocalChannel**: программное представление локального канала внутри текущего домена приложения.</span><span class="sxs-lookup"><span data-stu-id="43c60-109">**LocalChannel**: The programmatic representation of the local channel within the current application domain.</span></span> <span data-ttu-id="43c60-110">В этом проекте отправляющий модуль размещает сообщение в очереди памяти, а получающий модуль выводит его из очереди, получая сообщение.</span><span class="sxs-lookup"><span data-stu-id="43c60-110">In this project, the sending component places the message in an in-memory queue and the receiving component de-queues the message to receive it.</span></span>  
  
-   <span data-ttu-id="43c60-111">**ClientAndService**: этот проект размещает службу в консольном приложении и затем запускает клиент, чтобы вызвать службу из того же домена приложения.</span><span class="sxs-lookup"><span data-stu-id="43c60-111">**ClientAndService**: This project hosts a service in a console application and then runs a client to call the service from within the same application domain.</span></span>  
  
 <span data-ttu-id="43c60-112">Конструктор локального канала пропускает стек каналов и процесс сериализации для увеличения скорости.</span><span class="sxs-lookup"><span data-stu-id="43c60-112">The local channel design skips both the channel stack and the serialization process to increase speed.</span></span> <span data-ttu-id="43c60-113">Локальный канал транспорта реализуется при помощи очереди, которая используется для переноса вызовов службы от клиента к службе и возвращения значения клиенту.</span><span class="sxs-lookup"><span data-stu-id="43c60-113">The local transport channel is implemented using a queue to transport service calls from the client to the service and to return back the value to the client.</span></span> <span data-ttu-id="43c60-114">Вместо сериализации параметров и возвращения значений образец копирует объекты.</span><span class="sxs-lookup"><span data-stu-id="43c60-114">Rather than serializing parameters and return values, the sample copies the objects.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="43c60-115">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="43c60-115">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="43c60-116">Постройте и запустите решение LocalChannel.</span><span class="sxs-lookup"><span data-stu-id="43c60-116">Build and run the LocalChannel solution.</span></span>  
  
2.  <span data-ttu-id="43c60-117">Запускается узел службы, клиент вызывает службу при помощи локального канала.</span><span class="sxs-lookup"><span data-stu-id="43c60-117">The service host is started and the client calls the service using the local channel.</span></span> <span data-ttu-id="43c60-118">Появляется окно консоли, в котором отображаются результаты вызова службы.</span><span class="sxs-lookup"><span data-stu-id="43c60-118">A console window appears to display the results of the service call.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="43c60-119">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="43c60-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="43c60-120">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="43c60-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="43c60-121">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="43c60-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="43c60-122">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="43c60-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\LocalChannel`
