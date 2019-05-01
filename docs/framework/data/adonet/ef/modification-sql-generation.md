---
title: Создание кода SQL для изменения данных
ms.date: 03/30/2017
ms.assetid: 2188a39d-46ed-4a8b-906a-c9f15e6fefd1
ms.openlocfilehash: 13ed7186981e82d47f00b6a38a4328ed75f527f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034136"
---
# <a name="modification-sql-generation"></a>Создание кода SQL для изменения данных

В этом разделе приведено описание разработки модуля создания кода SQL для изменения данных для конкретного поставщика (базы данных, совместимой с SQL:1999). Этот модуль обеспечивает преобразование дерева команд изменения в соответствующие инструкции INSERT, UPDATE или DELETE языка SQL.

Сведения о создании кода SQL для инструкций select, см. в разделе [создание кода SQL](../../../../../docs/framework/data/adonet/ef/sql-generation.md).

## <a name="overview-of-modification-command-trees"></a>Общие сведения о деревьях команд изменения

Модуль создания кода SQL для изменения данных формирует зависящие от базы данных инструкции языка SQL для изменения на основе полученных входных данных DbModificationCommandTree.

DbModificationCommandTree - это представление объектной модели операции DML (операции INSERT, UPDATE или DELETE), унаследованной от DbCommandTree. Существуют три реализации DbModificationCommandTree:

- DbInsertCommandTree

- DbUpdateCommandTree

- DbDeleteCommandTree

DbModificationCommandTree и его реализации, которые создаются по [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] всегда представляют операцию одной строки. В настоящем разделе рассматриваются указанные типы и их ограничения в .NET Framework версии 3.5.

![Схема](../../../../../docs/framework/data/adonet/ef/media/558ba7b3-dd19-48d0-b91e-30a76415bf5f.gif "558ba7b3-dd19-48d0-b91e-30a76415bf5f")

DbModificationCommandTree имеет свойство Target, которое представляет набор целей для операции изменения. Свойство Expression свойства Target, которое определяет входной набор, всегда имеет тип DbScanExpression.  DbScanExpression может представлять либо таблицу или представление, или набора данных, определенный с запросом, если свойство метаданных «Defining Query» его свойства Target имеет отличное от null.

Объект DbScanExpression, который представляет запрос, может достичь поставщика только как цель изменения, если набор был определен с помощью определяющего запроса в модели, но для соответствующей операции изменения не была предоставлена какая-либо функция. Поставщики могут оказаться неспособными поддерживать такой сценарий (например, поставщик SqlClient его не поддерживает).

DbInsertCommandTree представляет операцию вставки из одной строки, выраженную в виде дерева команд.

```csharp
public sealed class DbInsertCommandTree : DbModificationCommandTree {
   public IList<DbModificationClause> SetClauses { get }
   public DbExpression Returning { get }
}
```

DbUpdateCommandTree представляет операцию обновления из одной строки, выраженную в виде дерева команд.

DbDeleteCommandTree представляет операцию удаления из одной строки, выраженную в виде дерева команд.

### <a name="restrictions-on-modification-command-tree-properties"></a>Ограничения свойств дерева команд изменения

Следующие сведения и ограничения относятся к свойствам дерева команд изменения.

#### <a name="returning-in-dbinsertcommandtree-and-dbupdatecommandtree"></a>Свойство Returning объектов DbInsertCommandTree и DbUpdateCommandTree

Значение свойства Returning, отличное от null, указывает, что команда возвращает модуль чтения. В противном случае команда возвращает скалярное значение, указывающее число затронутых строк (вставленных или обновленных).

