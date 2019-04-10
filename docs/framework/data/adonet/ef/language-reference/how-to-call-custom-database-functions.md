---
title: Практическое руководство. Вызов настраиваемых функций базы данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4354e5eb-dd45-469d-97fb-1c495705ee59
ms.openlocfilehash: cc2e25183649f6a95e7862520ccc5719f201277a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59311491"
---
# <a name="how-to-call-custom-database-functions"></a>Практическое руководство. Вызов настраиваемых функций базы данных
В данном разделе описаны процедуры вызова пользовательских функций, определенных в базе данных, из запросов LINQ to Entities.  
  
 Функции базы данных, вызываемые в запросах LINQ to Entities, выполняются в базе данных. При выполнении функций в базе данных может увеличиться производительность приложений.  
  
 Процедура, приведенная ниже, обеспечивает высокоуровневую структуру вызова пользовательской функции базы данных. В следующем примере подробно описаны шаги данной процедуры.  
  
### <a name="to-call-custom-functions-that-are-defined-in-the-database"></a>Вызов пользовательских функций, определенных в базе данных.  
  
1. Создайте пользовательскую функцию в базе данных.  
  
     Дополнительные сведения о создании пользовательских функций в SQL Server, см. в разделе [CREATE FUNCTION (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkID=139871).  
  
2. Объявите функцию на языке SSDL в EDMX-файле. Имя функции должно совпадать с именем функции, объявленной в базе данных.  
  
     Дополнительные сведения см. в разделе [функция элемент SSDL](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#function-element-ssdl).  
  
3. Добавьте соответствующий метод к классу в коде приложения и примените <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> к этому методу. Обратите внимание, что параметры атрибута <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> и <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> представляют собой имя пространства имен концептуальной модели и имя функции концептуальной модели соответственно. При разрешении имени функции для LINQ учитывается регистр.  
  
4. Вызовите метод в запросе LINQ to Entities.  
  
## <a name="example"></a>Пример  
 В следующем примере показываются процедуры вызова пользовательской функции базы данных из запроса LINQ to Entities. В этом примере используется модель School. Сведения о модели School см. в разделе [Создание образца базы данных School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) и [Создание School EDMX-файл](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).  
  
 Следующий код добавляет функцию `AvgStudentGrade` в образец базы данных.  
  
> [!NOTE]
>  Шаги вызова пользовательской функции базы данных одинаковы, независимо от сервера базы данных. Однако следующий код предназначен специально для создания функции в базе данных SQL Server. Код для создания пользовательской функции на других серверах баз данных может отличаться.  
  
 [!code-sql[DP L2E MapToDBFunction#1](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp l2e maptodbfunction/tsql/create_avgstudentgrade.sql#1)]  
  
## <a name="example"></a>Пример  
 Затем объявите функцию на языке SSDL в EDMX-файле. в следующем коде объявляется функция `AvgStudentGrade` на языке SSDL:  
  
 [!code-xml[DP L2E MapToDBFunction#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/school.edmx#2)]  
  
## <a name="example"></a>Пример  
 Теперь следует создать метод и сопоставить его с функцией, объявленной на языке SSDL. Метод в следующем классе сопоставляется с функцией, определенной на языке SSDL (выше) с помощью <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>. При вызове этого метода в базе данных выполняется соответствующая функция.  
  
 [!code-csharp[DP L2E MapToDBFunction#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#3)]
 [!code-vb[DP L2E MapToDBFunction#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#3)]  
  
## <a name="example"></a>Пример  
 Наконец, вызовите метод в запросе LINQ to Entities. Следующий код отображает в консоли фамилии студентов и средние баллы:  
  
 [!code-csharp[DP L2E MapToDBFunction#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#4)]
 [!code-vb[DP L2E MapToDBFunction#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#4)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения о EDMX-файлах](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [Запросы в LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
