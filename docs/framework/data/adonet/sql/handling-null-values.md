---
title: Обработка значений NULL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f18b288f-b265-4bbe-957f-c6833c0645ef
ms.openlocfilehash: 091fde9a6149f72577e0cf38c8ebf1536abdf6ea
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738201"
---
# <a name="handling-null-values"></a>Обработка значений NULL
Значение NULL в реляционной базе данных используется, если значение в столбце неизвестно или отсутствует. Значение Null не является ни пустой строкой (для символьного типа данных или типа данных datetime), ни нулевым значением (для числовых типов данных). Спецификация ANSI SQL-92 устанавливает, что значение NULL должно быть одинаково для всех типов данных, так чтобы все значения NULL обрабатывались согласованно. Пространство имен <xref:System.Data.SqlTypes> предоставляет семантику NULL при реализации интерфейса <xref:System.Data.SqlTypes.INullable>. Каждый из типов данных в <xref:System.Data.SqlTypes> имеет свое собственное свойство `IsNull` и значение `Null`, которое может быть присвоено экземпляру этого типа данных.  
  
> [!NOTE]
> В .NET Framework версии 2.0 введена поддержка типов данных, допускающих значения NULL, что дает программистам возможность расширить тип значения, чтобы могли быть представлены все значения базового типа. Эти типы среды CLR, допускающие значения NULL, представляют экземпляр структуры <xref:System.Nullable>. Такая возможность особенно полезна, если для типов значений могут устанавливаться и сниматься флажки, что обеспечивает улучшенную совместимость с типами объектов. Типы среды CLR, допускающие значения NULL, не предназначены для хранения значений NULL базы данных, т. к. поведение значения NULL для ANSI SQL отличается от поведения ссылки `null` (или `Nothing` в Visual Basic). Для работы со значениями NULL ANSI SQL базы данных используйте значения NULL <xref:System.Data.SqlTypes>, а не <xref:System.Nullable>. Дополнительные сведения о работе с типами данных CLR Nullable в Visual Basic см. в разделе [типы значений](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md), C# допускающих значения NULL, а для см. в статье типы [значений Nullable](../../../../csharp/language-reference/builtin-types/nullable-value-types.md).  
  
## <a name="nulls-and-three-valued-logic"></a>Значения NULL и тройственная логика  
 Разрешение использовать значения NULL в определениях столбцов вводит в приложение тройственную логику. Результатом оценки сравнения может быть одно из трех условий.  
  
- True  
  
- False  
  
- Неизвестно  
  
 Так как значения NULL рассматриваются как неизвестные, два значения NULL, сравниваемые друг с другом, не считаются равными. В выражениях, использующих арифметические операторы, если какие-либо из операндов равны NULL, результат также равен NULL.  
  
## <a name="nulls-and-sqlboolean"></a>Значения NULL и SqlBoolean  
 Сравнение каких-либо <xref:System.Data.SqlTypes> возвратит <xref:System.Data.SqlTypes.SqlBoolean>. Функция `IsNull` для каждого `SqlType` возвращает <xref:System.Data.SqlTypes.SqlBoolean> и может использоваться для проверки значений NULL. Следующие проверки истинности демонстрируют, как операторы AND, OR и NOT функционируют в присутствии значения NULL. (T=true, F=false и U=неизвестно, т.е. NULL).  
  
 ![Таблица истинности](./media/truthtable-bpuedev11.gif "TruthTable_bpuedev11")  
  
### <a name="understanding-the-ansi_nulls-option"></a>Основные сведения о параметре ANSI_NULLS  
 <xref:System.Data.SqlTypes> предоставляет ту же семантику, что и в случае, когда параметр ANSI_NULLS установлен в SQL Server. Все арифметические операторы (+,-, \*,/,%), битовые операторы (~, &, \|) и большинство функций возвращают значение null, если любой из операндов или аргументов имеет значение null, за исключением `IsNull`свойства.  
  
 Стандарт ANSI SQL-92 не поддерживает *ColumnName* = NULL в предложении WHERE. В SQL Server параметр ANSI_NULLS контролирует как допустимость значений NULL по умолчанию, так и оценку сравнений со значениями NULL. Если параметр ANSI_NULLS установлен в значение ON (по умолчанию), в выражениях при проверке на значения NULL должен использоваться оператор IS NULL. Например, при параметре ANSI_NULLS, установленном в значение ON, результатом следующего сравнения всегда является UNKNOWN:  
  