Значение Returning задает проекцию результатов, которые должны быть возвращены с учетом вставленных или обновленных строк. Это свойство может иметь только тип DbNewInstanceExpression, представляющий строку, каждый из аргументов которого является выражением DbPropertyExpression на основе выражения DbVariableReferenceExpression, представляющего ссылку на свойство Target соответствующего объекта DbModificationCommandTree. Свойства, представленные выражениями DbPropertyExpression, которые используются в свойстве Returning, всегда являются значениями, созданными или вычисленными хранилищем. В объекте DbInsertCommandTree свойство Returning не равно null, если по крайней мере одно свойство таблицы, в которую вставляется строка, указано как созданное или вычисленное хранилищем (что обозначается в языке SSDL с помощью StoreGeneratedPattern.Identity или StoreGeneratedPattern.Computed). В объектах DbUpdateCommandTree свойство Returning не равно null, если по крайней мере одно свойство таблицы, в которой обновляется строка, указано как вычисленное хранилищем (что в языке SSDL обозначается с помощью StoreGeneratedPattern.Computed).

#### <a name="setclauses-in-dbinsertcommandtree-and-dbupdatecommandtree"></a>Свойство SetClauses в объектах DbInsertCommandTree и DbUpdateCommandTree

Свойство SetClauses задает список предложений SET операций INSERT или UPDATE, которые определяют операцию INSERT или UPDATE.

```
The elements of the list are specified as type DbModificationClause, which specifies a single clause in an insert or update modification operation. DbSetClause inherits from DbModificationClause and specifies the clause in a modification operation that sets the value of a property. Beginning in version 3.5 of the .NET Framework, all elements in SetClauses are of type SetClause.
```

Property указывает свойство, которое должно быть обновлено. Это всегда выражение DbPropertyExpression на основе DbVariableReferenceExpression, которое представляет ссылку на свойство Target соответствующего объекта DbModificationCommandTree.

Выражение Value задает новое значение, которое применяется для обновления свойства. Оно относится к типу DbConstantExpression или DbNullExpression.

#### <a name="predicate-in-dbupdatecommandtree-and-dbdeletecommandtree"></a>Свойство Predicate в объектах DbUpdateCommandTree и DbDeleteCommandTree

Свойство Predicate указывает предикат, используемый для определения того, какие элементы целевой коллекции должны быть обновлены или удалены. Это дерево выражения, построенное исходя из следующего подмножества DbExpressions.

- DbComparisonExpression типа Equals, правый дочерний элемент которого является выражением DbPropertyExpression, ограниченные ниже, а левый дочерний DbConstantExpression.

- DbConstantExpression

- DbIsNullExpression DbPropertyExpression, ограниченные ниже

- Свойство DbPropertyExpression на основе выражения DbVariableReferenceExpression, представляющего ссылку на свойство Target соответствующего объекта DbModificationCommandTree.

- DbAndExpression

- DbNotExpression

- DbOrExpression

## <a name="modification-sql-generation-in-the-sample-provider"></a>Создание кода SQL для изменения данных в образце поставщика

