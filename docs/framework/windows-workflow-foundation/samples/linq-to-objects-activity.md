---
title: Действие LINQ to Objects
ms.date: 03/30/2017
ms.assetid: 403c82e8-7f2b-42f6-93cd-95c35bc76ead
ms.openlocfilehash: e2c2be52a88d8f9a886f0e59c027e1d6c737497c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="linq-to-objects-activity"></a><span data-ttu-id="81988-102">Действие LINQ to Objects</span><span class="sxs-lookup"><span data-stu-id="81988-102">LINQ to Objects Activity</span></span>
<span data-ttu-id="81988-103">В этом образце демонстрируется создание действия, использующего LINQ to Objects для запроса к элементам в коллекции.</span><span class="sxs-lookup"><span data-stu-id="81988-103">This sample demonstrates how to create an activity to use LINQ to Objects to query elements in a collection.</span></span>  
  
## <a name="activity-details-for-findincollection"></a><span data-ttu-id="81988-104">Сведения о действии FindInCollection</span><span class="sxs-lookup"><span data-stu-id="81988-104">Activity Details for FindInCollection</span></span>  
 <span data-ttu-id="81988-105">Это действие позволяет пользователям создавать запросы к элементам в коллекциях в памяти с помощью LINQ to Objects.</span><span class="sxs-lookup"><span data-stu-id="81988-105">This activity allows users to query elements from collections in memory using LINQ to Objects.</span></span> <span data-ttu-id="81988-106">Необходимо указать предикат LINQ в форме лямбда-выражения для фильтрации результатов.</span><span class="sxs-lookup"><span data-stu-id="81988-106">You must provide a LINQ predicate in the form of a lambda expression to filter the results.</span></span> <span data-ttu-id="81988-107">Это действие может быть использовано вместе с действиями <xref:System.Activities.Statements.AddToCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="81988-107">This activity can be used in conjunction with <xref:System.Activities.Statements.AddToCollection%601> activities.</span></span>  
  
 <span data-ttu-id="81988-108">В следующих сведениях о таблице подробно описаны свойства и возвращаемые значения для действия.</span><span class="sxs-lookup"><span data-stu-id="81988-108">The following table details the property and return values for the activity.</span></span>  
  
|<span data-ttu-id="81988-109">Свойство или возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="81988-109">Property or Return Value</span></span>|<span data-ttu-id="81988-110">Описание</span><span class="sxs-lookup"><span data-stu-id="81988-110">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="81988-111">Свойство `Collection`</span><span class="sxs-lookup"><span data-stu-id="81988-111">`Collection` property</span></span>|<span data-ttu-id="81988-112">Обязательное свойство, в котором указывается исходная коллекция.</span><span class="sxs-lookup"><span data-stu-id="81988-112">A required property that specifies the source collection.</span></span>|  
|<span data-ttu-id="81988-113">Свойство `Predicate`</span><span class="sxs-lookup"><span data-stu-id="81988-113">`Predicate` property</span></span>|<span data-ttu-id="81988-114">Обязательное свойство, в котором указывается фильтр для коллекции в виде лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="81988-114">A required property that specifies the filter for the collection in the form of a lambda expression.</span></span>|  
|<span data-ttu-id="81988-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="81988-115">Return Value</span></span>|<span data-ttu-id="81988-116">Фильтруемая коллекция.</span><span class="sxs-lookup"><span data-stu-id="81988-116">The filtered collection.</span></span>|  
  
## <a name="code-sample-that-uses-the-custom-activity"></a><span data-ttu-id="81988-117">Образец кода, использующий настраиваемое действие</span><span class="sxs-lookup"><span data-stu-id="81988-117">Code Sample that uses the Custom Activity</span></span>  
 <span data-ttu-id="81988-118">В следующем примере кода настраиваемое действие `FindInCollection` используется для нахождения всех строк в коллекции служащих, у которых свойство `Role` равно `Manager`, а свойство `Location` равно `Redmond`.</span><span class="sxs-lookup"><span data-stu-id="81988-118">The following code example uses the `FindInCollection` custom activity to find all rows in a collection of employees that have a `Role` property set to `Manager` and the `Location` property set to `Redmond`.</span></span>  
  
```csharp  
// Find all program managers in Redmond in the employees collection.  
  
Activity wf = new FindInCollection<Employee>  
{  
    Collections = new LambdaValue<IEnumerable<Employee>>(c => employees),                
    Predicate = new LambdaValue<Func<Employee, bool>>(c => new Func<Employee, bool>(e => e.Role.Equals("Manager") && e.Location.Equals("Redmond")))  
};  
```  
  
 <span data-ttu-id="81988-119">В следующем коде показано, как создать программу рабочего процесса, применяющую пользовательское действие FindInCollection и действия <xref:System.Activities.Statements.AddToCollection%601> и <xref:System.Activities.Statements.ForEach%601> для заполнения коллекции служащими, нахождения всех служащих, играющих роль разработчика и работающих в Редмонде и для итерации по получаемому списку результатов.</span><span class="sxs-lookup"><span data-stu-id="81988-119">The following code shows how to create a workflow program that uses the custom FindInCollection activity, <xref:System.Activities.Statements.AddToCollection%601>, and <xref:System.Activities.Statements.ForEach%601> activities to populate a collection with employees, find all the employees that have developer roles and are located in Redmond, and then iterate through the resulting list.</span></span>  
  
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
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="81988-120">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="81988-120">To use this sample</span></span>  
  
1.  <span data-ttu-id="81988-121">Откройте файл решения LinqToObjects.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81988-121">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the LinqToObjects.sln solution file.</span></span>  
  
2.  <span data-ttu-id="81988-122">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="81988-122">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="81988-123">Чтобы запустить решение, нажмите клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="81988-123">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="81988-124">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="81988-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="81988-125">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="81988-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="81988-126">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="81988-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="81988-127">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="81988-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Linq\LinqToObjects`  
  
## <a name="see-also"></a><span data-ttu-id="81988-128">См. также</span><span class="sxs-lookup"><span data-stu-id="81988-128">See Also</span></span>  
 [<span data-ttu-id="81988-129">Лямбда-выражения (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="81988-129">Lambda Expressions (C# Programming Guide)</span></span>](http://go.microsoft.com/fwlink/?LinkId=150381)  
 [<span data-ttu-id="81988-130">LINQ to Objects</span><span class="sxs-lookup"><span data-stu-id="81988-130">LINQ to Objects</span></span>](http://go.microsoft.com/fwlink/?LinkID=150380)
