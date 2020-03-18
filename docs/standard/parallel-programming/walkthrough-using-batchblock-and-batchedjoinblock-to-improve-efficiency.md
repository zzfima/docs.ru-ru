---
title: Пошаговое руководство. Повышение эффективности с помощью BatchBlock и BatchedJoinBlock
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, improving efficiency
ms.assetid: 5beb4983-80c2-4f60-8c51-a07f9fd94cb3
ms.openlocfilehash: 4b2b6a6124bf8cc0fb3b379607135283678e3268
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73091362"
---
# <a name="walkthrough-using-batchblock-and-batchedjoinblock-to-improve-efficiency"></a>Пошаговое руководство. Повышение эффективности с помощью BatchBlock и BatchedJoinBlock

Библиотека потоков данных TPL предоставляет классы <xref:System.Threading.Tasks.Dataflow.BatchBlock%601?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602?displayProperty=nameWithType>, чтобы пользователь мог получать и помещать в буфер данные из одного или нескольких источников и затем передавать эти помещенные в буфер данные в виде одной коллекции. Этот механизм пакетной обработки полезен при сборе данных из одного или нескольких источников и дальнейшей обработке различных элементов данных в пакетном режиме. Например, рассмотрим приложение, использующее поток данных для вставки записей в базу данных. Эта операция может быть эффективнее, если несколько элементов добавляются одновременно, а не последовательно по одному. В этом документе описано, как использовать класс <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> для увеличения эффективности подобных операций вставки в базу данных. Также здесь приводится способ использования класса <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> для перехвата и результатов, и всех исключений, возникающих при выполнении программой считывания из базы данных.

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="prerequisites"></a>Prerequisites

1. Прочитайте описание блоков объединения в документации по [потокам данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md), прежде чем приступать к этому руководству.

2. Убедитесь, что на вашем компьютере есть копия базы данных Northwind, Northwind.sdf. Этот файл обычно находится в папке %Program Files%\Microsoft SQL Server Compact Edition\v3.5\Samples\\.

    > [!IMPORTANT]
    > В некоторых версиях Windows вы не сможете подключиться к Northwind.sdf, если Visual Studio работает не в режиме администратора. Для подключения к Northwind.sdf запустите Visual Studio или командную строку разработчика для Visual Studio в режиме **Запуск от имени администратора**.

Это пошаговое руководство содержит следующие разделы:

