---
title: Действия с сущностями
ms.date: 03/30/2017
ms.assetid: c04f7413-7fb8-40c6-819e-dc92b145b62e
ms.openlocfilehash: 96301c15b849749299e744a435068c3ec9be2e3a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33519140"
---
# <a name="entity-activities"></a><span data-ttu-id="120a9-102">Действия с сущностями</span><span class="sxs-lookup"><span data-stu-id="120a9-102">Entity Activities</span></span>
<span data-ttu-id="120a9-103">В этом примере показано, как использовать ADO.NET Entity Framework с Windows Workflow Foundation для упрощения доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="120a9-103">This sample shows how to use the ADO.NET Entity Framework with Windows Workflow Foundation to simplify data access.</span></span>  
  
 <span data-ttu-id="120a9-104">С помощью платформы ADO.NET Entity Framework разработчики могут работать с данными в форме объектов, свойств и связей определенного домена, например клиентов, заказов, подробных сведений о заказах и связей между этими сущностями.</span><span class="sxs-lookup"><span data-stu-id="120a9-104">The ADO.NET Entity Framework enables developers to work with data in the form of domain-specific objects, properties and relationships such as Customers, Orders, Order Details and the relationships between these entities.</span></span> <span data-ttu-id="120a9-105">На платформе ADO.NET Entity Framework это достигается за счет уровня абстракции, позволяющего осуществлять программирование по концептуальной модели приложения, а не напрямую по схеме реляционного хранилища.</span><span class="sxs-lookup"><span data-stu-id="120a9-105">The ADO.NET Entity Framework does this by providing a level of abstraction that enables programming against a conceptual application model instead of programming directly against a relational storage schema.</span></span> <span data-ttu-id="120a9-106">Дополнительные сведения о ADO.NET Entity Framework см. [ADO.NET Entity Framework](http://go.microsoft.com/fwlink/?LinkId=165549).</span><span class="sxs-lookup"><span data-stu-id="120a9-106">For more information about the ADO.NET Entity Framework see [ADO.NET Entity Framework](http://go.microsoft.com/fwlink/?LinkId=165549).</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="120a9-107">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="120a9-107">Sample details</span></span>  
 <span data-ttu-id="120a9-108">В этом образце используется база данных `Northwind`, в него входят скрипты для создания и удаления базы данных `Northwind` (Setup.cmd и Cleanup.cmd).</span><span class="sxs-lookup"><span data-stu-id="120a9-108">This sample uses the `Northwind` database and includes scripts for creating and removing the `Northwind` database (Setup.cmd and Cleanup.cmd).</span></span> <span data-ttu-id="120a9-109">Среди проектов этого образца имеется модель EDM, основанная на базе данных `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="120a9-109">The projects in this sample include an Entity Data Model based on the `Northwind` database.</span></span> <span data-ttu-id="120a9-110">Модель можно найти, открыв файл `Northwind.edmx`, который включен в проект.</span><span class="sxs-lookup"><span data-stu-id="120a9-110">You can find the model by opening the `Northwind.edmx` file that is included in the project.</span></span> <span data-ttu-id="120a9-111">Именно эта модель определяет форму объектов, к которым может осуществляться доступ из платформы ADO.NET Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="120a9-111">This is the model that defines the shape of the objects that can be accessed using the ADO.NET Entity Framework.</span></span>  
  
 <span data-ttu-id="120a9-112">В данный образец включены следующие действия:</span><span class="sxs-lookup"><span data-stu-id="120a9-112">The following activities are included in this sample:</span></span>  
  
-   <span data-ttu-id="120a9-113">`EntitySQLQuery`: действие `EntitySQLQuery` позволяет получать объекты из базы данных на основе строки запроса Entity SQL.</span><span class="sxs-lookup"><span data-stu-id="120a9-113">`EntitySQLQuery`: The `EntitySQLQuery` activity allows you to retrieve objects from the database based on an Entity SQL query string.</span></span> <span data-ttu-id="120a9-114">Entity SQL - это независимый от хранилища язык, сходный с SQL, который позволяет задавать запросы на основе концептуальной модели и сущностей, являющихся частью модели или домена.</span><span class="sxs-lookup"><span data-stu-id="120a9-114">Entity SQL is a store independent language that is similar to SQL and it allows you to specify queries based on the conceptual model and the entities that are a part of the model or domain.</span></span> <span data-ttu-id="120a9-115">Дополнительные сведения о языке Entity SQL см. в разделе [язык Entity SQL](http://go.microsoft.com/fwlink/?LinkId=165646).</span><span class="sxs-lookup"><span data-stu-id="120a9-115">For more information about Entity SQL Language, see [Entity SQL Language](http://go.microsoft.com/fwlink/?LinkId=165646).</span></span>  
  
-   <span data-ttu-id="120a9-116">`EntityLinqQuery`: это действие позволяет получать объекты из базы данных на основе запроса LINQ или предиката.</span><span class="sxs-lookup"><span data-stu-id="120a9-116">`EntityLinqQuery`: This activity allows you to retrieve objects from the database based on a LINQ query or predicate.</span></span>  
  
-   <span data-ttu-id="120a9-117">`EntityAdd`: действие `EntityAdd` позволяет добавлять сущность или коллекцию сущностей в базу данных.</span><span class="sxs-lookup"><span data-stu-id="120a9-117">`EntityAdd`: The `EntityAdd` activity allows you to add an entity or a collection of entities to the database.</span></span>  
  
-   <span data-ttu-id="120a9-118">`EntityDelete`: действие `EntityDelete` позволяет удалять сущность или коллекцию сущностей из базы данных.</span><span class="sxs-lookup"><span data-stu-id="120a9-118">`EntityDelete`: The `EntityDelete` activity allows you to delete an entity or a collection of entities from the database.</span></span>  
  
-   <span data-ttu-id="120a9-119">`ObjectContextScope`: упомянутые ранее действия могут быть использованы только в пределах содержащего их экземпляра действия `ObjectContextScope`.</span><span class="sxs-lookup"><span data-stu-id="120a9-119">`ObjectContextScope`: The previously mentioned activities can only be used within a containing `ObjectContextScope` activity instance.</span></span> <span data-ttu-id="120a9-120">Действие `ObjectContextScope` настраивает соединение с базой данных.</span><span class="sxs-lookup"><span data-stu-id="120a9-120">The `ObjectContextScope` activity sets up the connection to the database.</span></span> <span data-ttu-id="120a9-121">Для действия требуется строка подключения (которая передается с использованием настройки файла конфигурации или возвращается с ее помощью).</span><span class="sxs-lookup"><span data-stu-id="120a9-121">It requires a connection string (that is either passed in or retrieved using a configuration file setting).</span></span> <span data-ttu-id="120a9-122">Действие `ObjectContextScope` облегчает выполнение группы связанных операций с сущностями.</span><span class="sxs-lookup"><span data-stu-id="120a9-122">The `ObjectContextScope` activity makes it easy to perform a group of related operations on entities.</span></span> <span data-ttu-id="120a9-123">Поскольку эта область поддерживает активное соединение, она является несохраняемой областью.</span><span class="sxs-lookup"><span data-stu-id="120a9-123">Because this scope maintains an active connection, it is a No Persist scope.</span></span> <span data-ttu-id="120a9-124">Кроме того, при выполнении действием `ObjectContextScope` выхода все изменения, которые внесены в объекты, возвращенные с помощью действий сущностей в области, автоматически сохраняются в базе данных. Для сохранения объектов в базу данных не требуется никаких последующих действий.</span><span class="sxs-lookup"><span data-stu-id="120a9-124">In addition, when the `ObjectContextScope` activity exits, any changes that are made to objects retrieved using Entity Activities within that scope automatically get persisted back to the database, and no explicit or subsequent action is required to save objects back to the database.</span></span>  
  
## <a name="using-the-entity-activities"></a><span data-ttu-id="120a9-125">Использование действий сущностей</span><span class="sxs-lookup"><span data-stu-id="120a9-125">Using the entity activities</span></span>  
 <span data-ttu-id="120a9-126">Следующие фрагменты кода демонстрируют использование действий сущностей, представленных в этом образце.</span><span class="sxs-lookup"><span data-stu-id="120a9-126">The following code snippets demonstrate how to use the entity activities presented in this sample.</span></span>  
  
### <a name="entitysql"></a><span data-ttu-id="120a9-127">EntitySql</span><span class="sxs-lookup"><span data-stu-id="120a9-127">EntitySql</span></span>  
 <span data-ttu-id="120a9-128">Приведенный далее фрагмент кода показывает, как запрашивать всех клиентов из Лондона с сортировкой по имени и как выполнить итерацию по списку клиентов.</span><span class="sxs-lookup"><span data-stu-id="120a9-128">The code snippet below shows how to query all customers in London sorted by name and how to iterate through the list of customers.</span></span>  
  
```  
Variable<IEnumerable<Customer>> londonCustomers = new Variable<IEnumerable<Customer>>();  
DelegateInArgument<Customer> iterationVariable = new DelegateInArgument<Customer>();  
  
// create and return the workflow  
return new ObjectContextScope  
{  
    ConnectionString = new InArgument<string>(connStr),  
    ContainerName = "NorthwindEntities",  
    Variables = { londonCustomers },  
    Body = new Sequence  
        {  
            Activities =   
                {               
                    new WriteLine { Text = "Executing query" },                            
                    // query for all customers that are in london   
                    new EntitySqlQuery<Customer>  
                    {  
                        EntitySql =  @"SELECT VALUE Customer   
                                        FROM NorthwindEntities.Customers AS Customer   
                                        WHERE Customer.City = 'London'   
                                        ORDER BY Customer.ContactName",  
                        Result = londonCustomers  
                    },  
  
                    // iterate through the list of customers and display them   
                    new ForEach<Customer>  
                    {                                      
                        Values = londonCustomers,  
                        Body = new ActivityAction<Customer>  
                        {  
                            Argument = iterationVariable,  
                            Handler = new WriteLine   
                            {   
                                  Text = new InArgument<String>(e =>    
                                              iterationVariable.Get(e).ContactName)   
                            }  
                        }  
                    }  
                }  
        }                 
};     
```  
  
### <a name="entitylinqquery"></a><span data-ttu-id="120a9-129">EntityLinqQuery</span><span class="sxs-lookup"><span data-stu-id="120a9-129">EntityLinqQuery</span></span>  
 <span data-ttu-id="120a9-130">Приведенный далее фрагмент кода показывает, как запросить всех клиентов из Лондона и как выполнить итерацию по итоговому списку клиентов.</span><span class="sxs-lookup"><span data-stu-id="120a9-130">The code snippet below shows how to query all customers in London and how to iterate through the resulting list of customers.</span></span>  
  
```  
Variable<IEnumerable<Customer>> londonCustomers = new Variable<IEnumerable<Customer>>() { Name = "LondonCustomers" };  
DelegateInArgument<Customer> iterationVariable = new DelegateInArgument<Customer>() { Name = "iterationVariable" };  
  
return new ObjectContextScope  
{  
    ConnectionString = new InArgument<string>(connStr),  
    ContainerName = "NorthwindEntities",  
    Variables = { londonCustomers },  
    Body = new Sequence  
    {  
        Activities =   
        {               
            // return all the customers that match with the provided Linq predicate  
            new EntityLinqQuery<Customer>  
            {   
                Predicate = new LambdaValue<Func<Customer, bool>>(  
                          ctx => new Func<Customer, bool>(c => c.City.Equals("London"))),                              
                Result = londonCustomers  
            },  
  
            // iterate through the list of customers and display in the console  
            new ForEach<Customer>  
            {                                      
                Values = londonCustomers,  
                Body = new ActivityAction<Customer>  
                {  
                    Argument = iterationVariable,  
                    Handler = new WriteLine   
                    {   
                        Text = new InArgument<String>(e =>   
                                      iterationVariable.Get(e).ContactName)   
                    }  
                }  
            }  
        }  
    }  
};  
```  
  
### <a name="entityadd"></a><span data-ttu-id="120a9-131">EntityAdd</span><span class="sxs-lookup"><span data-stu-id="120a9-131">EntityAdd</span></span>  
 <span data-ttu-id="120a9-132">Приведенный далее фрагмент кода показывает, как добавить запись OrderDetail в существующий заказ.</span><span class="sxs-lookup"><span data-stu-id="120a9-132">The code snippet below shows how to add an OrderDetail record to an existing Order.</span></span>  
  
```  
Variable<IEnumerable<Order>> orders = new Variable<IEnumerable<Order>>();  
Variable<IEnumerable<OrderDetail>> orderDetails = new Variable<IEnumerable<OrderDetail>>();  
Variable<Order> order = new Variable<Order>();  
Variable<OrderDetail> orderDetail = new Variable<OrderDetail>();              
  
return new ObjectContextScope  
{  
    Variables = { order, orders, orderDetail, orderDetails },  
    ContainerName = "NorthwindEntities",  
    ConnectionString = new InArgument<string>(connStr),                  
    Body = new Sequence  
    {                      
        Activities =   
        {                            
           // get the order where we want to add the detail  
           new EntitySqlQuery<Order>  
           {  
               EntitySql =    
                    @"SELECT VALUE [Order]  
                      FROM NorthwindEntities.Orders as [Order]  
                      WHERE Order.OrderID == 10249",  
               Result = orders  
           },  
  
           // store the order in a variable  
           new Assign<Order>   
           {  
               To = new OutArgument<Order>(order),  
               Value = new InArgument<Order>(c => orders.Get(c).First<Order>())  
           },  
  
           // add the detail to the order  
           new EntityAdd<OrderDetail>  
           {  
               Entity = new InArgument<OrderDetail>(c =>   
                                         new OrderDetail {   
                                                  OrderID=10249, ProductID=11,   
                                                  Quantity=1, UnitPrice = 15,   
                                                  Discount = 0, Order = order.Get(c) })  
           }  
        }  
    }  
};  
```  
  
### <a name="entitydelete"></a><span data-ttu-id="120a9-133">EntityDelete</span><span class="sxs-lookup"><span data-stu-id="120a9-133">EntityDelete</span></span>  
 <span data-ttu-id="120a9-134">Приведенный далее фрагмент кода показывает, как удалить существующую запись OrderDetail из заказа (если он существует).</span><span class="sxs-lookup"><span data-stu-id="120a9-134">The code snippet below shows how to delete an existing OrderDetail record in an Order (if it exists).</span></span>  
  
```  
Variable<IEnumerable<OrderDetail>> orderDetails = new Variable<IEnumerable<OrderDetail>>();              
  
return new ObjectContextScope  
{  
    Variables = { orderDetails },  
    ConnectionString = new InArgument<string>(connStr),  
    ContainerName = "NorthwindEntities",  
    Body = new Sequence  
    {  
        Activities =   
        {               
            // find the entitiy to be deleted (order detail for product 11 in order 10249)  
            new EntitySqlQuery<OrderDetail>  
            {  
                EntitySql = @"SELECT VALUE OrderDetail  
                                FROM NorthwindEntities.OrderDetails as OrderDetail  
                               WHERE OrderDetail.OrderID == 10249   
                                 AND OrderDetail.ProductID == 11",  
                Result = orderDetails  
            },  
  
            // if the order detail is found, delete it, otherwise, display a message  
            new If  
            {  
                Condition = new InArgument<bool>(c=>orderDetails.Get(c).Count() > 0),  
                Then = new Sequence  
                {   
                    Activities =   
                    {                                      
                        new EntityDelete<OrderDetail>  
                        {  
                            Entity = new InArgument<OrderDetail>(c =>   
                                              orderDetails.Get(c).First<OrderDetail>())  
                        },  
                    }  
                },                              
                Else = new WriteLine { Text = "Order Detail for Deleting not found" }                              
            }                                                  
        }  
    }  
};  
```  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="120a9-135">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="120a9-135">To use this sample</span></span>  
 <span data-ttu-id="120a9-136">Перед выполнением этого образца необходимо создать базу данных `Northwind` в локальном экземпляре SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="120a9-136">You must create the `Northwind` database in your local SQL server Express instance before running this sample.</span></span>  
  
#### <a name="to-set-up-the-northwind-database"></a><span data-ttu-id="120a9-137">Настройка базы данных «Northwind».</span><span class="sxs-lookup"><span data-stu-id="120a9-137">To set up the Northwind database</span></span>  
  
1.  <span data-ttu-id="120a9-138">Откройте окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="120a9-138">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="120a9-139">В новом окне командной строки перейдите в папку EntityActivities\CS.</span><span class="sxs-lookup"><span data-stu-id="120a9-139">In the new command prompt window, navigate to the EntityActivities\CS folder.</span></span>  
  
3.  <span data-ttu-id="120a9-140">Тип `setup.cmd` и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="120a9-140">Type `setup.cmd` and press ENTER.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="120a9-141">Выполнение образца</span><span class="sxs-lookup"><span data-stu-id="120a9-141">To run the sample</span></span>  
  
1.  <span data-ttu-id="120a9-142">Откройте файл решения EntityActivities.sln в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="120a9-142">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the EntityActivities.sln solution file.</span></span>  
  
2.  <span data-ttu-id="120a9-143">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="120a9-143">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="120a9-144">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="120a9-144">To run the solution, press CTRL+F5.</span></span>  
  
 <span data-ttu-id="120a9-145">После выполнения этого образца базу данных `Northwind` можно удалить.</span><span class="sxs-lookup"><span data-stu-id="120a9-145">After running this sample, you may want to remove the `Northwind` database.</span></span>  
  
#### <a name="to-uninstall-the-northwind-database"></a><span data-ttu-id="120a9-146">Удаление базы данных «Northwind».</span><span class="sxs-lookup"><span data-stu-id="120a9-146">To uninstall the Northwind database</span></span>  
  
1.  <span data-ttu-id="120a9-147">Откройте окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="120a9-147">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="120a9-148">В новом окне командной строки перейдите в папку EntityActivities\CS.</span><span class="sxs-lookup"><span data-stu-id="120a9-148">In the new command prompt window, navigate to the EntityActivities\CS folder.</span></span>  
  
3.  <span data-ttu-id="120a9-149">Тип `cleanup.cmd` и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="120a9-149">Type `cleanup.cmd` and press ENTER.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="120a9-150">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="120a9-150">The samples may already be installed on your machine.</span></span> <span data-ttu-id="120a9-151">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="120a9-151">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="120a9-152">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="120a9-152">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="120a9-153">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="120a9-153">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\EntityActivities`