[Образца поставщика Entity Framework](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) демонстрируются компоненты поставщиков данных ADO.NET, которые поддерживают [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Он предназначен для базы данных SQL Server 2005 и реализован как оболочка на основе поставщика данных System.Data.SqlClient ADO.NET 2.0.

Модуль создания кода SQL для изменения данных из образца поставщика (который находится в файле SQL Generation\DmlSqlGenerator.cs) принимает входные данные DbModificationCommandTree и вырабатывает одну инструкцию SQL изменения, за которой может следовать инструкция SELECT, обеспечивающая возврат модуля чтения, если это указано в DbModificationCommandTree. Следует отметить, что форма созданных команд зависит от целевой базы данных SQL Server.

### <a name="helper-classes-expressiontranslator"></a>Вспомогательные классы: Класс ExpressionTranslator

Класс ExpressionTranslator служит в качестве общего упрощенного преобразователя для всех свойств дерева команд изменения типа DbExpression. Он поддерживает преобразование только типов выражений, которыми ограничиваются свойства дерева команд изменения, и создается с учетом конкретных ограничений.

Ниже приведены сведения, касающиеся посещения конкретных типов выражений (узлы с тривиальными преобразованиями опущены).

### <a name="dbcomparisonexpression"></a>DbComparisonExpression

Если объект ExpressionTranslator создается со значением preserveMemberValues = true, а находящаяся справа константа представляет собой DbConstantExpression (а не DbNullExpression), он связывает левый операнд (DbPropertyExpressions) с этим выражением DbConstantExpression. Такой вариант используется, если возвращаемая инструкция SELECT должна быть создана для обозначения затронутой строки.

### <a name="dbconstantexpression"></a>DbConstantExpression

Для каждой посещенной константы создается параметр.

### <a name="dbpropertyexpression"></a>DbPropertyExpression

С учетом того, что экземпляр выражения DbPropertyExpression всегда представляет входную таблицу, при условии, что в ходе создания не был создан псевдоним (это происходит только при обновлении, когда используется табличная переменная), для входных данных не должен быть указан какой-либо псевдоним. В преобразовании по умолчанию применяется имя свойства.

## <a name="generating-an-insert-sql-command"></a>Создание команд INSERT языка SQL

Для каждого конкретного объекта DbInsertCommandTree из образца поставщика созданная команда INSERT соответствует одному из двух приведенных далее шаблонов INSERT.

Первый шаблон имеет команду для выполнения оператора INSERT с учетом значений из списка SetClauses и инструкции SELECT для возврата свойств, указанных в свойстве Returning для вставленной строки, если свойство Returning не имело значение null. Элемент предиката «\@ @ROWCOUNT > 0" имеет значение true, если строка была вставлена. Элемент предиката «keyMemberI = keyValueI &#124; scope_identity()» принимает форму «keyMemberI = scope_identity()» только в том случае, если keyMemberI — это ключ, созданный хранилищем, поскольку функция scope_identity() возвращает последнее значение identity, вставленное в identity ( столбец, созданный в хранилище).

```sql
-- first insert Template
INSERT <target>   [ (setClauseProperty0, .. setClausePropertyN)]
VALUES (setClauseValue0, .. setClauseValueN) |  DEFAULT VALUES

[SELECT <returning>
 FROM <target>
 WHERE @@ROWCOUNT > 0 AND keyMember0 = keyValue0 AND .. keyMemberI =  keyValueI | scope_identity()  .. AND  keyMemberN = keyValueN]
```

Необходимость во втором шаблоне возникает, если оператор INSERT задает вставку строки, для которой первичный ключ создается хранилищем, но не относится к целочисленному типу, поэтому его нельзя использовать с функцией scope_identity()). Он также используется, если применяются составные ключи, созданные хранилищем.

```sql
-- second insert template
DECLARE @generated_keys TABLE [(keyMember0, … keyMemberN)

INSERT <target>   [ (setClauseProperty0, .. setClausePropertyN)]
 OUTPUT inserted.KeyMember0, …, inserted.KeyMemberN INTO @generated_keys
 VALUES (setClauseValue0, .. setClauseValueN) |  DEFAULT VALUES

[SELECT <returning_over_t>
 FROM @generated_keys  AS g
JOIN <target> AS t ON g.KeyMember0 = t.KeyMember0 AND … g.KeyMemberN = t.KeyMemberN
 WHERE @@ROWCOUNT > 0
```

Далее приведен пример использования модели, которая прилагается к образцу поставщика. В нем создается команда INSERT на основе объекта DbInsertCommandTree.

Следующий код производит вставку объекта Category.

```csharp
using (NorthwindEntities northwindContext = new NorthwindEntities()) {
   Category c = new Category();
   c.CategoryName = "Test Category";
   c.Description = "A new category for testing";
   northwindContext.AddObject("Categories", c);
   northwindContext.SaveChanges();
}
```

Этот код формирует следующее дерево команд, передаваемое поставщику.

