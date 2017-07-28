---
title: "Walkthrough: Using BatchBlock and BatchedJoinBlock to Improve Efficiency | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Task Parallel Library, dataflows"
  - "TPL dataflow library, improving efficiency"
ms.assetid: 5beb4983-80c2-4f60-8c51-a07f9fd94cb3
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Walkthrough: Using BatchBlock and BatchedJoinBlock to Improve Efficiency
Библиотека потоков данных TPL предоставляет классы <xref:System.Threading.Tasks.Dataflow.BatchBlock%601?displayProperty=fullName> и <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602?displayProperty=fullName>, чтобы пользователь мог получить буферные данные из одного или нескольких источников и затем передавать эти данные в виде одной коллекции.  Этот механизм пакетной обработки полезен при сборе данных из одного или нескольких источников и дальнейшей обработке различных частей данных в пакетном режиме.  Например, рассмотрим приложение, использующее поток данных для вставки записи в базу данных.  Эта операция может быть эффективнее, если несколько элементов добавляются одновременно, а не последовательно по одному.  В этом документе описано, как использовать класс <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> для увеличения эффективности подобных операций вставки в базу данных.  Также он описывает, как использовать класс <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> для захвата и результатов, и всех исключений, возникающих при выполнении программой считывания из базы данных.  
  
