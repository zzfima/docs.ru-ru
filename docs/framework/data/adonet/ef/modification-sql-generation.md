---
title: Создание кода SQL для изменения данных
ms.date: 03/30/2017
ms.assetid: 2188a39d-46ed-4a8b-906a-c9f15e6fefd1
ms.openlocfilehash: b6c1b71effba17d33c035d0f1df386bf56d405b5
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039888"
---
# <a name="modification-sql-generation"></a>Создание кода SQL для изменения данных

В этом разделе приведено описание разработки модуля создания кода SQL для изменения данных для конкретного поставщика (базы данных, совместимой с SQL:1999). Этот модуль обеспечивает преобразование дерева команд изменения в соответствующие инструкции INSERT, UPDATE или DELETE языка SQL.

Дополнительные сведения о создании SQL для инструкций SELECT см. в разделе [Создание SQL](sql-generation.md).

## <a name="overview-of-modification-command-trees"></a>Общие сведения о деревьях команд изменения

Модуль создания кода SQL для изменения данных формирует зависящие от базы данных инструкции языка SQL для изменения на основе полученных входных данных DbModificationCommandTree.

DbModificationCommandTree - это представление объектной модели операции DML (операции INSERT, UPDATE или DELETE), унаследованной от DbCommandTree. Существуют три реализации DbModificationCommandTree:

- DbInsertCommandTree

- DbUpdateCommandTree

- DbDeleteCommandTree

DbModificationCommandTree и его реализации, создаваемые Entity Framework, всегда представляют операцию с одной строкой. В настоящем разделе рассматриваются указанные типы и их ограничения в .NET Framework версии 3.5.

![Схема](./media/558ba7b3-dd19-48d0-b91e-30a76415bf5f.gif "558ba7b3-dd19-48d0-b91e-30a76415bf5f")

DbModificationCommandTree имеет свойство Target, которое представляет набор целей для операции изменения. Свойство Expression свойства Target, которое определяет входной набор, всегда имеет тип DbScanExpression.  Дбсканекспрессион может представлять таблицу или представление либо набор данных, определенных с помощью запроса, если свойство метаданных ", определяющего запрос" целевого объекта, не имеет значение null.

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

Элементы списка задаются как тип Дбмодификатионклаусе, который задает одно предложение в операции вставки или обновления. Дбсетклаусе наследует от Дбмодификатионклаусе и указывает предложение в операции изменения, которое задает значение свойства. Начиная с версии 3,5 .NET Framework все элементы в Сетклаусес имеют тип Сетклаусе.

Property указывает свойство, которое должно быть обновлено. Это всегда выражение DbPropertyExpression на основе DbVariableReferenceExpression, которое представляет ссылку на свойство Target соответствующего объекта DbModificationCommandTree.

Выражение Value задает новое значение, которое применяется для обновления свойства. Оно относится к типу DbConstantExpression или DbNullExpression.

#### <a name="predicate-in-dbupdatecommandtree-and-dbdeletecommandtree"></a>Свойство Predicate в объектах DbUpdateCommandTree и DbDeleteCommandTree

Свойство Predicate указывает предикат, используемый для определения того, какие элементы целевой коллекции должны быть обновлены или удалены. Это дерево выражения, построенное исходя из следующего подмножества DbExpressions.

- DbComparisonExpression типа Equals, где правый дочерний элемент является Дбпропертекспрессион, как показано ниже, а левый дочерний элемент DbConstantExpression.

- DbConstantExpression

- DbIsNullExpression над Дбпропертекспрессион, как показано ниже

- Свойство DbPropertyExpression на основе выражения DbVariableReferenceExpression, представляющего ссылку на свойство Target соответствующего объекта DbModificationCommandTree.

- DbAndExpression

- DbNotExpression

- DbOrExpression

## <a name="modification-sql-generation-in-the-sample-provider"></a>Создание кода SQL для изменения данных в образце поставщика

В [Entity Framework примере поставщика](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) демонстрируются компоненты поставщиков данных ADO.NET, которые поддерживают Entity Framework. Он предназначен для базы данных SQL Server 2005 и реализован как оболочка на основе поставщика данных System.Data.SqlClient ADO.NET 2.0.

Модуль создания кода SQL для изменения данных из образца поставщика (который находится в файле SQL Generation\DmlSqlGenerator.cs) принимает входные данные DbModificationCommandTree и вырабатывает одну инструкцию SQL изменения, за которой может следовать инструкция SELECT, обеспечивающая возврат модуля чтения, если это указано в DbModificationCommandTree. Следует отметить, что форма созданных команд зависит от целевой базы данных SQL Server.

### <a name="helper-classes-expressiontranslator"></a>Вспомогательные классы: ExpressionTranslator

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

Первый шаблон имеет команду для выполнения оператора INSERT с учетом значений из списка SetClauses и инструкции SELECT для возврата свойств, указанных в свойстве Returning для вставленной строки, если свойство Returning не имело значение null. Элемент Predicate "\@@ROWCOUNT > 0" имеет значение true, если строка была вставлена. Элемент Predicate "Кэймембери = Кэйвалуеи &#124; SCOPE_IDENTITY ()" принимает фигуру "кэймембери = SCOPE_IDENTITY ()" только в том случае, если кэймембери является ключом, созданным для хранения, поскольку функция SCOPE_IDENTITY () возвращает последнее значение идентификатора, вставленное в удостоверение ( созданный хранилищем).

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

```output
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

Предложение SET имеет фиктивное предложение SET ("@i = 0") только в том случае, если не заданы предложения SET. Это должно гарантировать повторное вычисление всех вычисленных хранилищем столбцов.

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

```output
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

```output
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

- [Создание поставщика данных Entity Framework](writing-an-ef-data-provider.md)
