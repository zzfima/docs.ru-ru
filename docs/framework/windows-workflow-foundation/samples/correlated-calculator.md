---
title: "Калькулятор с корреляцией"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c365166e-6552-49a4-bf17-9f4e597d4d41
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f6296ecb5c708d344624cac6e24247d2163fd66b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="correlated-calculator"></a><span data-ttu-id="2a7c4-102">Калькулятор с корреляцией</span><span class="sxs-lookup"><span data-stu-id="2a7c4-102">Correlated Calculator</span></span>
<span data-ttu-id="2a7c4-103">В этом образце демонстрируется, как действия по обмену сообщениями (<xref:System.ServiceModel.Activities.Receive> и <xref:System.ServiceModel.Activities.SendReply>) могут использоваться в конструкторе с корреляцией на основе содержимого в зависимости от параметра в сообщении.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-103">This sample demonstrates how to use the messaging activities (<xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply>) in the designer with content-based correlation based on a parameter in the message.</span></span> <span data-ttu-id="2a7c4-104">В этом сценарии операции калькулятора находятся в параллельном сопровождении.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-104">In this scenario, the operations of the calculator are in a parallel convoy.</span></span> <span data-ttu-id="2a7c4-105">Экземпляр и корреляция (на основе `CalculatorId`) создаются после отправки первого сообщения в рабочий процесс, и последующие сообщения с тем же `CalculatorId` отправляются на тот же экземпляр до вызова операции сброса.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-105">Both an instance and a correlation (based on `CalculatorId`) are created when the first message is sent to the workflow, and subsequent messages with the same `CalculatorId` are dispatched to that instance until the Reset operation is called.</span></span> <span data-ttu-id="2a7c4-106">Клиент реализуется в виде приложения WPF, использующего основанный на коде прокси-агент клиента для взаимодействия со службой.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-106">The client is implemented as a WPF application that uses a code-based client proxy to communicate with the service.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="2a7c4-107">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="2a7c4-107">To use this sample</span></span>  
  
1.  <span data-ttu-id="2a7c4-108">Запустите [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] с повышенными разрешениями, откройте файл решения For.sln.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-108">Start [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] in elevated permissions, open the For.sln solution file.</span></span>  
  
    1.  <span data-ttu-id="2a7c4-109">Перейдите в папку, содержащую [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a7c4-109">Navigate to the folder that contains [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
    2.  <span data-ttu-id="2a7c4-110">Щелкните правой кнопкой Devenv.exe и выберите **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-110">Right-click Devenv.exe and select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="2a7c4-111">Используя [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], откройте файл решения CorrelatedCalculator.sln.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-111">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the CorrelatedCalculator.sln solution file.</span></span>  
  
3.  <span data-ttu-id="2a7c4-112">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-112">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="2a7c4-113">Нажмите клавиши Ctrl + F5, чтобы запустить проект службы.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-113">To run the service project, press CTRL+F5.</span></span>  
  
5.  <span data-ttu-id="2a7c4-114">После того как служба готова к прослушиванию сообщений, щелкните правой кнопкой мыши проект «Клиент» в обозревателе решений и запустите его.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-114">Once the service is ready and listening for messages, in Solution Explorer, right-click the Client project and run it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2a7c4-115">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2a7c4-116">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="2a7c4-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2a7c4-117">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2a7c4-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2a7c4-118">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="2a7c4-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\CorellatedCalculator`