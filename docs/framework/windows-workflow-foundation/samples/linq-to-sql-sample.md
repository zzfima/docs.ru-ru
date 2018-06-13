---
title: LINQ to SQL образца
ms.date: 03/30/2017
ms.assetid: 5f39db9e-0e62-42c9-8c98-bb8b54cec98c
ms.openlocfilehash: 3cfcaf3de1a22b8bb5505083f127a9888b99dbd8
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33806722"
---
# <a name="linq-to-sql-sample"></a><span data-ttu-id="c6eed-102">LINQ to SQL образца</span><span class="sxs-lookup"><span data-stu-id="c6eed-102">LINQ to SQL Sample</span></span>
<span data-ttu-id="c6eed-103">В этом образце показано создание действий, использующих запросы к сущностям LINQ to SQL из таблиц в базах данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c6eed-103">This sample demonstrates how to create an activity to use LINQ to SQL query entities from tables in SQL Server databases.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c6eed-104">Образцы WCF уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c6eed-104">The WCF samples may already be installed on your machine.</span></span> <span data-ttu-id="c6eed-105">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="c6eed-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\Samples\WCFWFCardspace`  
>   
>  <span data-ttu-id="c6eed-106">Если этот каталог не существует, щелкните ссылку "Загрузить образец" в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="c6eed-106">If this directory does not exist, click the download sample link at the top of this page.</span></span> <span data-ttu-id="c6eed-107">Обратите внимание, что этой ссылке происходит загрузка и установка всех [!INCLUDE[wf1](../../../../includes/wf1-md.md)], WCF, и [!INCLUDE[infocard](../../../../includes/infocard-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="c6eed-107">Note that this link downloads and installs all of the [!INCLUDE[wf1](../../../../includes/wf1-md.md)], WCF, and [!INCLUDE[infocard](../../../../includes/infocard-md.md)] samples.</span></span> <span data-ttu-id="c6eed-108">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="c6eed-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\Samples\WCFWFCardSpace\WF\Scenario\ActivityLibrary\Linq\LinqToSql`  
  
## <a name="activity-details-for-findinsqltable"></a><span data-ttu-id="c6eed-109">Сведения о действии FindInSqlTable</span><span class="sxs-lookup"><span data-stu-id="c6eed-109">Activity details for FindInSqlTable</span></span>  
 <span data-ttu-id="c6eed-110">Это действие позволяет пользователям создавать запросы к сущностям из таблиц в базе данных, используя LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="c6eed-110">This activity allows users to query entities from tables in a database using LINQ to SQL.</span></span> <span data-ttu-id="c6eed-111">Пользователи действия могут также указать предикат LINQ в форме лямбда-выражения для фильтрации результатов.</span><span class="sxs-lookup"><span data-stu-id="c6eed-111">Users of the activity can also provide a LINQ predicate in the form of a lambda expression to filter the results.</span></span> <span data-ttu-id="c6eed-112">Если не указан предикат, вся таблица возвращается.</span><span class="sxs-lookup"><span data-stu-id="c6eed-112">If no predicate is provided, the entire table is returned.</span></span> <span data-ttu-id="c6eed-113">В следующих сведениях о таблице подробно описаны свойства и возвращаемые значения для действия.</span><span class="sxs-lookup"><span data-stu-id="c6eed-113">The following table details the property and return values for the activity.</span></span>  
  
|<span data-ttu-id="c6eed-114">Свойство или возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c6eed-114">Property or Return Value</span></span>|<span data-ttu-id="c6eed-115">Описание</span><span class="sxs-lookup"><span data-stu-id="c6eed-115">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="c6eed-116">Свойство `Collection`</span><span class="sxs-lookup"><span data-stu-id="c6eed-116">`Collection` property</span></span>|<span data-ttu-id="c6eed-117">Обязательное свойство, в котором указывается исходная коллекция.</span><span class="sxs-lookup"><span data-stu-id="c6eed-117">A required property that specifies the source collection.</span></span>|  
|<span data-ttu-id="c6eed-118">Свойство `Predicate`</span><span class="sxs-lookup"><span data-stu-id="c6eed-118">`Predicate` property</span></span>|<span data-ttu-id="c6eed-119">Обязательное свойство, в котором указывается фильтр для коллекции в виде лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="c6eed-119">A required property that specifies the filter for the collection in the form of a lambda expression.</span></span>|  
|<span data-ttu-id="c6eed-120">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c6eed-120">Return Value</span></span>|<span data-ttu-id="c6eed-121">Фильтруемая коллекция.</span><span class="sxs-lookup"><span data-stu-id="c6eed-121">The filtered collection.</span></span>|  
  
## <a name="code-sample-that-uses-the-custom-activity"></a><span data-ttu-id="c6eed-122">Образец кода, использующий настраиваемое действие</span><span class="sxs-lookup"><span data-stu-id="c6eed-122">Code Sample that uses the Custom Activity</span></span>  
 <span data-ttu-id="c6eed-123">В следующем примере кода пользовательское действие `FindInSqlTable` применяется для нахождения всех строк в таблице SQL Server, имеющей название `Employee`, где значение столбца `Role` равно `SDE`.</span><span class="sxs-lookup"><span data-stu-id="c6eed-123">The following code example uses the `FindInSqlTable` custom activity to find all rows in a SQL Server table named `Employee` where the `Role` column is equal to `SDE`.</span></span>  
  