- [Создание консольного приложения](#creating)

- [Определение класса сотрудников](#employeeClass)

- [Определение операций базы данных сотрудников](#operations)

- [Добавление данных о сотруднике в базу данных без буферизации](#nonBuffering)

- [Использование буферизации для добавления данных о сотруднике в базу данных](#buffering)

- [Использование объединения буферизированных данных для считывания данных о сотруднике из базы данных](#bufferedJoin)

- [Полный пример](#complete)

<a name="creating"></a>

## <a name="creating-the-console-application"></a>Создание консольного приложения

1. В Visual Studio создайте проект **Консольное приложение** на Visual C# или Visual Basic. В этом документе проект называется `DataflowBatchDatabase`.

2. В проект добавьте ссылку на System.Data.SqlServerCe.dll и ссылку на System.Threading.Tasks.Dataflow.dll.

3. Убедитесь, что Form1.cs (Form1.vb для Visual Basic) содержит следующие операторы `using` (`Imports` в Visual Basic).

    [!code-csharp[TPLDataflow_BatchDatabase#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#1)]
    [!code-vb[TPLDataflow_BatchDatabase#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#1)]

4. Добавьте в класс `Program` следующие данные-члены.

    [!code-csharp[TPLDataflow_BatchDatabase#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#2)]
    [!code-vb[TPLDataflow_BatchDatabase#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#2)]

<a name="employeeClass"></a>

## <a name="defining-the-employee-class"></a>Определение класса "Сотрудник"

Добавьте в класс `Program` класс `Employee`.

[!code-csharp[TPLDataflow_BatchDatabase#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#3)]
[!code-vb[TPLDataflow_BatchDatabase#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#3)]

В классе `Employee` содержатся три свойства: `EmployeeID`, `LastName` и `FirstName`, Эти свойства соответствуют столбцам `Employee ID`, `Last Name` и `First Name` в таблице `Employees` в базе данных Northwind. Для этого примера в классе `Employee` также определяется метод `Random`, который создает объект `Employee` со случайными значениями свойств.

<a name="operations"></a>

## <a name="defining-employee-database-operations"></a>Определение операций базы данных сотрудников

Добавьте в класс `Program` методы `InsertEmployees`, `GetEmployeeCount` и `GetEmployeeID`.

[!code-csharp[TPLDataflow_BatchDatabase#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#4)]
[!code-vb[TPLDataflow_BatchDatabase#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#4)]

Метод `InsertEmployees` добавляет новые записи "Сотрудник" в базу данных. Метод `GetEmployeeCount` получает число записей в таблице `Employees`. Метод `GetEmployeeID` получает идентификатор первого сотрудника с указанным именем. Каждый из этих методов принимает строку подключения к базе данных Northwind и использует функциональные возможности пространства имен `System.Data.SqlServerCe` для обмена данными с базой данных.

<a name="nonBuffering"></a>

## <a name="adding-employee-data-to-the-database-without-using-buffering"></a>Добавление данных о сотруднике в базу данных без использования буферизации

Добавьте в класс `Program` методы `AddEmployees` и `PostRandomEmployees`.

[!code-csharp[TPLDataflow_BatchDatabase#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#5)]
[!code-vb[TPLDataflow_BatchDatabase#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#5)]

Метод `AddEmployees` добавляет случайные данные о сотрудниках в базу данных с помощью потока данных. Он создает объект <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, который вызывает метод `InsertEmployees` для добавления записи о сотруднике в базу данных. Метод `AddEmployees` затем вызывает метод `PostRandomEmployees` для прикрепления нескольких объектов `Employee` к объекту <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>. Метод `AddEmployees` затем ожидает завершения всех операций вставки.

<a name="buffering"></a>

## <a name="using-buffering-to-add-employee-data-to-the-database"></a>Использование буферизации для добавления данных о сотруднике в базу данных

Добавьте метод `Program` в класс `AddEmployeesBatched`.

[!code-csharp[TPLDataflow_BatchDatabase#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#6)]
[!code-vb[TPLDataflow_BatchDatabase#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#6)]

Этот метод похож на `AddEmployees` за исключением того, что он использует класс <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> для буферизации нескольких объектов `Employee` перед их отправкой объекту <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>. Поскольку класс <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> выдает на выходе несколько элементов в виде коллекции, объект <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> изменяется для работы с массивом объектов `Employee`. Как и в методе `AddEmployees`, `AddEmployeesBatched` вызывает метод `PostRandomEmployees` для отправки нескольких объектов `Employee`; однако `AddEmployeesBatched` отправляет эти объекты объекту <xref:System.Threading.Tasks.Dataflow.BatchBlock%601>. Метод `AddEmployeesBatched` также ожидает завершения всех операций вставки.

<a name="bufferedJoin"></a>

## <a name="using-buffered-join-to-read-employee-data-from-the-database"></a>Использование объединения буферизированных данных для считывания данных о сотруднике из базы данных

Добавьте метод `Program` в класс `GetRandomEmployees`.

[!code-csharp[TPLDataflow_BatchDatabase#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#7)]
[!code-vb[TPLDataflow_BatchDatabase#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#7)]

Этот метод выводит сведения о случайных сотрудниках на консоль. Он создает несколько произвольных объектов `Employee` и вызывает метод `GetEmployeeID` для извлечения уникального идентификатора каждого объекта. Поскольку метод `GetEmployeeID` создает исключение, если не найден сотрудник с данным именем и фамилией, метод `GetRandomEmployees` использует класс <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> для хранения объектов `Employee` в случае успешного вызова объектов `GetEmployeeID` и <xref:System.Exception?displayProperty=nameWithType> для вызовов, которые завершились ошибкой. Объект <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> в этом примере работает с объектом <xref:System.Tuple%602>, содержащим список объектов `Employee` и список объектов <xref:System.Exception>. Объект <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> передает эти данные, когда в сумме количество полученных объектов `Employee` и <xref:System.Exception> равняется размеру пакета.

<a name="complete"></a>

## <a name="the-complete-example"></a>Полный пример

В следующем примере показан полный код. Метод `Main` сравнивает время выполнения пакетной вставки в базу данных и время выполнения непакетной вставки. Здесь также демонстрируется использование объединения буферизированных данных для чтения сведений о сотруднике из базы данных, помимо этого он докладывает об ошибках.

[!code-csharp[TPLDataflow_BatchDatabase#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#100)]
[!code-vb[TPLDataflow_BatchDatabase#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#100)]

## <a name="see-also"></a>См. также раздел

- [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
