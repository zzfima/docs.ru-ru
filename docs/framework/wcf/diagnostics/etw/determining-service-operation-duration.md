---
title: "Определение продолжительности выполнения для операции службы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 63a8c92713ee452da2439475ac526229d1e5741c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="determining-service-operation-duration"></a><span data-ttu-id="ba975-102">Определение продолжительности выполнения для операции службы</span><span class="sxs-lookup"><span data-stu-id="ba975-102">Determining service operation duration</span></span>
<span data-ttu-id="ba975-103">Если в приложении [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] включена аналитическая трассировка, то продолжительность выполнения операции службы легко определить по журналу событий.</span><span class="sxs-lookup"><span data-stu-id="ba975-103">If analytic tracing is enabled in a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] application, the duration of execution for a service operation can easily be determined by examining the event log.</span></span>  <span data-ttu-id="ba975-104">В этом разделе показано, как определить время, затраченное на выполнение операции службы.</span><span class="sxs-lookup"><span data-stu-id="ba975-104">This topic demonstrates how to determine the amount of time a service operation takes to complete.</span></span>  
  
### <a name="determining-service-operation-execution-duration"></a><span data-ttu-id="ba975-105">Определение продолжительности выполнения для операции службы</span><span class="sxs-lookup"><span data-stu-id="ba975-105">Determining service operation execution duration</span></span>  
  
1.  <span data-ttu-id="ba975-106">Откройте средство просмотра событий, щелкнув **запустить**, **запуска**и введя `eventvwr.exe`.</span><span class="sxs-lookup"><span data-stu-id="ba975-106">Open Event Viewer by clicking **Start**, **Run**, and entering `eventvwr.exe`.</span></span>  
  
2.  <span data-ttu-id="ba975-107">Если не включено аналитическое отслеживание, разверните **журналы приложений и служб**, **Microsoft**, **Windows**, **сервер приложений-приложения** .</span><span class="sxs-lookup"><span data-stu-id="ba975-107">If you haven’t enabled analytic tracing, expand **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="ba975-108">Выберите **представление**, **Отобразить аналитический и отладочный журналы**.</span><span class="sxs-lookup"><span data-stu-id="ba975-108">Select **View**, **Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="ba975-109">Щелкните правой кнопкой мыши **аналитический** и выберите **включить журнал**.</span><span class="sxs-lookup"><span data-stu-id="ba975-109">Right-click **Analytic** and select **Enable Log**.</span></span> <span data-ttu-id="ba975-110">Оставьте окно просмотра событий открытым, чтобы можно было просмотреть трассировки после выполнения операции службы.</span><span class="sxs-lookup"><span data-stu-id="ba975-110">Leave Event Viewer open so that traces can be viewed after the service operation is run.</span></span>  
  
3.  <span data-ttu-id="ba975-111">Затем откройте приложение [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], в которое входит проект службы и проект клиента, который взаимодействует с этой службой.</span><span class="sxs-lookup"><span data-stu-id="ba975-111">Next, open a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] application that includes a service project and a client project that interacts with that service.</span></span>  <span data-ttu-id="ba975-112">Можно создать такое приложение, выполнив [учебник по началу работы](../../../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="ba975-112">You can create such an application by following the [Getting Started Tutorial](../../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>  <span data-ttu-id="ba975-113">Если у вас есть [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] образцы, устанавливаемые, можно открыть [Приступая к работе](../../../../../docs/framework/wcf/samples/getting-started-sample.md), который содержит завершенный проект, созданный в учебнике.</span><span class="sxs-lookup"><span data-stu-id="ba975-113">If you have the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] samples installed, you can open the [Getting Started](../../../../../docs/framework/wcf/samples/getting-started-sample.md), which contains the completed project created in the tutorial.</span></span>  
  
4.  <span data-ttu-id="ba975-114">Выполните серверное приложение, нажав клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="ba975-114">Execute the server application by pressing **F5**.</span></span> <span data-ttu-id="ba975-115">Запустите клиентское приложение, щелкнув правой кнопкой мыши **клиента** проекта и выбрав **отладки**, **запустить новый экземпляр**.</span><span class="sxs-lookup"><span data-stu-id="ba975-115">Execute the client application by right-clicking on the **Client** project and selecting **Debug**, **Start New Instance**.</span></span>  
  
5.  <span data-ttu-id="ba975-116">В окне просмотра событий обновите аналитический журнал и отсортируйте события по идентификатору события.</span><span class="sxs-lookup"><span data-stu-id="ba975-116">In Event Viewer, refresh the Analytic log and sort the events by Event ID.</span></span>  <span data-ttu-id="ba975-117">Найдите события с кодом события [214 - OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md).</span><span class="sxs-lookup"><span data-stu-id="ba975-117">Look for events with Event ID [214 - OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md).</span></span>  <span data-ttu-id="ba975-118">В этих событиях показано, какие операции выполнены, и указана продолжительность операции.</span><span class="sxs-lookup"><span data-stu-id="ba975-118">These events will show which operations have completed, and what the duration of the operation was.</span></span>  <span data-ttu-id="ba975-119">В следующем событии показана продолжительность операции Add.</span><span class="sxs-lookup"><span data-stu-id="ba975-119">The following event shows the duration of an Add operation.</span></span>  
  
    ```Output  
    An OperationInvoker completed the call to the 'Add' method.  The method call duration was '3' ms.  
    ```
