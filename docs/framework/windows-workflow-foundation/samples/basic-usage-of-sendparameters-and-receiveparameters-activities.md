---
title: Основное использование действий SendParameters и ReceiveParameters
ms.date: 03/30/2017
ms.assetid: 1b6b1681-3d41-403f-bfe2-3f600f24aa8c
ms.openlocfilehash: 8732b10f3f96ccf9ed352f9b54c60a4ee0d1664c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515402"
---
# <a name="basic-usage-of-sendparameters-and-receiveparameters-activities"></a><span data-ttu-id="f938b-102">Основное использование действий SendParameters и ReceiveParameters</span><span class="sxs-lookup"><span data-stu-id="f938b-102">Basic Usage of SendParameters and ReceiveParameters Activities</span></span>
<span data-ttu-id="f938b-103">В этом образце показано использование действий <xref:System.ServiceModel.Activities.SendParametersContent> и <xref:System.ServiceModel.Activities.ReceiveParametersContent>.</span><span class="sxs-lookup"><span data-stu-id="f938b-103">This sample shows the use of <xref:System.ServiceModel.Activities.SendParametersContent> and <xref:System.ServiceModel.Activities.ReceiveParametersContent> activities.</span></span> <span data-ttu-id="f938b-104">Служба предоставляет одну операцию, которая принимает строковый аргумент и возвращает его клиенту.</span><span class="sxs-lookup"><span data-stu-id="f938b-104">The service exposes one operation that takes a string argument and echoes the input back to the client.</span></span> <span data-ttu-id="f938b-105">В образце показано, как установить параметры для этих действий обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="f938b-105">The sample shows how to set up the parameters for these messaging activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f938b-106">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f938b-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f938b-107">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="f938b-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f938b-108">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="f938b-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f938b-109">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="f938b-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\SendReceiveParameters`  
  
#### <a name="using-this-sample"></a><span data-ttu-id="f938b-110">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="f938b-110">Using this sample</span></span>  
  
1.  <span data-ttu-id="f938b-111">Загрузите решение проекта в среду [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] и постройте проект.</span><span class="sxs-lookup"><span data-stu-id="f938b-111">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="f938b-112">Сначала запустите приложение EchoWorkflowService, сформированное в [основной каталог решения]\EchoWorkflowService\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="f938b-112">First run the EchoWorkflowService application generated in [solution base directory]\EchoWorkflowService\bin\debug.</span></span>  
  
3.  <span data-ttu-id="f938b-113">Затем запустите приложение EchoWorkflowClient, сформированное в [основной каталог решения]\EchoWorkflowClient\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="f938b-113">Second, run the EchoWorkflowClient application generated in [solution base directory]\EchoWorkflowClient\bin\debug.</span></span>  
  
4.  <span data-ttu-id="f938b-114">Клиент вызывает операцию Echo на службе и печатает результаты.</span><span class="sxs-lookup"><span data-stu-id="f938b-114">The client calls Echo operation on the service and prints the results.</span></span> <span data-ttu-id="f938b-115">После завершения нажмите клавишу ВВОД, чтобы закрыть клиент и службу.</span><span class="sxs-lookup"><span data-stu-id="f938b-115">When complete, press ENTER to exit the client and then the service.</span></span>