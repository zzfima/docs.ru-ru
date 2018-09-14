---
title: Форматирование сообщений в службах рабочего процесса
ms.date: 03/30/2017
ms.assetid: 6d15d44b-20f8-4cb7-bd4f-598c32781ebc
ms.openlocfilehash: eb9a6b3a83a28154dc968bd4c1c41d34028bdd41
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45590199"
---
# <a name="formatting-messages-in-workflow-services"></a><span data-ttu-id="9964f-102">Форматирование сообщений в службах рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="9964f-102">Formatting messages in Workflow Services</span></span>
<span data-ttu-id="9964f-103">В этом образце показано, как использовать различные пользовательские типы в действиях обмена сообщениями (в службах WF).</span><span class="sxs-lookup"><span data-stu-id="9964f-103">This sample shows how different user types can be used in messaging activities (WF services).</span></span> <span data-ttu-id="9964f-104">Образец показывает простую службу утверждения затрат. Он представляет три операции.</span><span class="sxs-lookup"><span data-stu-id="9964f-104">The sample service is a simple expense approval service and exposes three operations.</span></span> <span data-ttu-id="9964f-105">`ApproveExpense` принимает значение типа контракта данных и показывает, как использовать известные типы.</span><span class="sxs-lookup"><span data-stu-id="9964f-105">`ApproveExpense` takes a data contract type and shows how to use known types.</span></span> <span data-ttu-id="9964f-106">Операция возвращает значение `true` или `false` в зависимости от суммы затрат.</span><span class="sxs-lookup"><span data-stu-id="9964f-106">The operation returns `true` or `false` based on the expense amount.</span></span> <span data-ttu-id="9964f-107">`ApprovePO` принимает значение типа XmlSerializer и возвращает `true` или `false` зависимости от суммы затрат.`ApprovedVendor`</span><span class="sxs-lookup"><span data-stu-id="9964f-107">`ApprovePO` takes an XmlSerializer type and returns `true` or `false` based on the expense amount.`ApprovedVendor`</span></span> <span data-ttu-id="9964f-108">Получает тип контракта сообщения и возвращает `true` или `false` Если поставщик имеется в списке утвержденных поставщиков или если запрос прибыл из финансового отдела (финансовый отдел может использовать любого поставщика).</span><span class="sxs-lookup"><span data-stu-id="9964f-108">takes a message contract type and returns `true` or `false` if the vendor is in the list of approved vendors or if the request came from the finance department (the finance department can use any vendor).</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="9964f-109">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="9964f-109">To use this sample</span></span>  
  
1.  <span data-ttu-id="9964f-110">Загрузите решение проекта в среду [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] и постройте проект.</span><span class="sxs-lookup"><span data-stu-id="9964f-110">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="9964f-111">Вначале запустите службу, созданную в каталоге [базовый каталог решений]\FormatterService\bin\debug\.</span><span class="sxs-lookup"><span data-stu-id="9964f-111">First run the service, generated in [solution base directory]\FormatterService\bin\debug\\</span></span>  
  
3.  <span data-ttu-id="9964f-112">Затем запустите клиентское приложение, созданное в каталоге [базовый каталог решений]\FormatterClient\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="9964f-112">Second, run the Client application generated in [solution base directory]\FormatterClient\bin\debug.</span></span>  
  
4.  <span data-ttu-id="9964f-113">Клиент вызывает три операции службы и печатает результаты.</span><span class="sxs-lookup"><span data-stu-id="9964f-113">The client calls three operations on the service and prints the results.</span></span> <span data-ttu-id="9964f-114">После завершения нажмите клавишу ВВОД, чтобы закрыть клиент и службу.</span><span class="sxs-lookup"><span data-stu-id="9964f-114">When complete, press ENTER to exit the client and then the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9964f-115">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9964f-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9964f-116">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="9964f-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9964f-117">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="9964f-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9964f-118">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="9964f-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Formatter`