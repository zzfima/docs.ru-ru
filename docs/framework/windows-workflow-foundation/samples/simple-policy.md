---
title: Простая политика
ms.date: 03/30/2017
ms.assetid: 6a94c834-2e32-4bed-9f47-ae5845eef6ff
ms.openlocfilehash: dff3979d75fdeb5a45be3940af3568c26f5e8f98
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515900"
---
# <a name="simple-policy"></a><span data-ttu-id="742b7-102">Простая политика</span><span class="sxs-lookup"><span data-stu-id="742b7-102">Simple Policy</span></span>
<span data-ttu-id="742b7-103">В данном образце показано, как использовать действие класса <xref:System.Workflow.Activities.PolicyActivity> в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="742b7-103">This sample shows how to use a <xref:System.Workflow.Activities.PolicyActivity> activity in a workflow.</span></span>  
  
 <span data-ttu-id="742b7-104">В этом образце последовательный рабочий процесс создается с помощью действия класса <xref:System.Workflow.Activities.PolicyActivity>.</span><span class="sxs-lookup"><span data-stu-id="742b7-104">The sequential workflow in this sample is created by using a <xref:System.Workflow.Activities.PolicyActivity> activity.</span></span> <span data-ttu-id="742b7-105">Рабочий процесс определяет поля `orderValue`, `customerType` и `discount`, которые используются для определения рабочего процесса скидки на товар.</span><span class="sxs-lookup"><span data-stu-id="742b7-105">The workflow defines `orderValue`, `customerType`, and `discount` fields that are used to define a product discount workflow.</span></span> <span data-ttu-id="742b7-106">Правила, определенные в наборе файлов правил, задают значение скидки на основе значений `orderValue` и `customerType`.</span><span class="sxs-lookup"><span data-stu-id="742b7-106">The rules defined in the rules file set a discount value that is based on the `orderValue` and `customerType`.</span></span> <span data-ttu-id="742b7-107">Значения `orderValue` и `customerType` заданы в определении класса `SimplePolicyWorkflow`, и их можно редактировать, чтобы изменить поведение.</span><span class="sxs-lookup"><span data-stu-id="742b7-107">The `orderValue` and `customerType` are set in the `SimplePolicyWorkflow` class definition and can be changed to alter the behavior.</span></span> <span data-ttu-id="742b7-108">Конечная скидка записывается в консоль в обработчике событий <xref:System.Workflow.Runtime.WorkflowRuntime.WorkflowCompleted>, определенном в классе `SimplePolicyWorkflow`.</span><span class="sxs-lookup"><span data-stu-id="742b7-108">The resulting discount is written to the console in the <xref:System.Workflow.Runtime.WorkflowRuntime.WorkflowCompleted> event handler that is defined in the `SimplePolicyWorkflow` class.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="742b7-109">Сборка образца</span><span class="sxs-lookup"><span data-stu-id="742b7-109">To build the sample</span></span>  
  
1.  <span data-ttu-id="742b7-110">Откройте решение в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="742b7-110">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="742b7-111">Выполните сборку решения, нажав клавиши CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="742b7-111">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="742b7-112">Запустите решение без отладки, нажав сочетание клавиш CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="742b7-112">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="742b7-113">Выполнение образца</span><span class="sxs-lookup"><span data-stu-id="742b7-113">To run the sample</span></span>  
  
-   <span data-ttu-id="742b7-114">В окне командной строки пакета SDK запустите файл с расширением EXE в папке «SimplePolicy\bin\debug» (или в папке «SimplePolicy\bin» для образца в Visual Basic), вложенной в главную папку образца.</span><span class="sxs-lookup"><span data-stu-id="742b7-114">In the SDK Command Prompt window, run the .exe file in the SimplePolicy\bin\debug folder (or the SimplePolicy\bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="742b7-115">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="742b7-115">The samples may already be installed on your computer.</span></span> <span data-ttu-id="742b7-116">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="742b7-116">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="742b7-117">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="742b7-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="742b7-118">Этот образец находится в следующем каталоге:</span><span class="sxs-lookup"><span data-stu-id="742b7-118">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\SimplePolicy`  
  
## <a name="see-also"></a><span data-ttu-id="742b7-119">См. также</span><span class="sxs-lookup"><span data-stu-id="742b7-119">See Also</span></span>  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [<span data-ttu-id="742b7-120">Дополнительная политика</span><span class="sxs-lookup"><span data-stu-id="742b7-120">Advanced Policy</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/advanced-policy.md)
