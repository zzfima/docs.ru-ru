---
title: Сбои при отправке и обработке
ms.date: 03/30/2017
ms.assetid: 98e8e04d-2ac9-4a33-ae08-462f757a7a14
ms.openlocfilehash: 6796b4daccd88adc3bd006f454ce96ca155fbcb3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516130"
---
# <a name="sending-and-handling-faults"></a><span data-ttu-id="df220-102">Сбои при отправке и обработке</span><span class="sxs-lookup"><span data-stu-id="df220-102">Sending and Handling Faults</span></span>
<span data-ttu-id="df220-103">В этом образце демонстрируется использование действий обмена сообщениями <xref:System.ServiceModel.Activities.SendReply> и <xref:System.ServiceModel.Activities.ReceiveReply> для отправки и получения сообщений об ожидаемых и непредвиденных ошибках.</span><span class="sxs-lookup"><span data-stu-id="df220-103">This sample demonstrates how to use the <xref:System.ServiceModel.Activities.SendReply> and <xref:System.ServiceModel.Activities.ReceiveReply> messaging activities to send and receive expected and unexpected faults.</span></span> <span data-ttu-id="df220-104">В этом сценарии первый запрос клиента дает в результате ожидаемую ошибку, которая была включена в коллекцию <xref:System.ServiceModel.Activities.Send.KnownTypes%2A>.</span><span class="sxs-lookup"><span data-stu-id="df220-104">In this scenario, the first client request results in an expected fault that has been included in its <xref:System.ServiceModel.Activities.Send.KnownTypes%2A> collection.</span></span> <span data-ttu-id="df220-105">Следующие несколько запросов клиентов приводят к получению непредвиденных ошибок, после чего последний запрос дает положительный результат.</span><span class="sxs-lookup"><span data-stu-id="df220-105">The next few client requests result in receiving unexpected faults, before the final request succeeds.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="df220-106">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="df220-106">To use this sample</span></span>  
  
1.  <span data-ttu-id="df220-107">Откройте [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] с повышенными разрешениями, щелкнув правой кнопкой мыши [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] значок и выбрав **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="df220-107">Open [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with elevated permissions, by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="df220-108">Откройте файл решения Faults.sln.</span><span class="sxs-lookup"><span data-stu-id="df220-108">Open the Faults.sln solution file.</span></span>  
  
3.  <span data-ttu-id="df220-109">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="df220-109">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="df220-110">Запустите проект службы.</span><span class="sxs-lookup"><span data-stu-id="df220-110">Run the service project.</span></span>  
  
    1.  <span data-ttu-id="df220-111">В **обозревателе решений**, щелкните правой кнопкой мыши `FaultService` проект и выберите **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="df220-111">In **Solution Explorer**, right-click the `FaultService` project and select **Set as StartUp Project**.</span></span>  
  
    2.  <span data-ttu-id="df220-112">Нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="df220-112">Press CTRL+F5.</span></span>  
  
5.  <span data-ttu-id="df220-113">Откройте другую копию [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] с повышенными разрешениями, щелкнув правой кнопкой мыши [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] значок и выбрав **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="df220-113">Open another copy of [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with elevated permissions, by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
6.  <span data-ttu-id="df220-114">Откройте файл решения Faults.sln.</span><span class="sxs-lookup"><span data-stu-id="df220-114">Open the Faults.sln solution file.</span></span>  
  
7.  <span data-ttu-id="df220-115">Запустите клиентский проект.</span><span class="sxs-lookup"><span data-stu-id="df220-115">Run the client project.</span></span>  
  
    1.  <span data-ttu-id="df220-116">В **обозревателе решений**, щелкните правой кнопкой мыши `FaultClient` проект и выберите **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="df220-116">In **Solution Explorer**, right-click the `FaultClient` project and select **Set as StartUp Project**.</span></span>  
  
    2.  <span data-ttu-id="df220-117">Нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="df220-117">Press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="df220-118">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="df220-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="df220-119">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="df220-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="df220-120">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="df220-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="df220-121">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="df220-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Faults`