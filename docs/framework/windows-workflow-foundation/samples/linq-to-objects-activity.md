---
title: "Действие LINQ to Objects"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 403c82e8-7f2b-42f6-93cd-95c35bc76ead
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9f34189c8f9911b09017056b22611d27df25c10e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="linq-to-objects-activity"></a>Действие LINQ to Objects
В этом образце демонстрируется создание действия, использующего LINQ to Objects для запроса к элементам в коллекции.  
  
## <a name="activity-details-for-findincollection"></a>Сведения о действии FindInCollection  
 Это действие позволяет пользователям создавать запросы к элементам в коллекциях в памяти с помощью LINQ to Objects. Необходимо указать предикат LINQ в форме лямбда-выражения для фильтрации результатов. Это действие может быть использовано вместе с действиями <xref:System.Activities.Statements.AddToCollection%601>.  
  
 В следующих сведениях о таблице подробно описаны свойства и возвращаемые значения для действия.  
  
|Свойство или возвращаемое значение|Описание|  
|------------------------------|-----------------|  
|Свойство `Collection`|Обязательное свойство, в котором указывается исходная коллекция.|  
|Свойство `Predicate`|Обязательное свойство, в котором указывается фильтр для коллекции в виде лямбда-выражения.|  
|Возвращаемое значение|Фильтруемая коллекция.|  
  
## <a name="code-sample-that-uses-the-custom-activity"></a>Образец кода, использующий настраиваемое действие  
 В следующем примере кода настраиваемое действие `FindInCollection` используется для нахождения всех строк в коллекции служащих, у которых свойство `Role` равно `Manager`, а свойство `Location` равно `Redmond`.  
  
```csharp  
// Find all program managers in Redmond in the employees collection.  
  
Activity wf = new FindInCollection<Employee>  
{  
    Collections = new LambdaValue<IEnumerable<Employee>>(c => employees),                
    Predicate = new LambdaValue<Func<Employee, bool>>(c => new Func<Employee, bool>(e => e.Role.Equals("Manager") && e.Location.Equals("Redmond")))  
};  
```  
  
 В следующем коде показано, как создать программу рабочего процесса, применяющую пользовательское действие FindInCollection и действия <xref:System.Activities.Statements.AddToCollection%601> и <xref:System.Activities.Statements.ForEach%601> для заполнения коллекции служащими, нахождения всех служащих, играющих роль разработчика и работающих в Редмонде и для итерации по получаемому списку результатов.  
  
```csharp  
// Create the Linq predicate for the find expression  
  
Func<Employee, bool> predicate = e => e.Role == "DEV" && e.Location.Equals("Redmond");  
  
// Create workflow program  
Activity sampleWorkflow = new Sequence  
{  
    Variables = { employees, devsFromRedmond },  
    Activities =  
    {  
        new Assign<IList<Employee>>  
        {  
            To = employees,  
            Value = new LambdaValue<IList<Employee>>(c => new List<Employee>())  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(1, "Employee 1", "DEV", "Redmond"))  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(2, "Employee 2", "DEV", "Redmond"))  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(3, "Employee 3", "PM", "Redmond"))  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(4, "Employee 4", "PM", "China"))  
        },  
        new FindInCollection<Employee>  
        {  
            Collections = new InArgument<IEnumerable<Employee>>(employees),  
            Predicate = new LambdaValue<Func<Employee, bool>>(c => predicate),  
            Result = new OutArgument<IList<Employee>>(devsFromRedmond)  
        },  
        new ForEach<Employee>  
        {  
            Values = new InArgument<IEnumerable<Employee>>(devsFromRedmond),  
            Body = new ActivityAction<Employee>  
            {  
                Argument = iterationVariable,  
                Handler = new WriteLine  
                {  
                    Text = new InArgument<string>(env => iterationVariable.Get(env).ToString())  
                }  
            }  
        }  
    }  
};  
```  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Откройте файл решения LinqToObjects.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Для построения решения нажмите CTRL+SHIFT+B.  
  
3.  Чтобы запустить решение, нажмите клавишу F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Linq\LinqToObjects`  
  
## <a name="see-also"></a>См. также  
 [Лямбда-выражения (руководство по программированию на C#)](http://go.microsoft.com/fwlink/?LinkId=150381)  
 [LINQ to Objects](http://go.microsoft.com/fwlink/?LinkID=150380)
