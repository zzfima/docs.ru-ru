---
title: Эмуляция прерывания в действии While
ms.date: 03/30/2017
ms.assetid: ddff715d-d623-4b54-b841-60bacbc3ca21
ms.openlocfilehash: 4938e07364609520f6528688877bce112be26d3f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43560429"
---
# <a name="emulating-breaking-in-a-while-activity"></a><span data-ttu-id="eb6d5-102">Эмуляция прерывания в действии While</span><span class="sxs-lookup"><span data-stu-id="eb6d5-102">Emulating breaking in a While activity</span></span>
<span data-ttu-id="eb6d5-103">Этот образец показывает, как прервать циклический механизм следующих действий: <xref:System.Activities.Statements.DoWhile>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.While> и <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="eb6d5-103">This sample demonstrates how to break the looping mechanism of the following activities: <xref:System.Activities.Statements.DoWhile>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.While>, and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span>  
  
 <span data-ttu-id="eb6d5-104">Это полезно, поскольку Windows Workflow Foundation (WF) не включает действия для прерывания выполнения этих циклов.</span><span class="sxs-lookup"><span data-stu-id="eb6d5-104">This is useful because Windows Workflow Foundation (WF) does not include any activity to break the execution of these loops.</span></span>  
  
## <a name="scenario"></a><span data-ttu-id="eb6d5-105">Сценарий</span><span class="sxs-lookup"><span data-stu-id="eb6d5-105">Scenario</span></span>  
 <span data-ttu-id="eb6d5-106">Образец находит первого надежного поставщика из списка поставщиков (экземпляры класса `Vendor`).</span><span class="sxs-lookup"><span data-stu-id="eb6d5-106">The sample finds the first reliable vendor from a list of vendors (instances of the `Vendor` class).</span></span> <span data-ttu-id="eb6d5-107">Каждый поставщик имеет `ID`, `Name` и числовое значение надежности, определяющее, насколько на его продукцию можно положиться.</span><span class="sxs-lookup"><span data-stu-id="eb6d5-107">Each vendor has an `ID`, a `Name` and a numeric reliability value that determines how dependable the vendor is.</span></span> <span data-ttu-id="eb6d5-108">Образец создает пользовательское действие с именем `FindReliableVendor`, получающее два входных параметра (список поставщиков и минимальное значение надежности) и возвращает первого поставщика из списка, соответствующего предоставленным критериям.</span><span class="sxs-lookup"><span data-stu-id="eb6d5-108">The sample creates a custom activity called `FindReliableVendor` that receives two input parameters (a list of vendors and a minimum reliability value) and returns the first vendor of the list that matches the supplied criteria.</span></span>  
  
## <a name="breaking-a-loop"></a><span data-ttu-id="eb6d5-109">Прерывание цикла</span><span class="sxs-lookup"><span data-stu-id="eb6d5-109">Breaking a Loop</span></span>  
 <span data-ttu-id="eb6d5-110">Windows Workflow Foundation (WF) не включены действия для прерывания цикла.</span><span class="sxs-lookup"><span data-stu-id="eb6d5-110">Windows Workflow Foundation (WF) does not include an activity to break a loop.</span></span> <span data-ttu-id="eb6d5-111">Образец кода выполняет прерывание цикла с помощью действия <xref:System.Activities.Statements.If> и нескольких переменных.</span><span class="sxs-lookup"><span data-stu-id="eb6d5-111">The code sample accomplishes breaking a loop by using an <xref:System.Activities.Statements.If> activity and several variables.</span></span> <span data-ttu-id="eb6d5-112">В этом образце действие <xref:System.Activities.Statements.While> прерывается, если переменной `reliableVendor` присваивается значение, отличное от `null`.</span><span class="sxs-lookup"><span data-stu-id="eb6d5-112">In the sample, the <xref:System.Activities.Statements.While> activity is broken once the `reliableVendor` variable is assigned a value other than `null`.</span></span>  
  
 <span data-ttu-id="eb6d5-113">Следующий пример кода демонстрирует, как этот образец прерывает цикл while.</span><span class="sxs-lookup"><span data-stu-id="eb6d5-113">The following code example demonstrates how the sample breaks a while loop.</span></span>  
  
```csharp  
// Iterates while the "i" variable is lower than the size of the list   
// and any reliable Vendor is found.        
new While(env => i.Get(env) < this.Vendors.Get(env).Count && reliableVendor.Get(env) == null)  
{  
    DisplayName = "Main loop. Breaks when a reliable vendor is found",  
    Body = new Sequence  
    {                              
        Activities =  
        {  
            // This is the if used for setting the value of the break value…  
            new If  
            {  
                DisplayName = "Check for a reliable vendor",  
  
                //  If a vendor satisfies the reliability level…  
                Condition = new InArgument<bool>(env =>   
                           this.Vendors.Get(env)[i.Get(env)].Reliability >   
                           this.MinimumReliability.Get(env)),  
  
                // then assign that vendor to the reliable vendor variable and   
                // the while condition becomes false (exit the loop).  
                Then = new Assign<Vendor>  
                {  
                    To = reliableVendor,  
                    Value = new InArgument<Vendor>(env =>   
                                  this.Vendors.Get(env)[i.Get(env)])  
                }  
            },  
  
            // Increment the iteration variable.   
            new Assign<int>  
            {  
                DisplayName = "Increment iteration variable",  
                To = i,  
                Value = new InArgument<int>(env => i.Get(env) + 1)  
            }   
        }  
    }  
}  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="eb6d5-114">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="eb6d5-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="eb6d5-115">Откройте файл решения EmulatingBreakInWhile.sln с помощью [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb6d5-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the EmulatingBreakInWhile.sln solution file.</span></span>  
  
2.  <span data-ttu-id="eb6d5-116">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="eb6d5-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="eb6d5-117">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="eb6d5-117">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="eb6d5-118">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="eb6d5-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="eb6d5-119">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="eb6d5-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="eb6d5-120">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="eb6d5-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="eb6d5-121">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="eb6d5-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\EmulatingBreakInWhile`