```sql
colname > NULL  
```  
  
 Результатом сравнения переменной, содержащей значение NULL, также является UNKNOWN:  
  
```sql
colname > @MyVariable  
```  
  
 Для проверки на значение NULL используется предикат IS NULL или IS NOT NULL. Это может усложнить предложение WHERE. Например, в столбце TerritoryID таблицы «Заказчики AdventureWorks» разрешены значения NULL. Если инструкция SELECT используется для проверки на значения NULL в дополнение к другим, она должна включать предикат IS NULL:  
  
```sql
SELECT CustomerID, AccountNumber, TerritoryID  
FROM AdventureWorks.Sales.Customer  
WHERE TerritoryID IN (1, 2, 3)  
   OR TerritoryID IS NULL  
```  
  
 Если в SQL Server параметр ANSI_NULLS установлен в OFF, можно создать выражения, использующие оператор равенства для сравнения со значением NULL. Однако нельзя предотвратить в разных соединениях установку параметров NULL для данного соединения. Использование IS NULL для проверки на значения NULL всегда работает, независимо от установки ANSI_NULLS для соединения.  
  
 Установка ANSI_NULLS в OFF не поддерживается в `DataSet`, который всегда следует стандарту ANSI SQL-92 для обработки значений NULL в <xref:System.Data.SqlTypes>.  
  
## <a name="assigning-null-values"></a>Присвоение значений Null  
 Значения NULL являются особыми, и их семантика хранения и присвоения различается для разных систем типов и систем хранения. `Dataset` предназначен для использования с различными системами типов и хранения.  
  
 В этом разделе описывается семантика присвоения значений NULL для <xref:System.Data.DataColumn> в <xref:System.Data.DataRow> для разных систем типов.  
  
 `DBNull.Value`  
 Это присвоение действительно для `DataColumn` любого типа. Если тип реализует `INullable`, `DBNull.Value` приводится в соответствующее строго типизированное значение NULL.  
  
 `SqlType.Null`  
 Все типы данных <xref:System.Data.SqlTypes> реализуют `INullable`. Если строго типизированное значение NULL может быть преобразовано в тип данных столбца с использованием неявных операторов приведения, присвоение должно выполняться. В противном случае возникает исключение недопустимого приведения.  
  
 `null`  
 Если NULL является допустимым значением для типа данных данного `DataColumn`, оно приводится в соответствующее `DbNull.Value` или `Null`, связанное с `INullable` типом (`SqlType.Null`)  
  
 `derivedUdt.Null`  
 Для столбцов определяемого пользователем типа значения NULL всегда сохраняются на основании типа, связанного с `DataColumn`. Рассмотрим случай определяемого пользователем типа, связанного с `DataColumn`, который не реализует `INullable`, хотя его подкласс реализует. В этом случае, если присваивается значение NULL со строгой типизацией, которое связано с производным классом, оно хранится как нетипизированное `DbNull.Value`, т. к. хранение значения NULL всегда согласовано с типом данных DataColumn.  
  
> [!NOTE]
> Структура `Nullable<T>` или <xref:System.Nullable> в настоящее время в `DataSet` не поддерживается.  
  
### <a name="multiple-column-row-assignment"></a>Присвоение для многих столбцов или строк  
 `DataTable.Add`, `DataTable.LoadDataRow` или другие API, которые принимают <xref:System.Data.DataRow.ItemArray%2A>, которые сопоставлены со строкой, сопоставляют «NULL» значению по умолчанию для DataColumn. Если объект в массиве содержит `DbNull.Value` или его строго типизированный аналог, применяются те же вышеописанные правила.  
  
 Кроме того, следующие правила применяются для экземпляра присваивания `DataRow.["columnName"]` значений NULL.  
  
