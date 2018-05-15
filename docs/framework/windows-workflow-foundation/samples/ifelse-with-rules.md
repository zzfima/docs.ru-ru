---
title: Действие IfElse с правилами
ms.date: 03/30/2017
ms.assetid: c4ad9bb2-9037-413a-8b14-59ed7b927a9e
ms.openlocfilehash: 179ec29f957894433fb527a14048460f5ff6ee5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ifelse-with-rules"></a><span data-ttu-id="b662b-102">Действие IfElse с правилами</span><span class="sxs-lookup"><span data-stu-id="b662b-102">IfElse With Rules</span></span>
<span data-ttu-id="b662b-103">В данном образце демонстрируется использование условий правила для действия класса <xref:System.Workflow.Activities.IfElseActivity>.</span><span class="sxs-lookup"><span data-stu-id="b662b-103">This sample shows the use of a rule condition with an <xref:System.Workflow.Activities.IfElseActivity> activity.</span></span>  
  
 <span data-ttu-id="b662b-104">В данном образце из узла передается параметр `OrderValue`.</span><span class="sxs-lookup"><span data-stu-id="b662b-104">The sample passes in an `OrderValue` parameter from the host.</span></span> <span data-ttu-id="b662b-105">Значение параметра используется в условии правила для первого ответвления действия класса <xref:System.Workflow.Activities.IfElseActivity>.</span><span class="sxs-lookup"><span data-stu-id="b662b-105">The value of the parameter is used in a rule condition on the first branch of the <xref:System.Workflow.Activities.IfElseActivity> activity.</span></span> <span data-ttu-id="b662b-106">Если значение меньше 10 000, выполняет первую ветвь и <xref:System.Workflow.Activities.CodeActivity> действия в первом ответвлении выводит **получение руководителя** на консоль.</span><span class="sxs-lookup"><span data-stu-id="b662b-106">If the value is less than 10,000, the first branch executes, and the <xref:System.Workflow.Activities.CodeActivity> activity in the first branch prints **Get Manager Approval** to the console.</span></span> <span data-ttu-id="b662b-107">Если значение больше 10 000, <xref:System.Workflow.Activities.CodeActivity> действия во втором разветвлении выполняется и выводится **получить утверждение вице-Президент**.</span><span class="sxs-lookup"><span data-stu-id="b662b-107">If the value is greater than 10,000, the <xref:System.Workflow.Activities.CodeActivity> activity in the second branch executes and prints **Get VP Approval**.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="b662b-108">Сборка образца</span><span class="sxs-lookup"><span data-stu-id="b662b-108">To build the sample</span></span>  
  
1.  <span data-ttu-id="b662b-109">Откройте решение в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b662b-109">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="b662b-110">Выполните сборку решения, нажав клавиши CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="b662b-110">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="b662b-111">Запустите решение без отладки, нажав сочетание клавиш CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="b662b-111">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="b662b-112">Выполнение образца</span><span class="sxs-lookup"><span data-stu-id="b662b-112">To run the sample</span></span>  
  
-   <span data-ttu-id="b662b-113">В окне командной строки пакета SDK запустите файл с расширением EXE в папке «IfElseWithRules\bin\debug» (или в папке «IfElseWithRules\bin» для образца в Visual Basic), вложенной в главную папку образца.</span><span class="sxs-lookup"><span data-stu-id="b662b-113">In the SDK Command Prompt window, run the .exe file in the IfElseWithRules\bin\debug folder (or the IfElseWithRules\bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b662b-114">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b662b-114">The samples may already be installed on your computer.</span></span> <span data-ttu-id="b662b-115">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b662b-115">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b662b-116">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="b662b-116">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b662b-117">Этот образец находится в следующем каталоге:</span><span class="sxs-lookup"><span data-stu-id="b662b-117">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\IfElseWithRules`  
  
## <a name="see-also"></a><span data-ttu-id="b662b-118">См. также</span><span class="sxs-lookup"><span data-stu-id="b662b-118">See Also</span></span>  
 <xref:System.Workflow.Activities.Rules>  
 <xref:System.Workflow.Activities.IfElseActivity>  
 <xref:System.Workflow.Activities.CodeActivity>  
 <xref:System.Workflow.Activities.Rules.RuleDefinitions>
