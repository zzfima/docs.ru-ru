---
title: Обработка значений NULL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f18b288f-b265-4bbe-957f-c6833c0645ef
ms.openlocfilehash: c64f11c00174981925342f1493ef0b809a57ecb0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148651"
---
# <a name="handling-null-values"></a>Обработка значений NULL
Значение NULL в реляционной базе данных используется, если значение в столбце неизвестно или отсутствует. NULL не является ни пустой строкой (для типов данных character или datetime), ни нулевым значением (для числовых типов данных). В спецификации ANSI SQL-92 указано, что значение NULL должно быть одинаковым для всех типов данных, чтобы все значения NULL обрабатывались согласованно. Пространство имен <xref:System.Data.SqlTypes> обеспечивает семантику со значением NULL, реализуя интерфейс <xref:System.Data.SqlTypes.INullable>. Каждый из типов данных в <xref:System.Data.SqlTypes> имеет собственное свойство `IsNull` и значение `Null`, которое может быть назначено экземпляру этого типа данных.  
  
> [!NOTE]
> В .NET Framework версии 2.0 введена поддержка типов данных, допускающих значения NULL, что дает программистам возможность расширить тип значения, чтобы могли быть представлены все значения базового типа. Эти типы CLR, допускающие значение NULL, представляют экземпляр структуры <xref:System.Nullable>. Эта возможность особенно полезна, если типы значений упакованы и распакованы, что обеспечивает улучшенную совместимость с типами объектов. Типы CLR, допускающие значение NULL, не предназначены для хранения значений NULL базы данных, так как значение NULL ANSI SQL не работает так же, как ссылка на `null` (или `Nothing` в Visual Basic). Для работы со значениями NULL в базе данных ANSI SQL используйте значения NULL <xref:System.Data.SqlTypes> вместо <xref:System.Nullable>. Для получения дополнительной информации о работе с недействительными типами CLR в Visual Basic см. [Недействительные типы значений,](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)а для СЗ см. [Nullable value types](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)  
  
## <a name="nulls-and-three-valued-logic"></a>Значения NULL и тройственная логика  
 Разрешение значений NULL в определениях столбцов вводит в приложение логику трех значений. Результатом сравнения может быть одно из трех условий:  
  
- True  
  
- False  
  
- Неизвестно  
  
 Так как значение NULL считается неизвестным, два значения NULL, сравниваемые друг с другом, не считаются равными. В выражениях, использующих арифметические операторы, если какой-либо из операндов имеет значение NULL, результат также равен NULL.  
  
## <a name="nulls-and-sqlboolean"></a>Значения NULL и SqlBoolean  
 При сравнении между любыми типами <xref:System.Data.SqlTypes> будет возвращаться значение <xref:System.Data.SqlTypes.SqlBoolean>. Функция `IsNull` для каждого типа `SqlType` возвращает <xref:System.Data.SqlTypes.SqlBoolean> и может использоваться для проверки на наличие значений NULL. В следующих таблицах истинности показано, как работают операторы AND, OR и NOT при наличии значения NULL. (T = true, F = false и U = неизвестно или NULL.)  
  
 ![Таблица истинности](./media/truthtable-bpuedev11.gif "TruthTable_bpuedev11")  
  
### <a name="understanding-the-ansi_nulls-option"></a>Основные сведения о параметре ANSI_NULLS  
 <xref:System.Data.SqlTypes> предоставляет ту же семантику, что и при установке параметра ANSI_NULLS в SQL Server. Все арифметические операторы (яп., -,, \*/, \|%), bitwise операторов (я, &, ), и большинство функций `IsNull`вернуть недействительными, если какой-либо из operands или аргументы являются недействительными, за исключением собственности .  
  
 Стандарт ANSI SQL-92 не поддерживает *columnName* = NULL в предложении WHERE. В SQL Server параметр ANSI_NULLS управляет допустимостью значений NULL по умолчанию в базе данных и вычислением сравнений со значениями NULL. Если параметр ANSI_NULLS включен (по умолчанию), то при проверке на наличие значений NULL в выражениях должен использоваться оператор IS NULL. Например, результатом следующего сравнения всегда является неизвестность при включенном параметре ANSI_NULLS:  
  
