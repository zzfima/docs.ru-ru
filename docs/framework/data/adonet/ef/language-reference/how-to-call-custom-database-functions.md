---
title: Практическое руководство. Вызов настраиваемых функций базы данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4354e5eb-dd45-469d-97fb-1c495705ee59
ms.openlocfilehash: f3177ab98382506770c4655c62573da5c1d96c69
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78848760"
---
# <a name="how-to-call-custom-database-functions"></a>Практическое руководство. Вызов настраиваемых функций базы данных

В данном разделе описаны процедуры вызова пользовательских функций, определенных в базе данных, из запросов LINQ to Entities.

Функции базы данных, вызываемые в запросах LINQ to Entities, выполняются в базе данных. При выполнении функций в базе данных может увеличиться производительность приложений.

Процедура, приведенная ниже, обеспечивает высокоуровневую структуру вызова пользовательской функции базы данных. В следующем примере подробно описаны шаги данной процедуры.

## <a name="to-call-custom-functions-that-are-defined-in-the-database"></a>Вызов пользовательских функций, определенных в базе данных.

1. Создайте пользовательскую функцию в базе данных.

     Для получения более подробной информации о создании пользовательских функций в сервере S'L, [см.](/sql/t-sql/statements/create-function-transact-sql)

2. Объявите функцию на языке SSDL в EDMX-файле. Имя функции должно совпадать с именем функции, объявленной в базе данных.

     Для получения дополнительной информации [см.](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#function-element-ssdl)

3. Добавьте соответствующий метод к классу в коде приложения и примените <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> к этому методу. Обратите внимание, что параметры атрибута <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> и <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> представляют собой имя пространства имен концептуальной модели и имя функции концептуальной модели соответственно. При разрешении имени функции для LINQ учитывается регистр.

4. Вызовите метод в запросе LINQ to Entities.  

## <a name="example"></a>Пример

В следующем примере показываются процедуры вызова пользовательской функции базы данных из запроса LINQ to Entities. В этом примере используется модель School. Для получения информации о модели школы [Generating the School .edmx File](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100))см. [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))

Следующий код добавляет функцию `AvgStudentGrade` в образец базы данных.

> [!NOTE]
> Шаги вызова пользовательской функции базы данных одинаковы, независимо от сервера базы данных. Однако следующий код предназначен специально для создания функции в базе данных SQL Server. Код для создания пользовательской функции на других серверах баз данных может отличаться.

[!code-sql[DP L2E MapToDBFunction#1](~/samples/snippets/tsql/VS_Snippets_Data/dp l2e maptodbfunction/tsql/create_avgstudentgrade.sql#1)]

## <a name="example"></a>Пример

Затем объявите функцию в языке определения схемы хранилища (SSDL) файла *.edmx.* Следующий код декларирует функцию `AvgStudentGrade` в SSDL:

[!code-xml[DP L2E MapToDBFunction#2](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/school.edmx#2)]

## <a name="example"></a>Пример

Создайте метод и сообразуйте его с функцией, заявленной в SSDL. Метод в следующем классе сопоставляется с функцией, определенной на языке SSDL (выше) с помощью <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>. При вызове этого метода в базе данных выполняется соответствующая функция.

[!code-csharp[DP L2E MapToDBFunction#3](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#3)]
[!code-vb[DP L2E MapToDBFunction#3](~/samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#3)]

## <a name="example"></a>Пример

Наконец, вызовите метод в запросе LINQ to Entities. Следующий код отображает в консоли фамилии студентов и средние баллы:

[!code-csharp[DP L2E MapToDBFunction#4](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#4)]
[!code-vb[DP L2E MapToDBFunction#4](~/samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#4)]

## <a name="see-also"></a>См. также раздел

- [Общие сведения о EDMX-файлах](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [Запросы в LINQ to Entities](queries-in-linq-to-entities.md)
