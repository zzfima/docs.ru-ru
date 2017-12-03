---
title: "Наблюдение за сбоями в работе службы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59472ba3-8ebf-4479-bd7b-f440d5e636cb
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c6030b1ad1dc3953137d3b068be1bceb99975a5f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="monitoring-service-operation-failures"></a><span data-ttu-id="6279a-102">Наблюдение за сбоями в работе службы</span><span class="sxs-lookup"><span data-stu-id="6279a-102">Monitoring Service Operation Failures</span></span>
<span data-ttu-id="6279a-103">Если для приложения включено аналитическое отслеживание, сбои в работе службы можно легко отслеживать в обозревателе событий.</span><span class="sxs-lookup"><span data-stu-id="6279a-103">If analytic tracing is enabled for an application, service failures can easily be monitored in the event viewer.</span></span>  <span data-ttu-id="6279a-104">В этом разделе показано, как определить момент, в который произошел сбой операции службы, и как определить причину сбоя.</span><span class="sxs-lookup"><span data-stu-id="6279a-104">This topic demonstrates how to determine when a service operation fails, and how to determine what caused the failure.</span></span>  
  
### <a name="determining-service-operation-failure-information"></a><span data-ttu-id="6279a-105">Определение сведений о сбое операции службы</span><span class="sxs-lookup"><span data-stu-id="6279a-105">Determining service operation failure information</span></span>  
  
1.  <span data-ttu-id="6279a-106">Откройте средство просмотра событий, щелкнув **запустить**, **запуска**и введя `eventvwr.exe`.</span><span class="sxs-lookup"><span data-stu-id="6279a-106">Open Event Viewer by clicking **Start**, **Run**, and entering `eventvwr.exe`.</span></span>  
  
2.  <span data-ttu-id="6279a-107">Если не включено аналитическое отслеживание, разверните **журналы приложений и служб**, **Microsoft**, **Windows**, **сервер приложений-приложения** .</span><span class="sxs-lookup"><span data-stu-id="6279a-107">If you haven’t enabled analytic tracing, expand **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="6279a-108">Выберите **представление**, **Отобразить аналитический и отладочный журналы**.</span><span class="sxs-lookup"><span data-stu-id="6279a-108">Select **View**, **Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="6279a-109">Щелкните правой кнопкой мыши **аналитический** и выберите **включить журнал**.</span><span class="sxs-lookup"><span data-stu-id="6279a-109">Right-click **Analytic** and select **Enable Log**.</span></span> <span data-ttu-id="6279a-110">Оставьте окно просмотра событий открытым, чтобы можно было просмотреть трассировки после сбоя операции службы.</span><span class="sxs-lookup"><span data-stu-id="6279a-110">Leave Event Viewer open so that traces can be viewed after the service operation fails.</span></span>  
  
3.  <span data-ttu-id="6279a-111">Затем откройте образец, созданные в [учебник по началу работы](../../../../../docs/framework/wcf/getting-started-tutorial.md) в [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] Обратите внимание, что необходимо запустить [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] с правами администратора для создания службы.</span><span class="sxs-lookup"><span data-stu-id="6279a-111">Next, open the sample created in the [Getting Started Tutorial](../../../../../docs/framework/wcf/getting-started-tutorial.md) in [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] Note that you must run [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] as an administrator so that the service can be created.</span></span> <span data-ttu-id="6279a-112">Если у вас есть [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] образцы, устанавливаемые, можно открыть [Приступая к работе](../../../../../docs/framework/wcf/samples/getting-started-sample.md), который содержит завершенный проект, созданный в учебнике.</span><span class="sxs-lookup"><span data-stu-id="6279a-112">If you have the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] samples installed, you can open the [Getting Started](../../../../../docs/framework/wcf/samples/getting-started-sample.md), which contains the completed project created in the tutorial.</span></span>  
  
4.  <span data-ttu-id="6279a-113">В файле Program.cs в проекте «Server» добавьте следующую строку кода к началу метода `Divide` класса `CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="6279a-113">In the Program.cs file in the Server project, add the following line of code to the start of the `Divide` method in the `CalculatorService` class:</span></span>  
  
    ```  
    if (n2 == 0) throw new DivideByZeroException();  
    ```  
  
5.  <span data-ttu-id="6279a-114">В файле Program.cs в проекте «Client» измените значение, назначенное value2, на нуль:</span><span class="sxs-lookup"><span data-stu-id="6279a-114">In the Program.cs file in the Client project, change the value assigned to value2 to zero:</span></span>  
  
    ```  
    //Call the Divide service operation  
    value1 = 22.00D;  
    value2 = 0.00D;  
    result = client.Divide(value1, value2);  
    Console.WriteLine("Divide({0}, {1}) = {2}", value1, value2, result);  
    ```  
  
6.  <span data-ttu-id="6279a-115">Выполните серверное приложение без отладки, нажав **Ctrl + F5**.</span><span class="sxs-lookup"><span data-stu-id="6279a-115">Execute the server application without debugging by pressing **Ctrl+F5**.</span></span>  
  
7.  <span data-ttu-id="6279a-116">Откройте командную строку Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6279a-116">Open a Visual Studio command prompt.</span></span>  <span data-ttu-id="6279a-117">С помощью командной строки перейдите в каталог клиента и запустите клиент.</span><span class="sxs-lookup"><span data-stu-id="6279a-117">Navigate to the client directory and execute the client from the command line.</span></span>  
  
8.  <span data-ttu-id="6279a-118">В окне просмотра событий отключите и обновите аналитический журнал и отсортируйте события по идентификаторам событий.</span><span class="sxs-lookup"><span data-stu-id="6279a-118">In Event Viewer, disable and refresh the Analytic log and sort the events by Event ID.</span></span>  <span data-ttu-id="6279a-119">Найдите событие с кодом события [219 - ServiceException](../../../../../docs/framework/wcf/diagnostics/etw/219-serviceexception.md), которое описывает сбоя службы.</span><span class="sxs-lookup"><span data-stu-id="6279a-119">Look for an event with Event ID [219 - ServiceException](../../../../../docs/framework/wcf/diagnostics/etw/219-serviceexception.md), which describes the service failure.</span></span>  
  
    ```Output  
    There was an unhandled exception of type 'System.DivideByZeroException' during message processing.  Full Exception ToString: System.DivideByZeroException: Attempted to divide by zero.  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="6279a-120">При отправке в обозреватель событий события буферизуются, при этом событие сбоя может не отобразиться сразу.</span><span class="sxs-lookup"><span data-stu-id="6279a-120">Events are buffered when being sent to the event viewer; the failure event may not appear right away.</span></span>
