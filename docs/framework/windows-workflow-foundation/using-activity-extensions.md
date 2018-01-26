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
ms.workload: dotnet
ms.openlocfilehash: 6bc2e498a4073f6f0881e011b00de6ac89f4f2fe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="using-activity-extensions"></a>Использование модулей действий
Действия могут взаимодействовать с расширениями приложений рабочих процессов. Благодаря этому узел может предоставлять дополнительные возможности, которые не были явно смоделированы в рабочем процессе.  В этом разделе описывается создание расширений для подсчета количества выполнений действия.  
  
### <a name="to-use-an-activity-extension-to-count-executions"></a>Использования расширения действия для подсчета выполнений  
  
1.  Откройте [!INCLUDE[vs2010](../../../includes/vs2010-md.md)]. Выберите **новый**, **проекта**. В разделе **Visual C#** выберите **рабочего процесса**.  Выберите **консольное приложение рабочего процесса** из списка шаблонов. Задайте для проекта имя `Extensions`. Нажмите кнопку **ОК** для создания проекта.  
  
2.  Добавить `using` инструкции в файл Program.cs для **System.Collections.Generic** пространства имен.  
  
    ```  
    using System.Collections.Generic;  
    ```  
  
3.  В файле Program.cs создайте новый класс с именем **ExecutionCountExtension**. Следующий код создает расширение рабочего процесса, отслеживающее идентификаторы экземпляра при его **зарегистрировать** вызывается метод.  
  
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
  
4.  Создать действие, использующее **ExecutionCountExtension**. В следующем коде определяется действие, извлекающее **ExecutionCountExtension** из среды выполнения и вызывающее его **зарегистрировать** метод при выполнении действия.  
  
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
  
5.  Реализуйте действие в **Main** метод файла program.cs. В следующем коде содержатся методы для создания двух различных рабочих процессов, выполнения всех процессов по несколько раз и отображения полученных данных, содержащихся в расширении.  
  
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