```csharp  
new FindInSqlTable<Employee>   
{  
    ConnectionString = @"Data Source=.\SQLExpress;Initial Catalog=LinqToSqlSample;Integrated Security=True",                          
    Predicate = new LambdaValue<Func<Employee, bool>>(c => new Func<Employee, bool>(emp => emp.Role.Equals("SDE"))),  
    Result = new OutArgument<IList<Employee>>(employees)  
},  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="c6eed-124">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="c6eed-124">To use this sample</span></span>  
  
1.  <span data-ttu-id="c6eed-125">Откройте окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="c6eed-125">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="c6eed-126">Перейдите в папку, содержащую этот образец.</span><span class="sxs-lookup"><span data-stu-id="c6eed-126">Navigate to the folder that contains this sample.</span></span>  
  
3.  <span data-ttu-id="c6eed-127">Запустите командный файл Setup.cmd.</span><span class="sxs-lookup"><span data-stu-id="c6eed-127">Run the Setup.cmd command file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6eed-128">Скрипт Setup.cmd пытается установить образец базы данных в SQL Server Express на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c6eed-128">The Setup.cmd script attempts to install the sample database in your local machine SQL Server Express.</span></span> <span data-ttu-id="c6eed-129">Для установки данного образца на другом экземпляре SQL Server отредактируйте Setup.cmd.</span><span class="sxs-lookup"><span data-stu-id="c6eed-129">If you want to install it in other SQL server instance, edit Setup.cmd.</span></span>  
  
     <span data-ttu-id="c6eed-130">Скрипт Setup.cmd выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="c6eed-130">The Setup.cmd script does the following actions.:</span></span>  
  
    -   <span data-ttu-id="c6eed-131">Создает базу данных c именем LinqToSqlSample.</span><span class="sxs-lookup"><span data-stu-id="c6eed-131">Creates a database called LinqToSqlSample.</span></span>  
  
    -   <span data-ttu-id="c6eed-132">Создает таблицу Roles.</span><span class="sxs-lookup"><span data-stu-id="c6eed-132">Creates a Roles table.</span></span>  
  
    -   <span data-ttu-id="c6eed-133">Создает таблицу Employees.</span><span class="sxs-lookup"><span data-stu-id="c6eed-133">Creates an Employees table.</span></span>  
  
    -   <span data-ttu-id="c6eed-134">Вставляет 3 записи в таблицу Roles.</span><span class="sxs-lookup"><span data-stu-id="c6eed-134">Inserts 3 records into the Roles table.</span></span>  
  
    -   <span data-ttu-id="c6eed-135">Вставляет 12 записей в таблицу Employees.</span><span class="sxs-lookup"><span data-stu-id="c6eed-135">Inserts 12 records into the Employees table.</span></span>  
  
4.  <span data-ttu-id="c6eed-136">Используя [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], откройте файл решения LinqToSQL.sln.</span><span class="sxs-lookup"><span data-stu-id="c6eed-136">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the LinqToSQL.sln solution file.</span></span>  
  
5.  <span data-ttu-id="c6eed-137">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="c6eed-137">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
6.  <span data-ttu-id="c6eed-138">Чтобы запустить решение, нажмите клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="c6eed-138">To run the solution, press F5.</span></span>  
  
#### <a name="to-uninstall-the-linqtosql-sample-database"></a><span data-ttu-id="c6eed-139">Удаление образца базы данных LinqToSql</span><span class="sxs-lookup"><span data-stu-id="c6eed-139">To uninstall the LinqToSql sample database</span></span>  
  
1.  <span data-ttu-id="c6eed-140">Откройте окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="c6eed-140">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="c6eed-141">Перейдите в папку, содержащую этот образец.</span><span class="sxs-lookup"><span data-stu-id="c6eed-141">Navigate to the folder that contains this sample.</span></span>  
  
3.  <span data-ttu-id="c6eed-142">Запустите командный файл Cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="c6eed-142">Run the Cleanup.cmd command file.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c6eed-143">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c6eed-143">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c6eed-144">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="c6eed-144">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c6eed-145">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="c6eed-145">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c6eed-146">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="c6eed-146">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Liiinq\LinqToSql`  
  
## <a name="see-also"></a><span data-ttu-id="c6eed-147">См. также</span><span class="sxs-lookup"><span data-stu-id="c6eed-147">See Also</span></span>  
 [<span data-ttu-id="c6eed-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="c6eed-148">LINQ to SQL</span></span>](http://go.microsoft.com/fwlink/?LinkId=150376)  
 [<span data-ttu-id="c6eed-149">Начало работы (LINQ to SQL)</span><span class="sxs-lookup"><span data-stu-id="c6eed-149">Getting Started (LINQ to SQL)</span></span>](http://go.microsoft.com/fwlink/?LinkId=150377)