> [!TIP]
>  Библиотека потоков данных TPL \(пространство имен <xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\) не поставляется с [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  Чтобы установить пространство имен <xref:System.Threading.Tasks.Dataflow>, откройте ваш проект в [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], выберите пункт **Manage NuGet Packages** в меню Проект и выполните поиск пакета `Microsoft.Tpl.Dataflow` в сети.  
  
## Обязательные компоненты  
  
1.  Прочитайте раздел "Блоки объединения" в документе [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) перед освоением этого руководства.  
  
2.  Убедитесь, что на вашем компьютере находятся копии базы данных Northwind, Northwind.sdf.  Этот файл обычно находится в папке %Program Files%\\Microsoft SQL Server Compact Edition\\v3.5\\Samples\\.  
  
    > [!IMPORTANT]
    >  В некоторых версиях Windows невозможно подключиться к Northwind.sdf, если [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] не работает в режиме администратора.  Для подключения к Northwind.sdf, запустите командную строку [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] или [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] в режиме **Запуск от имени администратора**.  
  
 Это пошаговое руководство содержит следующие подразделы.  
  
-   [Создание консольного приложения](#creating)  
  
-   [Определение класса "Сотрудник"](#employeeClass)  
  
-   [Определение операций базы данных сотрудников.](#operations)  
  
-   [Добавление данных о сотруднике в базу данных без использования буферизации](#nonBuffering)  
  
-   [Использование буферизации для добавления данных о сотруднике в базу данных](#buffering)  
  
-   [Использование объединения буферизированных данных для считывания данных о сотруднике из базы данных](#bufferedJoin)  
  
-   [Полный код примера](#complete)  
  
<a name="creating"></a>   
## Создание консольного приложения  
  
<a name="consoleApp"></a>   
1.  В [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] создайте проект **Консольное приложение** Visual Basic или Visual C\#.  В этом документе проект называется `DataflowBatchDatabase`.  
  
2.  В проект добавьте ссылку на System.Data.SqlServerCe.dll и ссылку на System.Threading.Tasks.Dataflow.dll.  
  
3.  Убедитесь, что Form1.cs \(Form1.vb для [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) содержит следующие операторы `using` \(`Imports` в [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\).  
  
     [!code-csharp[TPLDataflow_BatchDatabase#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#1)]
     [!code-vb[TPLDataflow_BatchDatabase#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#1)]  
  
4.  Добавьте в класс `Program` следующие члены данных.  
  
     [!code-csharp[TPLDataflow_BatchDatabase#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#2)]
     [!code-vb[TPLDataflow_BatchDatabase#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#2)]  
  
<a name="employeeClass"></a>   
## Определение класса "Сотрудник"  
 Добавьте в класс `Program` класс `Employee`.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#3)]
 [!code-vb[TPLDataflow_BatchDatabase#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#3)]  
  
 В классе `Employee` присутствуют три свойства: `EmployeeID`, `LastName` и `FirstName`,  Эти свойства соответствуют столбцам `Employee ID`, `Last Name` и `First Name` в таблице `Employees` в базе данных Northwind.  Для этой демонстрации в классе `Employee` также определяется метод `Random`, который создает объект `Employee` с случайными значениями свойств.  
  
<a name="operations"></a>   
## Определение операций базы данных сотрудников.  
 Добавьте в класс `Program` методы `InsertEmployees`, `GetEmployeeCount` и `GetEmployeeID`.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#4)]
 [!code-vb[TPLDataflow_BatchDatabase#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#4)]  
  
 Метод `InsertEmployees` добавляет новые записи "Сотрудник" в базу данных.  Метод `GetEmployeeCount` получает число записей в таблице `Employees`.  Метод `GetEmployeeID` получает идентификатор первого сотрудника, который имеет указанное имя.  Каждый из этих методов принимает строку подключения к базе данных Northwind и использует функцию из пространства имен `System.Data.SqlServerCe` для обмена данными с базой данных.  
  
<a name="nonBuffering"></a>   
## Добавление данных о сотруднике в базу данных без использования буферизации  
 Добавьте в класс `Program` методы `AddEmployees` и `PostRandomEmployees`.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#5)]
 [!code-vb[TPLDataflow_BatchDatabase#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#5)]  
  
 Метод `AddEmployees` добавляет случайные данные о сотрудниках в базу данных с помощью потока данных.  Он создает объект <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> вызывает метод `InsertEmployees` для добавления записи о сотруднике в базу данных.  Метод `AddEmployees` затем вызывает метод `PostRandomEmployees` для прикрепления нескольких объектов `Employee` к объекту <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>.  Метод `AddEmployees` затем ожидает завершения всех операций вставки.  
  
<a name="buffering"></a>   
## Использование буферизации для добавления данных о сотруднике в базу данных  
 Добавьте метод `AddEmployeesBatched` в класс `Program`.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#6)]
 [!code-vb[TPLDataflow_BatchDatabase#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#6)]  
  
 Этот метод похож на `AddEmployees`, за исключением того, что он использует класс <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> для буферизации нескольких объектов `Employee` прежде, чем они будут отправлены <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>.  Поскольку класс <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> выдает на выходе несколько элементов в виде коллекции, объект <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> изменен для работы с массивом объектов `Employee`.  Как и в методе `AddEmployees`, `AddEmployeesBatched` вызывает метод `PostRandomEmployees` для создания нескольких объектов `Employee`; однако `AddEmployeesBatched` отправляет эти объекты объекту <xref:System.Threading.Tasks.Dataflow.BatchBlock%601>.  Метод `AddEmployeesBatched`  также ожидает завершения всех операций вставки.  
  
<a name="bufferedJoin"></a>   
## Использование объединения буферизированных данных для считывания данных о сотруднике из базы данных  
 Добавьте метод `GetRandomEmployees` в класс `Program`.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#7)]
 [!code-vb[TPLDataflow_BatchDatabase#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#7)]  
  
 Этот метод выводит сведения о случайных сотрудниках на консоль.  Он создает несколько произвольных объектов `Employee` и вызывает метод `GetEmployeeID` для извлечения уникального идентификатора каждого объекта.  Поскольку метод `GetEmployeeID` создает исключение, если не найден сотрудник с данными именем и фамилией, метод `GetRandomEmployees` использует класс <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> для хранения объектов `Employee` в случае успешного вызова `GetEmployeeID` и объектов <xref:System.Exception?displayProperty=fullName> для вызовов, которые завершились ошибкой.  Объект <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> в этом примере работает с объектом <xref:System.Tuple%602>, содержащим список объектов `Employee` и список объектов <xref:System.Exception>.  Объект <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> передает эти данные, когда в сумме количество полученных объектов `Employee` и <xref:System.Exception> равно размеру пакета  
  
<a name="complete"></a>   
## Полный код примера  
 Ниже приведен полный пример кода.  Метод `Main` сравнивает время выполнения пакетной вставки в базу данных и время выполнения непакетной вставки.  В нем также демонстрируется использование объединения буферизированных данных для чтения данных о сотруднике, помимо этого он докладывает об ошибках.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#100)]
 [!code-vb[TPLDataflow_BatchDatabase#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#100)]  
  
## См. также  
 [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)