```sql
colname > NULL  
```  
  
 Сравнение с переменной, содержащей значение NULL, также приводит к неизвестному результату:  
  
```sql
colname > @MyVariable  
```  
  
 Для тестирования на значение NULL используются предикаты IS NULL и IS NOT NULL. Это может усложнить предложение WHERE. Например, столбец TerritoryID в таблице AdventureWorks Customer допускает значения NULL. Если инструкция SELECT используется для тестирования на значения NULL в дополнение к другим, она должна включать предикат IS NULL:  
  
```sql
SELECT CustomerID, AccountNumber, TerritoryID  
FROM AdventureWorks.Sales.Customer  
WHERE TerritoryID IN (1, 2, 3)  
   OR TerritoryID IS NULL  
```  
  
 Если в SQL Server параметр ANSI_NULLS отключен, можно создать выражения, которые используют оператор равенства для сравнения со значением NULL. Однако нельзя запретить другим подключениям задавать параметры NULL для этого подключения. Использование параметра IS NULL для проверки на наличие значений NULL всегда работает, независимо от установленного значения ANSI_NULLS для подключения.  
  
 Установка ANSI_NULLS OFF не поддерживается в `DataSet`, который всегда соответствует стандарту ANSI SQL-92 для обработки значений NULL в <xref:System.Data.SqlTypes>.  
  
## <a name="assigning-null-values"></a>Присвоение значений Null  
 Значения NULL являются специальными, и их семантика хранения и назначения различается в разных системах типов и системах хранения. `Dataset` предназначен для использования с различными системами типов и хранения.  
  
 В этом разделе описывается семантика значений NULL для присвоения значений NULL для <xref:System.Data.DataColumn> в <xref:System.Data.DataRow> в различных системах типов.  
  
 `DBNull.Value`  
 Это назначение допустимо для любого типа `DataColumn`. Если тип реализует `INullable`, `DBNull.Value` приводится к соответствующему строго типизированному значению NULL.  
  
 `SqlType.Null`  
 Все типы данных <xref:System.Data.SqlTypes> реализуют `INullable`. Если строго типизированное значение NULL может быть преобразовано в тип данных столбца с помощью операторов неявного приведения, то назначение должно быть принятым. Иначе будет вызвано исключение недопустимого приведения.  
  
 `null`  
 Если значение NULL является допустимым для указанного типа данных `DataColumn`, оно приводится к соответствующему значению `DbNull.Value` или `Null`, связанному с типом `INullable` (`SqlType.Null`).  
  
 `derivedUdt.Null`  
 Для столбцов пользовательского типа значения NULL всегда хранятся в зависимости от типа, связанного с `DataColumn`. Рассмотрим случай пользовательского типа, связанного с `DataColumn`, который не реализует `INullable` в отличие от своего подкласса. В этом случае, если назначено строго типизированное значение NULL, связанное с производным классом, оно сохраняется как нетипизированное значение `DbNull.Value`, так как хранилище значений NULL всегда согласуется с типом данных DataColumn.  
  
> [!NOTE]
> В настоящее время структура `Nullable<T>` или <xref:System.Nullable> не поддерживается в `DataSet`.  
  
### <a name="multiple-column-row-assignment"></a>Присвоение для многих столбцов или строк  
 `DataTable.Add`, `DataTable.LoadDataRow` или другие API-интерфейсы, принимающие массив <xref:System.Data.DataRow.ItemArray%2A>, который сопоставляется со строкой, сопоставляют значение NULL со значением по умолчанию DataColumn. Если объект в массиве содержит `DbNull.Value` или строго типизированный аналог, применяются те же правила, которые описаны выше.  
  
 Кроме того, следующие правила применяются к экземпляру назначений NULL `DataRow.["columnName"]`:  
  
1. Используемое по умолчанию значение *default* является `DbNull.Value` для всех столбцов, за исключением строго типизированных нулевых столбцов с допустимыми строго типизированными значениями NULL.  
  
