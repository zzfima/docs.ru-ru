---
title: Сбои при отправке и обработке
ms.date: 03/30/2017
ms.assetid: 98e8e04d-2ac9-4a33-ae08-462f757a7a14
ms.openlocfilehash: 896f209e7daeeab2bb33c1fde15298aae96c8776
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "44037715"
---
# <a name="sending-and-handling-faults"></a><span data-ttu-id="eadde-102">Сбои при отправке и обработке</span><span class="sxs-lookup"><span data-stu-id="eadde-102">Sending and Handling Faults</span></span>
<span data-ttu-id="eadde-103">В этом образце демонстрируется использование действий обмена сообщениями <xref:System.ServiceModel.Activities.SendReply> и <xref:System.ServiceModel.Activities.ReceiveReply> для отправки и получения сообщений об ожидаемых и непредвиденных ошибках.</span><span class="sxs-lookup"><span data-stu-id="eadde-103">This sample demonstrates how to use the <xref:System.ServiceModel.Activities.SendReply> and <xref:System.ServiceModel.Activities.ReceiveReply> messaging activities to send and receive expected and unexpected faults.</span></span> <span data-ttu-id="eadde-104">В этом сценарии первый запрос клиента дает в результате ожидаемую ошибку, которая была включена в коллекцию <xref:System.ServiceModel.Activities.Send.KnownTypes%2A>.</span><span class="sxs-lookup"><span data-stu-id="eadde-104">In this scenario, the first client request results in an expected fault that has been included in its <xref:System.ServiceModel.Activities.Send.KnownTypes%2A> collection.</span></span> <span data-ttu-id="eadde-105">Следующие несколько запросов клиентов приводят к получению непредвиденных ошибок, после чего последний запрос дает положительный результат.</span><span class="sxs-lookup"><span data-stu-id="eadde-105">The next few client requests result in receiving unexpected faults, before the final request succeeds.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="eadde-106">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="eadde-106">To use this sample</span></span>  
  
1.  <span data-ttu-id="eadde-107">Откройте [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] с повышенным уровнем разрешений, щелкните правой кнопкой мыши [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] значок и выбрав **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="eadde-107">Open [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with elevated permissions, by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="eadde-108">Откройте файл решения Faults.sln.</span><span class="sxs-lookup"><span data-stu-id="eadde-108">Open the Faults.sln solution file.</span></span>  
  
3.  <span data-ttu-id="eadde-109">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="eadde-109">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="eadde-110">Запустите проект службы.</span><span class="sxs-lookup"><span data-stu-id="eadde-110">Run the service project.</span></span>  
  
    1.  <span data-ttu-id="eadde-111">В **обозревателе решений**, щелкните правой кнопкой мыши `FaultService` проекта и выберите **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="eadde-111">In **Solution Explorer**, right-click the `FaultService` project and select **Set as StartUp Project**.</span></span>  
  
    2.  <span data-ttu-id="eadde-112">Нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="eadde-112">Press CTRL+F5.</span></span>  
  
5.  <span data-ttu-id="eadde-113">Откройте другую копию [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] с повышенным уровнем разрешений, щелкните правой кнопкой мыши [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] значок и выбрав **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="eadde-113">Open another copy of [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with elevated permissions, by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
6.  <span data-ttu-id="eadde-114">Откройте файл решения Faults.sln.</span><span class="sxs-lookup"><span data-stu-id="eadde-114">Open the Faults.sln solution file.</span></span>  
  
7.  <span data-ttu-id="eadde-115">Запустите клиентский проект.</span><span class="sxs-lookup"><span data-stu-id="eadde-115">Run the client project.</span></span>  
  
    1.  <span data-ttu-id="eadde-116">В **обозревателе решений**, щелкните правой кнопкой мыши `FaultClient` проекта и выберите **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="eadde-116">In **Solution Explorer**, right-click the `FaultClient` project and select **Set as StartUp Project**.</span></span>  
  
    2.  <span data-ttu-id="eadde-117">Нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="eadde-117">Press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="eadde-118">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="eadde-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="eadde-119">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="eadde-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="eadde-120">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="eadde-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="eadde-121">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="eadde-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Faults`