```
DbInsertCommandTree
|_Parameters
|_Target : 'target'
| |_Scan : dbo.Categories
|_SetClauses
| |_DbSetClause
| | |_Property
| | | |_Var(target).CategoryName
| | |_Value
| |   |_'Test Category'
| |_DbSetClause
| | |_Property
| | | |_Var(target).Description
| | |_Value
| |   |_'A new category for testing'
| |_DbSetClause
|   |_Property
|   | |_Var(target).Picture
|   |_Value
|     |_null
|_Returning
  |_NewInstance : Record['CategoryID'=Edm.Int32]
    |_Column : 'CategoryID'
      |_Var(target).CategoryID
```

Далее приведен пример использования модели, которая прилагается к образцу поставщика.

```sql
insert [dbo].[Categories]([CategoryName], [Description], [Picture])
values (@p0, @p1, null)
select [CategoryID]
from [dbo].[Categories]
where @@ROWCOUNT > 0 and [CategoryID] = scope_identity()
```

## <a name="generating-an-update-sql-command"></a>Создание команды UPDATE языка SQL

Для данного объекта DbUpdateCommandTree созданная команда UPDATE основана на следующем шаблоне:

```sql
-- UPDATE Template
UPDATE <target>
SET setClauseProperty0 = setClauseValue0, .. setClausePropertyN = setClauseValueN  | @i = 0
WHERE <predicate>

[SELECT <returning>
 FROM <target>
 WHERE @@ROWCOUNT > 0 AND keyMember0 = keyValue0 AND .. keyMemberI =  keyValueI | scope_identity()  .. AND  keyMemberN = keyValueN]
```

Предложение set имеет фиктивное предложение set («@i = 0") только в том случае, если указаны никаких предложений set. Это должно гарантировать повторное вычисление всех вычисленных хранилищем столбцов.

Только если свойство Returning не равно null, создается инструкция SELECT для возврата свойств, указанных в свойстве Returning.

В следующем примере используется модель, которая включена в образец поставщика для создания команды UPDATE.

Следующий пользовательский код обновляет Category.

```csharp
using (NorthwindEntities northwindContext = new NorthwindEntities()) {
   Category c = northwindContext.Categories.Where(i => i.CategoryName == "Test Category").First();
   c.CategoryName = "New test name";
   northwindContext.SaveChanges();
}
```

Этот пользовательский код формирует следующее дерево команд, которое передается поставщику.

```
DbUpdateCommandTree
|_Parameters
|_Target : 'target'
| |_Scan : dbo.Categories
|_SetClauses
| |_DbSetClause
|   |_Property
|   | |_Var(target).CategoryName
|   |_Value
|     |_'New test name'
|_Predicate
| |_
|   |_Var(target).CategoryID
|   |_=
|   |_10
|_Returning
```

Образец поставщика формирует следующую команду хранилища:

```sql
update [dbo].[Categories]
set [CategoryName] = @p0
where ([CategoryID] = @p1)
```

### <a name="generating-a-delete-sql-command"></a>Создание команды DELETE языка SQL

Для данного объекта DbDeleteCommandTree команда DELETE создается на основе следующего шаблона.

```sql
-- DELETE Template
DELETE <target>
WHERE <predicate>
```

В следующем примере используется модель, которая включена в образец поставщика для создания команды DELETE.

Следующий пользовательский код удаляет Category.

```csharp
using (NorthwindEntities northwindContext = new NorthwindEntities()) {
   Category c = northwindContext.Categories.Where(i => i.CategoryName == "New test name").First();
   northwindContext.DeleteObject(c);
   northwindContext.SaveChanges();
}
```

Этот пользовательский код формирует следующее дерево команд, которое передается поставщику.

```
DbDeleteCommandTree
|_Parameters
|_Target : 'target'
| |_Scan : dbo.Categories
|_Predicate
  |_
    |_Var(target).CategoryID
    |_=
    |_10
```

Следующая команда хранилища сформирована образцом поставщика.

```sql
delete [dbo].[Categories]
where ([CategoryID] = @p0)
```

## <a name="see-also"></a>См. также

- [Создание поставщика данных Entity Framework](../../../../../docs/framework/data/adonet/ef/writing-an-ef-data-provider.md)