2. Значения NULL никогда не записываются во время сериализации в XML-файлы (как в xsi:nil).  
  
3. Все значения, в том числе по умолчанию, отличные от NULL, всегда записываются при сериализации в XML. Это отличается от семантики XSD/XML, где значение NULL (xsi: nil) является явным, а значение по умолчанию — неявным (если отсутствует в XML, то проверяющее средство синтаксического анализа может получить его из связанной схемы XSD). Обратное верно для `DataTable`: значение NULL является неявным, а значение по умолчанию — явным.  
  
4. Всем отсутствующим значениям столбцов для строк, считываемых из входных данных XML, присваивается значение NULL. Строкам, созданным с помощью <xref:System.Data.DataTable.NewRow%2A> или аналогичных методов, присваивается значение по умолчанию DataColumn.  
  
5. Метод <xref:System.Data.DataRow.IsNull%2A> возвращает `true` как для `DbNull.Value`, так и для `INullable.Null`.  
  
## <a name="assigning-null-values"></a>Присвоение значений Null  
 Значение по умолчанию для любого экземпляра <xref:System.Data.SqlTypes>— NULL.  
  
 Значения NULL в <xref:System.Data.SqlTypes> относятся к определенному типу и не могут быть представлены одним значением, таким как `DbNull`. Чтобы проверить на наличие значений NULL, используйте свойство `IsNull`.  
  
 Значения NULL могут быть назначены <xref:System.Data.DataColumn>, как показано в следующем примере кода. Вы можете напрямую назначить значения NULL для переменных `SqlTypes` без запуска исключения.  
  
### <a name="example"></a>Пример  
 В следующем примере кода показано создание <xref:System.Data.DataTable> с двумя столбцами, определенными как <xref:System.Data.SqlTypes.SqlInt32> и <xref:System.Data.SqlTypes.SqlString>. Код добавляет одну строку известных значений, одну строку значений NULL, а затем выполняет итерацию по <xref:System.Data.DataTable>, присваивая значения переменным и отображая выходные данные в окне консоли.  
  
 [!code-csharp[DataWorks SqlTypes.IsNull#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.IsNull/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.IsNull#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.IsNull/VB/source.vb#1)]  
  
 В этом примере отображаются следующие результаты:  
  
```output
isColumnNull=False, ID=123, Description=Side Mirror  
isColumnNull=True, ID=Null, Description=Null  
```  
  
## <a name="comparing-null-values-with-sqltypes-and-clr-types"></a>Сравнение значений NULL с типами SqlType и CLR  
 При сравнении значений NULL важно понимать разницу между тем, как метод `Equals` вычисляет значения NULL в <xref:System.Data.SqlTypes> по сравнению с тем, как он работает с типами CLR. Все методы <xref:System.Data.SqlTypes>`Equals` используют семантику базы данных для вычисления значений NULL. Если одно или оба значения являются NULL, результатом сравнения будет NULL. С другой стороны, при использовании метода `Equals` CLR для двух <xref:System.Data.SqlTypes> вернется значение true, если оба значения соответствуют NULL. Это отражает разницу между использованием метода экземпляра, такого как метод `String.Equals` CLR, и использованием статического или общего метода `SqlString.Equals`.  
  
 В следующем примере показана разница результатов между методами `SqlString.Equals` и `String.Equals`, если каждому из них передается пара значений NULL, а затем пара пустых строк.  
  
 [!code-csharp[DataWorks SqlTypes.CompareNulls#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.CompareNulls/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.CompareNulls#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.CompareNulls/VB/source.vb#1)]  
  
 Получается следующий вывод:  
  
```output
SqlString.Equals shared/static method:  
  Two nulls=Null  
  
String.Equals instance method:  
  Two nulls=True  
  
SqlString.Equals shared/static method:  
  Two empty strings=True  
  
String.Equals instance method:  
  Two empty strings=True
```  
  
## <a name="see-also"></a>См. также раздел

- [Типы и ADO.NET серверных данных S'L](sql-server-data-types.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
