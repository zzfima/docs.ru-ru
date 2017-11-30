---
title: "Форматирование сообщений в службах рабочего процесса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d15d44b-20f8-4cb7-bd4f-598c32781ebc
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d2367f4fe4ebe576eb9a5e2f707eb043e5ee7ccb
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2017
---
# <a name="formatting-messages-in-workflow-services"></a><span data-ttu-id="3aa7c-102">Форматирование сообщений в службах рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="3aa7c-102">Formatting messages in Workflow Services</span></span>
<span data-ttu-id="3aa7c-103">В этом образце показано, как использовать различные пользовательские типы в действиях обмена сообщениями (в службах WF).</span><span class="sxs-lookup"><span data-stu-id="3aa7c-103">This sample shows how different user types can be used in messaging activities (WF services).</span></span> <span data-ttu-id="3aa7c-104">Образец показывает простую службу утверждения затрат. Он представляет три операции.</span><span class="sxs-lookup"><span data-stu-id="3aa7c-104">The sample service is a simple expense approval service and exposes three operations.</span></span> <span data-ttu-id="3aa7c-105">`ApproveExpense` принимает значение типа контракта данных и показывает, как использовать известные типы.</span><span class="sxs-lookup"><span data-stu-id="3aa7c-105">`ApproveExpense` takes a data contract type and shows how to use known types.</span></span> <span data-ttu-id="3aa7c-106">Операция возвращает значение `true` или `false` в зависимости от суммы затрат.</span><span class="sxs-lookup"><span data-stu-id="3aa7c-106">The operation returns `true` or `false` based on the expense amount.</span></span> <span data-ttu-id="3aa7c-107">`ApprovePO`принимает значение типа XmlSerializer и возвращает `true` или `false` зависимости от суммы затрат.`ApprovedVendor`</span><span class="sxs-lookup"><span data-stu-id="3aa7c-107">`ApprovePO` takes an XmlSerializer type and returns `true` or `false` based on the expense amount.`ApprovedVendor`</span></span> <span data-ttu-id="3aa7c-108">Получает тип контракта сообщения и возвращает `true` или `false` Если поставщик имеется в списке утвержденных поставщиков или если запрос прибыл из финансового отдела (финансовый отдел может использовать любого поставщика).</span><span class="sxs-lookup"><span data-stu-id="3aa7c-108">takes a message contract type and returns `true` or `false` if the vendor is in the list of approved vendors or if the request came from the finance department (the finance department can use any vendor).</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="3aa7c-109">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="3aa7c-109">To use this sample</span></span>  
  
1.  <span data-ttu-id="3aa7c-110">Загрузите решение проекта в среду [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] и постройте проект.</span><span class="sxs-lookup"><span data-stu-id="3aa7c-110">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="3aa7c-111">Вначале запустите службу, созданную в каталоге [базовый каталог решений]\FormatterService\bin\debug\.</span><span class="sxs-lookup"><span data-stu-id="3aa7c-111">First run the service, generated in [solution base directory]\FormatterService\bin\debug\\</span></span>  
  
3.  <span data-ttu-id="3aa7c-112">Затем запустите клиентское приложение, созданное в каталоге [базовый каталог решений]\FormatterClient\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="3aa7c-112">Second, run the Client application generated in [solution base directory]\FormatterClient\bin\debug.</span></span>  
  
4.  <span data-ttu-id="3aa7c-113">Клиент вызывает три операции службы и печатает результаты.</span><span class="sxs-lookup"><span data-stu-id="3aa7c-113">The client calls three operations on the service and prints the results.</span></span> <span data-ttu-id="3aa7c-114">После завершения нажмите клавишу ВВОД, чтобы закрыть клиент и службу.</span><span class="sxs-lookup"><span data-stu-id="3aa7c-114">When complete, press ENTER to exit the client and then the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3aa7c-115">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3aa7c-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3aa7c-116">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="3aa7c-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3aa7c-117">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3aa7c-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3aa7c-118">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3aa7c-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Formatter`