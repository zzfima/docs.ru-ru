---
title: Локальный канал
ms.date: 03/30/2017
ms.assetid: fa1917a4-f701-4e82-a439-14a16282c7cc
ms.openlocfilehash: 87e140395ac2fb5702d8655cf970da8a60c991ec
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144511"
---
# <a name="local-channel"></a><span data-ttu-id="3df09-102">Локальный канал</span><span class="sxs-lookup"><span data-stu-id="3df09-102">Local Channel</span></span>
<span data-ttu-id="3df09-103">Локальный канал является транспортным каналом Фонда связи Windows (WCF), который используется для связи в одном домене приложения.</span><span class="sxs-lookup"><span data-stu-id="3df09-103">Local Channel is a Windows Communication Foundation (WCF) transport channel that is used for communication within the same application domain.</span></span> <span data-ttu-id="3df09-104">Это полезно в случаях, когда клиент и служба работают на одном домене приложения и требуется избежать увеличения расхода ресурсов типичного WCF-канала (сериализация и десериализация сообщений).</span><span class="sxs-lookup"><span data-stu-id="3df09-104">This is useful for scenarios where the client and the service are running in the same application domain and the overhead of the typical WCF channel stack (serialization and deserialization of messages) must be avoided.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="3df09-105">Что демонстрирует</span><span class="sxs-lookup"><span data-stu-id="3df09-105">Demonstrates</span></span>  
 <span data-ttu-id="3df09-106">Локальный канал</span><span class="sxs-lookup"><span data-stu-id="3df09-106">Local Channel</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="3df09-107">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="3df09-107">Discussion</span></span>  
 <span data-ttu-id="3df09-108">Образец состоит из двух файлов проектов:</span><span class="sxs-lookup"><span data-stu-id="3df09-108">The sample consists of two project files:</span></span>  
  
- <span data-ttu-id="3df09-109">**LocalChannel**: Программное представление локального канала в рамках текущего домена приложения.</span><span class="sxs-lookup"><span data-stu-id="3df09-109">**LocalChannel**: The programmatic representation of the local channel within the current application domain.</span></span> <span data-ttu-id="3df09-110">В этом проекте отправляющий модуль размещает сообщение в очереди памяти, а получающий модуль выводит его из очереди, получая сообщение.</span><span class="sxs-lookup"><span data-stu-id="3df09-110">In this project, the sending component places the message in an in-memory queue and the receiving component de-queues the message to receive it.</span></span>  
  
- <span data-ttu-id="3df09-111">**ClientAndService**: Этот проект размещает службу в консольном приложении, а затем запускает клиента для вызова службы из одного и того же домена приложения.</span><span class="sxs-lookup"><span data-stu-id="3df09-111">**ClientAndService**: This project hosts a service in a console application and then runs a client to call the service from within the same application domain.</span></span>  
  
 <span data-ttu-id="3df09-112">Конструктор локального канала пропускает стек каналов и процесс сериализации для увеличения скорости.</span><span class="sxs-lookup"><span data-stu-id="3df09-112">The local channel design skips both the channel stack and the serialization process to increase speed.</span></span> <span data-ttu-id="3df09-113">Локальный канал транспорта реализуется при помощи очереди, которая используется для переноса вызовов службы от клиента к службе и возвращения значения клиенту.</span><span class="sxs-lookup"><span data-stu-id="3df09-113">The local transport channel is implemented using a queue to transport service calls from the client to the service and to return back the value to the client.</span></span> <span data-ttu-id="3df09-114">Вместо сериализации параметров и возвращения значений образец копирует объекты.</span><span class="sxs-lookup"><span data-stu-id="3df09-114">Rather than serializing parameters and return values, the sample copies the objects.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3df09-115">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="3df09-115">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="3df09-116">Постройте и запустите решение LocalChannel.</span><span class="sxs-lookup"><span data-stu-id="3df09-116">Build and run the LocalChannel solution.</span></span>  
  
2. <span data-ttu-id="3df09-117">Запускается узел службы, клиент вызывает службу при помощи локального канала.</span><span class="sxs-lookup"><span data-stu-id="3df09-117">The service host is started and the client calls the service using the local channel.</span></span> <span data-ttu-id="3df09-118">Появляется окно консоли, в котором отображаются результаты вызова службы.</span><span class="sxs-lookup"><span data-stu-id="3df09-118">A console window appears to display the results of the service call.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3df09-119">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3df09-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3df09-120">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="3df09-120">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="3df09-121">Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы.</span><span class="sxs-lookup"><span data-stu-id="3df09-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3df09-122">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3df09-122">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\LocalChannel`
