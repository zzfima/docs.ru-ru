---
title: "Использование модулей действий"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 500eb96a-c009-4247-b6b5-b36faffdf715
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fd8bde396cd53577a87976f8fe40c0ae3ab3708e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="using-activity-extensions"></a><span data-ttu-id="75674-102">Использование модулей действий</span><span class="sxs-lookup"><span data-stu-id="75674-102">Using Activity Extensions</span></span>
<span data-ttu-id="75674-103">Действия могут взаимодействовать с расширениями приложений рабочих процессов. Благодаря этому узел может предоставлять дополнительные возможности, которые не были явно смоделированы в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="75674-103">Activities can interact with workflow application extensions that allow the host to provide additional functionality that is not explicitly modeled in the workflow.</span></span>  <span data-ttu-id="75674-104">В этом разделе описывается создание расширений для подсчета количества выполнений действия.</span><span class="sxs-lookup"><span data-stu-id="75674-104">This topic describes how to create and use an extension to count the number of times the activity executes.</span></span>  
  
### <a name="to-use-an-activity-extension-to-count-executions"></a><span data-ttu-id="75674-105">Использования расширения действия для подсчета выполнений</span><span class="sxs-lookup"><span data-stu-id="75674-105">To use an activity extension to count executions</span></span>  
  
1.  <span data-ttu-id="75674-106">Откройте [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="75674-106">Open [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span> <span data-ttu-id="75674-107">Выберите **новый**, **проекта**.</span><span class="sxs-lookup"><span data-stu-id="75674-107">Select **New**, **Project**.</span></span> <span data-ttu-id="75674-108">В разделе **Visual C#** выберите **рабочего процесса**.</span><span class="sxs-lookup"><span data-stu-id="75674-108">Under the **Visual C#** node, select **Workflow**.</span></span>  <span data-ttu-id="75674-109">Выберите **консольное приложение рабочего процесса** из списка шаблонов.</span><span class="sxs-lookup"><span data-stu-id="75674-109">Select **Workflow Console Application** from the list of templates.</span></span> <span data-ttu-id="75674-110">Задайте для проекта имя `Extensions`.</span><span class="sxs-lookup"><span data-stu-id="75674-110">Name the project `Extensions`.</span></span> <span data-ttu-id="75674-111">Нажмите кнопку **ОК** для создания проекта.</span><span class="sxs-lookup"><span data-stu-id="75674-111">Click **OK** to create the project.</span></span>  
  
2.  <span data-ttu-id="75674-112">Добавить `using` инструкции в файл Program.cs для **System.Collections.Generic** пространства имен.</span><span class="sxs-lookup"><span data-stu-id="75674-112">Add a `using` statement in the Program.cs file for the **System.Collections.Generic** namespace.</span></span>  
  
    ```  
    using System.Collections.Generic;  
    ```  
  
3.  <span data-ttu-id="75674-113">В файле Program.cs создайте новый класс с именем **ExecutionCountExtension**.</span><span class="sxs-lookup"><span data-stu-id="75674-113">In the Program.cs file, create a new class named **ExecutionCountExtension**.</span></span> <span data-ttu-id="75674-114">Следующий код создает расширение рабочего процесса, отслеживающее идентификаторы экземпляра при его **зарегистрировать** вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="75674-114">The following code creates a workflow extension that tracks instance IDs when its **Register** method is called.</span></span>  
  
    ```  
    // This extension collects a list of workflow Ids  
    public class ExecutionCountExtension  
    {  
        IList<Guid> instances = new List<Guid>();  
  
        public int ExecutionCount  
        {  
            get  
            {  
                return this.instances.Count;  
            }  
        }  
  
        public IEnumerable<Guid> InstanceIds  
        {  
            get  
            {  
                return this.instances;  
            }  
        }  
  
        public void Register(Guid activityInstanceId)  
        {  
            if (!this.instances.Contains<Guid>(activityInstanceId))  
            {  
                instances.Add(activityInstanceId);  
            }  
        }  
    }  
    ```  
  
4.  <span data-ttu-id="75674-115">Создать действие, использующее **ExecutionCountExtension**.</span><span class="sxs-lookup"><span data-stu-id="75674-115">Create an activity that consumes the **ExecutionCountExtension**.</span></span> <span data-ttu-id="75674-116">В следующем коде определяется действие, извлекающее **ExecutionCountExtension** из среды выполнения и вызывающее его **зарегистрировать** метод при выполнении действия.</span><span class="sxs-lookup"><span data-stu-id="75674-116">The following code defines an activity that retrieves the **ExecutionCountExtension** object from the runtime and calls its **Register** method when the activity executes.</span></span>  
  
    ```  
    // Activity that consumes an extension provided by the host. If the extension is available  
    // in the context, it will invoke (in this case, registers the Id of the executing workflow)  
    public class MyActivity: CodeActivity  
    {  
        protected override void Execute(CodeActivityContext context)  
        {  
            ExecutionCountExtension ext = context.GetExtension<ExecutionCountExtension>();  
            if (ext != null)  
            {  
                ext.Register(context.WorkflowInstanceId);                         
            }  
  
        }  
    }  
    ```  
  
5.  <span data-ttu-id="75674-117">Реализуйте действие в **Main** метод файла program.cs.</span><span class="sxs-lookup"><span data-stu-id="75674-117">Implement the activity in the **Main** method of the program.cs file.</span></span> <span data-ttu-id="75674-118">В следующем коде содержатся методы для создания двух различных рабочих процессов, выполнения всех процессов по несколько раз и отображения полученных данных, содержащихся в расширении.</span><span class="sxs-lookup"><span data-stu-id="75674-118">The following code contains methods to generate two different workflows, execute each workflow several times, and display the resulting data that is contained in the extension.</span></span>  
  
    ```  
    class Program  
    {  
        // Creates a workflow that uses the activity that consumes the extension  
        static Activity CreateWorkflow1()  
        {  
            return new Sequence  
            {  
                Activities =  
                {  
                    new MyActivity()  
                }  
            };  
        }  
  
        // Creates a workflow that uses two instances of the activity that consumes the extension  
        static Activity CreateWorkflow2()  
        {  
            return new Sequence  
            {  
                Activities =  
                {  
                    new MyActivity(),  
                    new MyActivity()  
                }  
            };  
        }  
  
        static void Main(string[] args)  
        {  
            // create the extension   
            ExecutionCountExtension executionCountExt = new ExecutionCountExtension();  
  
            // configure the first invoker and execute 3 times  
            WorkflowInvoker invoker = new WorkflowInvoker(CreateWorkflow1());  
            invoker.Extensions.Add(executionCountExt);                          
            invoker.Invoke();  
            invoker.Invoke();  
            invoker.Invoke();  
  
            // configure the second invoker and execute 2 times  
            WorkflowInvoker invoker2 = new WorkflowInvoker(CreateWorkflow2());  
            invoker2.Extensions.Add(executionCountExt);  
            invoker2.Invoke();  
            invoker2.Invoke();  
  
            // show the data in the extension  
            Console.WriteLine("Executed {0} times", executionCountExt.ExecutionCount);  
            executionCountExt.InstanceIds.ToList().ForEach(i => Console.WriteLine("...{0}", i));  
        }  
    }  
    ```
