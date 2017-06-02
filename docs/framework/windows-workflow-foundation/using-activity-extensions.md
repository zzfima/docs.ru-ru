---
title: "Использование модулей действий | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 500eb96a-c009-4247-b6b5-b36faffdf715
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Использование модулей действий
Действия могут взаимодействовать с расширениями приложений рабочих процессов. Благодаря этому узел может предоставлять дополнительные возможности, которые не были явно смоделированы в рабочем процессе.В этом разделе описывается создание расширений для подсчета количества выполнений действия.  
  
### Использования расширения действия для подсчета выполнений  
  
1.  Откройте [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].Выберите **Создать**, **Создать проект**.В узле **Visual C\#** выберите **Рабочий процесс**.Выберите **Консольное приложение рабочего процесса** из списка шаблонов.Назовите проект `Extensions`.Нажмите кнопку **ОК**, чтобы создать проект.  
  
2.  Добавьте инструкцию `using` в файл Program.cs для пространства имен **System.Collections.Generic**.  
  
    ```  
    using System.Collections.Generic;  
  
    ```  
  
3.  В файле Program.cs создайте новый класс с именем **ExecutionCountExtension**.В следующем коде создается расширение рабочего процесса, отслеживающее идентификаторы экземпляра при вызове метода **Register**.  
  
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
  
4.  Создайте действие, использующее **ExecutionCountExtension**.В следующем коде определяется действие, извлекающее объект **ExecutionCountExtension** из среды выполнения и вызывающее его метод **Register** при выполнении действия.  
  
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
  
5.  Реализуйте действие в методе **Main** файла program.cs.В следующем коде содержатся методы для создания двух различных рабочих процессов, выполнения всех процессов по несколько раз и отображения полученных данных, содержащихся в расширении.  
  
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