1. *Значение по умолчанию* `DbNull.Value` для всех, кроме строго типизированных столбцов NULL, где это строго типизированное значение null.  
  
2. Значения NULL никогда не записываются в XML-файлы во время сериализации (в виде "xsi:nil").  
  
3. Все отличные от NULL значения, включая значения по умолчанию, при сериализации всегда записываются в XML. Это отличается от семантики XSD и XML, где значение NULL (xsi:nil) является явным, а значение по умолчанию - неявным (если оно не присутствует в XML, проверяющее средство синтаксического анализа может получить его из связанной схемы XSD). Для `DataTable` справедливо и обратное: значение NULL является неявным, а значение по умолчанию - явным.  
  
4. Всем отсутствующим значениям столбцов для строк, считываемым из входных XML-данных, присваивается значение NULL. Строкам, созданным методом <xref:System.Data.DataTable.NewRow%2A> или аналогичным методом, присваивается значение по умолчанию для DataColumn.  
  
5. Метод <xref:System.Data.DataRow.IsNull%2A> возвращает `true` и для `DbNull.Value`, и для `INullable.Null`.  
  
## <a name="assigning-null-values"></a>Присвоение значений Null  
 Аргументом по умолчанию для любого экземпляра <xref:System.Data.SqlTypes> является значение NULL.  
  
 Значения NULL в <xref:System.Data.SqlTypes> зависят от типа и не могут представляться одним значением, таким как `DbNull`. Для проверки на значения NULL используется свойство `IsNull`.  
  
 Значения NULL могут присваиваться <xref:System.Data.DataColumn>, как показано в следующем примере кода. Значения NULL можно непосредственно присваивать переменным `SqlTypes` без возникновения исключения.  
  
### <a name="example"></a>Пример  
 В следующем примере кода создается <xref:System.Data.DataTable> с двумя столбцами, определенными как <xref:System.Data.SqlTypes.SqlInt32> и <xref:System.Data.SqlTypes.SqlString>. Код добавляет одну строку известных значений, одну строку значений NULL и затем производит итерацию по <xref:System.Data.DataTable>, присваивая значения переменным и отображая выходные данные в окне консоли.  
  
 [!code-csharp[DataWorks SqlTypes.IsNull#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.IsNull/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.IsNull#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.IsNull/VB/source.vb#1)]  
  
 В результате выполнения данного примера выдаются следующие результаты:  
  
```output
isColumnNull=False, ID=123, Description=Side Mirror  
isColumnNull=True, ID=Null, Description=Null  
```  
  
## <a name="comparing-null-values-with-sqltypes-and-clr-types"></a>Сравнение значений NULL с типами SqlType и CLR  
 При сравнении значений NULL важно понимать разницу между способом, которым метод `Equals` оценивает значения NULL в <xref:System.Data.SqlTypes>, и способом его работы с типами среды CLR. Все методы <xref:System.Data.SqlTypes>`Equals` используют семантику базы данных для оценки значений NULL: если одно из значений или оба значения равны NULL, то результатом сравнения является NULL. С другой стороны, результатом использования метода среды CLR `Equals` на двух <xref:System.Data.SqlTypes> является true, если оба значения являются NULL. Это отражает разницу между использованием метода экземпляра, например метода среды CLR `String.Equals`, и использованием статического или общего метода `SqlString.Equals`.  
  
 Следующий пример демонстрирует разницу в результатах методов `SqlString.Equals` и `String.Equals`, если каждому посылается пара значений NULL, а затем пара пустых строк.  
  
 [!code-csharp[DataWorks SqlTypes.CompareNulls#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.CompareNulls/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.CompareNulls#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.CompareNulls/VB/source.vb#1)]  
  
 Этот код выводит следующие результаты:  
  
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
  
## <a name="see-also"></a>См. также

- [Типы данных SQL Server и ADO.NET](sql-server-data-types.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
