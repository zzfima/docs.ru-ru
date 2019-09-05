---
title: Создание кода SQL для изменения данных
ms.date: 03/30/2017
ms.assetid: 2188a39d-46ed-4a8b-906a-c9f15e6fefd1
ms.openlocfilehash: ab0c18473e73b2d6fe9eb45c43e9b47947a55d99
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248571"
---
# <a name="modification-sql-generation"></a><span data-ttu-id="02c55-102">Создание кода SQL для изменения данных</span><span class="sxs-lookup"><span data-stu-id="02c55-102">Modification SQL Generation</span></span>

<span data-ttu-id="02c55-103">В этом разделе приведено описание разработки модуля создания кода SQL для изменения данных для конкретного поставщика (базы данных, совместимой с SQL:1999).</span><span class="sxs-lookup"><span data-stu-id="02c55-103">This section discusses how to develop a modification SQL generation module for your (SQL:1999-compliant database) provider.</span></span> <span data-ttu-id="02c55-104">Этот модуль обеспечивает преобразование дерева команд изменения в соответствующие инструкции INSERT, UPDATE или DELETE языка SQL.</span><span class="sxs-lookup"><span data-stu-id="02c55-104">This module is responsible for translating a modification command tree into the appropriate SQL INSERT, UPDATE or DELETE statements.</span></span>

<span data-ttu-id="02c55-105">Дополнительные сведения о создании SQL для инструкций SELECT см. в разделе [Создание SQL](sql-generation.md).</span><span class="sxs-lookup"><span data-stu-id="02c55-105">For information about SQL generation for select statements, see [SQL Generation](sql-generation.md).</span></span>

## <a name="overview-of-modification-command-trees"></a><span data-ttu-id="02c55-106">Общие сведения о деревьях команд изменения</span><span class="sxs-lookup"><span data-stu-id="02c55-106">Overview of Modification Command Trees</span></span>

<span data-ttu-id="02c55-107">Модуль создания кода SQL для изменения данных формирует зависящие от базы данных инструкции языка SQL для изменения на основе полученных входных данных DbModificationCommandTree.</span><span class="sxs-lookup"><span data-stu-id="02c55-107">The modification SQL generation module generates database-specific modification SQL statements based on a given input DbModificationCommandTree.</span></span>

<span data-ttu-id="02c55-108">DbModificationCommandTree - это представление объектной модели операции DML (операции INSERT, UPDATE или DELETE), унаследованной от DbCommandTree.</span><span class="sxs-lookup"><span data-stu-id="02c55-108">A DbModificationCommandTree is an object model representation of a modification DML operation (an insert, an update, or a delete operation), inheriting from DbCommandTree.</span></span> <span data-ttu-id="02c55-109">Существуют три реализации DbModificationCommandTree:</span><span class="sxs-lookup"><span data-stu-id="02c55-109">There are three implementations of DbModificationCommandTree:</span></span>

- <span data-ttu-id="02c55-110">DbInsertCommandTree</span><span class="sxs-lookup"><span data-stu-id="02c55-110">DbInsertCommandTree</span></span>

- <span data-ttu-id="02c55-111">DbUpdateCommandTree</span><span class="sxs-lookup"><span data-stu-id="02c55-111">DbUpdateCommandTree</span></span>

- <span data-ttu-id="02c55-112">DbDeleteCommandTree</span><span class="sxs-lookup"><span data-stu-id="02c55-112">DbDeleteCommandTree</span></span>

<span data-ttu-id="02c55-113">DbModificationCommandTree и его реализации, создаваемые функцией [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] , всегда представляют операцию с одной строкой.</span><span class="sxs-lookup"><span data-stu-id="02c55-113">DbModificationCommandTree and its implementations that are produced by the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] always represent a single row operation.</span></span> <span data-ttu-id="02c55-114">В настоящем разделе рассматриваются указанные типы и их ограничения в .NET Framework версии 3.5.</span><span class="sxs-lookup"><span data-stu-id="02c55-114">This section describes these types with their constraints in the .NET Framework version 3.5.</span></span>

<span data-ttu-id="02c55-115">![Схема](./media/558ba7b3-dd19-48d0-b91e-30a76415bf5f.gif "558ba7b3-dd19-48d0-b91e-30a76415bf5f")</span><span class="sxs-lookup"><span data-stu-id="02c55-115">![Diagram](./media/558ba7b3-dd19-48d0-b91e-30a76415bf5f.gif "558ba7b3-dd19-48d0-b91e-30a76415bf5f")</span></span>

<span data-ttu-id="02c55-116">DbModificationCommandTree имеет свойство Target, которое представляет набор целей для операции изменения.</span><span class="sxs-lookup"><span data-stu-id="02c55-116">DbModificationCommandTree has a Target property that represents the target set for the modification operation.</span></span> <span data-ttu-id="02c55-117">Свойство Expression свойства Target, которое определяет входной набор, всегда имеет тип DbScanExpression.</span><span class="sxs-lookup"><span data-stu-id="02c55-117">The Target’s Expression property, which defines the input set is always DbScanExpression.</span></span>  <span data-ttu-id="02c55-118">Дбсканекспрессион может представлять таблицу или представление либо набор данных, определенных с помощью запроса, если свойство метаданных ", определяющего запрос" целевого объекта, не имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="02c55-118">A DbScanExpression can either represent a table or a view, or a set of data defined with a query if the metadata property "Defining Query" of its Target is non-null.</span></span>

<span data-ttu-id="02c55-119">Объект DbScanExpression, который представляет запрос, может достичь поставщика только как цель изменения, если набор был определен с помощью определяющего запроса в модели, но для соответствующей операции изменения не была предоставлена какая-либо функция.</span><span class="sxs-lookup"><span data-stu-id="02c55-119">A DbScanExpression that represents a query could only reach a provider as a target of modification if the set was defined by using a defining query in the model but no function was provided for the corresponding modification operation.</span></span> <span data-ttu-id="02c55-120">Поставщики могут оказаться неспособными поддерживать такой сценарий (например, поставщик SqlClient его не поддерживает).</span><span class="sxs-lookup"><span data-stu-id="02c55-120">Providers may not be able to support such a scenario (SqlClient, for example, does not).</span></span>

<span data-ttu-id="02c55-121">DbInsertCommandTree представляет операцию вставки из одной строки, выраженную в виде дерева команд.</span><span class="sxs-lookup"><span data-stu-id="02c55-121">DbInsertCommandTree represents a single row insert operation expressed as a command tree.</span></span>

```csharp
public sealed class DbInsertCommandTree : DbModificationCommandTree {
   public IList<DbModificationClause> SetClauses { get }
   public DbExpression Returning { get }
}
```

<span data-ttu-id="02c55-122">DbUpdateCommandTree представляет операцию обновления из одной строки, выраженную в виде дерева команд.</span><span class="sxs-lookup"><span data-stu-id="02c55-122">DbUpdateCommandTree represents a single-row update operation expressed as a command tree.</span></span>

<span data-ttu-id="02c55-123">DbDeleteCommandTree представляет операцию удаления из одной строки, выраженную в виде дерева команд.</span><span class="sxs-lookup"><span data-stu-id="02c55-123">DbDeleteCommandTree represents a single row delete operation expressed as a command tree.</span></span>

### <a name="restrictions-on-modification-command-tree-properties"></a><span data-ttu-id="02c55-124">Ограничения свойств дерева команд изменения</span><span class="sxs-lookup"><span data-stu-id="02c55-124">Restrictions on Modification Command Tree Properties</span></span>

<span data-ttu-id="02c55-125">Следующие сведения и ограничения относятся к свойствам дерева команд изменения.</span><span class="sxs-lookup"><span data-stu-id="02c55-125">The following information and restrictions apply to the modification command tree properties.</span></span>

#### <a name="returning-in-dbinsertcommandtree-and-dbupdatecommandtree"></a><span data-ttu-id="02c55-126">Свойство Returning объектов DbInsertCommandTree и DbUpdateCommandTree</span><span class="sxs-lookup"><span data-stu-id="02c55-126">Returning in DbInsertCommandTree and DbUpdateCommandTree</span></span>

<span data-ttu-id="02c55-127">Значение свойства Returning, отличное от null, указывает, что команда возвращает модуль чтения.</span><span class="sxs-lookup"><span data-stu-id="02c55-127">When non-null, Returning indicates that the command returns a reader.</span></span> <span data-ttu-id="02c55-128">В противном случае команда возвращает скалярное значение, указывающее число затронутых строк (вставленных или обновленных).</span><span class="sxs-lookup"><span data-stu-id="02c55-128">Otherwise, the command should return a scalar value indicating the number of rows affected (inserted or updated).</span></span>

<span data-ttu-id="02c55-129">Значение Returning задает проекцию результатов, которые должны быть возвращены с учетом вставленных или обновленных строк.</span><span class="sxs-lookup"><span data-stu-id="02c55-129">The Returning value specifies a projection of results to be returned based on the inserted or the updated row.</span></span> <span data-ttu-id="02c55-130">Это свойство может иметь только тип DbNewInstanceExpression, представляющий строку, каждый из аргументов которого является выражением DbPropertyExpression на основе выражения DbVariableReferenceExpression, представляющего ссылку на свойство Target соответствующего объекта DbModificationCommandTree.</span><span class="sxs-lookup"><span data-stu-id="02c55-130">It can only be of type DbNewInstanceExpression representing a row, with each of its arguments being a DbPropertyExpression over a DbVariableReferenceExpression representing a reference to the Target of the corresponding DbModificationCommandTree.</span></span> <span data-ttu-id="02c55-131">Свойства, представленные выражениями DbPropertyExpression, которые используются в свойстве Returning, всегда являются значениями, созданными или вычисленными хранилищем.</span><span class="sxs-lookup"><span data-stu-id="02c55-131">The properties represented by the DbPropertyExpressions used in the property Returning are always store generated or computed values.</span></span> <span data-ttu-id="02c55-132">В объекте DbInsertCommandTree свойство Returning не равно null, если по крайней мере одно свойство таблицы, в которую вставляется строка, указано как созданное или вычисленное хранилищем (что обозначается в языке SSDL с помощью StoreGeneratedPattern.Identity или StoreGeneratedPattern.Computed).</span><span class="sxs-lookup"><span data-stu-id="02c55-132">In DbInsertCommandTree, Returning is not null when at least one property of the table in which the row is being inserted is specified as store generated or computed (marked as StoreGeneratedPattern.Identity or StoreGeneratedPattern.Computed in the ssdl).</span></span> <span data-ttu-id="02c55-133">В объектах DbUpdateCommandTree свойство Returning не равно null, если по крайней мере одно свойство таблицы, в которой обновляется строка, указано как вычисленное хранилищем (что в языке SSDL обозначается с помощью StoreGeneratedPattern.Computed).</span><span class="sxs-lookup"><span data-stu-id="02c55-133">In DbUpdateCommandTrees, Returning is not null when at least one property of the table in which the row is being updated is specified as store computed (marked as StoreGeneratedPattern.Computed in the ssdl).</span></span>

#### <a name="setclauses-in-dbinsertcommandtree-and-dbupdatecommandtree"></a><span data-ttu-id="02c55-134">Свойство SetClauses в объектах DbInsertCommandTree и DbUpdateCommandTree</span><span class="sxs-lookup"><span data-stu-id="02c55-134">SetClauses in DbInsertCommandTree and DbUpdateCommandTree</span></span>

<span data-ttu-id="02c55-135">Свойство SetClauses задает список предложений SET операций INSERT или UPDATE, которые определяют операцию INSERT или UPDATE.</span><span class="sxs-lookup"><span data-stu-id="02c55-135">SetClauses specifies the list of insert or update set clauses that define the insert or update operation.</span></span>

```
The elements of the list are specified as type DbModificationClause, which specifies a single clause in an insert or update modification operation. DbSetClause inherits from DbModificationClause and specifies the clause in a modification operation that sets the value of a property. Beginning in version 3.5 of the .NET Framework, all elements in SetClauses are of type SetClause.
```

<span data-ttu-id="02c55-136">Property указывает свойство, которое должно быть обновлено.</span><span class="sxs-lookup"><span data-stu-id="02c55-136">Property specifies the property that should be updated.</span></span> <span data-ttu-id="02c55-137">Это всегда выражение DbPropertyExpression на основе DbVariableReferenceExpression, которое представляет ссылку на свойство Target соответствующего объекта DbModificationCommandTree.</span><span class="sxs-lookup"><span data-stu-id="02c55-137">It is always a DbPropertyExpression over a DbVariableReferenceExpression, which represents a reference to the Target of the corresponding DbModificationCommandTree.</span></span>

<span data-ttu-id="02c55-138">Выражение Value задает новое значение, которое применяется для обновления свойства.</span><span class="sxs-lookup"><span data-stu-id="02c55-138">Value specifies the new value with which to update the property.</span></span> <span data-ttu-id="02c55-139">Оно относится к типу DbConstantExpression или DbNullExpression.</span><span class="sxs-lookup"><span data-stu-id="02c55-139">It is either of type DbConstantExpression or DbNullExpression.</span></span>

#### <a name="predicate-in-dbupdatecommandtree-and-dbdeletecommandtree"></a><span data-ttu-id="02c55-140">Свойство Predicate в объектах DbUpdateCommandTree и DbDeleteCommandTree</span><span class="sxs-lookup"><span data-stu-id="02c55-140">Predicate in DbUpdateCommandTree and DbDeleteCommandTree</span></span>

<span data-ttu-id="02c55-141">Свойство Predicate указывает предикат, используемый для определения того, какие элементы целевой коллекции должны быть обновлены или удалены.</span><span class="sxs-lookup"><span data-stu-id="02c55-141">Predicate specifies the predicate used to determine which members of the target collection should be updated or deleted.</span></span> <span data-ttu-id="02c55-142">Это дерево выражения, построенное исходя из следующего подмножества DbExpressions.</span><span class="sxs-lookup"><span data-stu-id="02c55-142">It is an expression tree built of the following subset of DbExpressions:</span></span>

- <span data-ttu-id="02c55-143">DbComparisonExpression типа Equals, где правый дочерний элемент является Дбпропертекспрессион, как показано ниже, а левый дочерний элемент DbConstantExpression.</span><span class="sxs-lookup"><span data-stu-id="02c55-143">DbComparisonExpression of kind Equals, with the right child being a DbPropertyExpression as restricted below and the left child a DbConstantExpression.</span></span>

- <span data-ttu-id="02c55-144">DbConstantExpression</span><span class="sxs-lookup"><span data-stu-id="02c55-144">DbConstantExpression</span></span>

- <span data-ttu-id="02c55-145">DbIsNullExpression над Дбпропертекспрессион, как показано ниже</span><span class="sxs-lookup"><span data-stu-id="02c55-145">DbIsNullExpression over a DbPropertyExpression as restricted below</span></span>

- <span data-ttu-id="02c55-146">Свойство DbPropertyExpression на основе выражения DbVariableReferenceExpression, представляющего ссылку на свойство Target соответствующего объекта DbModificationCommandTree.</span><span class="sxs-lookup"><span data-stu-id="02c55-146">DbPropertyExpression over a DbVariableReferenceExpression representing a reference to the Target of the corresponding DbModificationCommandTree.</span></span>

- <span data-ttu-id="02c55-147">DbAndExpression</span><span class="sxs-lookup"><span data-stu-id="02c55-147">DbAndExpression</span></span>

- <span data-ttu-id="02c55-148">DbNotExpression</span><span class="sxs-lookup"><span data-stu-id="02c55-148">DbNotExpression</span></span>

- <span data-ttu-id="02c55-149">DbOrExpression</span><span class="sxs-lookup"><span data-stu-id="02c55-149">DbOrExpression</span></span>

## <a name="modification-sql-generation-in-the-sample-provider"></a><span data-ttu-id="02c55-150">Создание кода SQL для изменения данных в образце поставщика</span><span class="sxs-lookup"><span data-stu-id="02c55-150">Modification SQL Generation in the Sample Provider</span></span>

<span data-ttu-id="02c55-151">В [Entity Framework примере поставщика](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) демонстрируются компоненты поставщиков данных ADO.NET, которые поддерживают [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02c55-151">The [Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) demonstrates the components of ADO.NET Data Providers that support the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="02c55-152">Он предназначен для базы данных SQL Server 2005 и реализован как оболочка на основе поставщика данных System.Data.SqlClient ADO.NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="02c55-152">It targets a SQL Server 2005 database and is implemented as a wrapper on top of System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>

<span data-ttu-id="02c55-153">Модуль создания кода SQL для изменения данных из образца поставщика (который находится в файле SQL Generation\DmlSqlGenerator.cs) принимает входные данные DbModificationCommandTree и вырабатывает одну инструкцию SQL изменения, за которой может следовать инструкция SELECT, обеспечивающая возврат модуля чтения, если это указано в DbModificationCommandTree.</span><span class="sxs-lookup"><span data-stu-id="02c55-153">The modification SQL generation module of the sample provider (located in the file SQL Generation\DmlSqlGenerator.cs) takes an input DbModificationCommandTree and produces a single modification SQL statement possibly followed by a select statement to return a reader if specified by the DbModificationCommandTree.</span></span> <span data-ttu-id="02c55-154">Следует отметить, что форма созданных команд зависит от целевой базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="02c55-154">Note that the shape of the commands generated is affected by the target SQL Server database.</span></span>

### <a name="helper-classes-expressiontranslator"></a><span data-ttu-id="02c55-155">Вспомогательные классы: експрессионтранслатор</span><span class="sxs-lookup"><span data-stu-id="02c55-155">Helper Classes: ExpressionTranslator</span></span>

<span data-ttu-id="02c55-156">Класс ExpressionTranslator служит в качестве общего упрощенного преобразователя для всех свойств дерева команд изменения типа DbExpression.</span><span class="sxs-lookup"><span data-stu-id="02c55-156">ExpressionTranslator serves as a common lightweight translator for all modification command tree properties of type DbExpression.</span></span> <span data-ttu-id="02c55-157">Он поддерживает преобразование только типов выражений, которыми ограничиваются свойства дерева команд изменения, и создается с учетом конкретных ограничений.</span><span class="sxs-lookup"><span data-stu-id="02c55-157">It supports translation of only the expression types to which the properties of the modification command tree are constrained and is built with the particular constraints in mind.</span></span>

<span data-ttu-id="02c55-158">Ниже приведены сведения, касающиеся посещения конкретных типов выражений (узлы с тривиальными преобразованиями опущены).</span><span class="sxs-lookup"><span data-stu-id="02c55-158">The following information discusses visiting specific expression types (nodes with trivial translations are omitted).</span></span>

### <a name="dbcomparisonexpression"></a><span data-ttu-id="02c55-159">DbComparisonExpression</span><span class="sxs-lookup"><span data-stu-id="02c55-159">DbComparisonExpression</span></span>

<span data-ttu-id="02c55-160">Если объект ExpressionTranslator создается со значением preserveMemberValues = true, а находящаяся справа константа представляет собой DbConstantExpression (а не DbNullExpression), он связывает левый операнд (DbPropertyExpressions) с этим выражением DbConstantExpression.</span><span class="sxs-lookup"><span data-stu-id="02c55-160">When the ExpressionTranslator is constructed with preserveMemberValues = true, and when the constant to the right is a DbConstantExpression (instead of DbNullExpression), it associates the left operand (a DbPropertyExpressions) with that DbConstantExpression.</span></span> <span data-ttu-id="02c55-161">Такой вариант используется, если возвращаемая инструкция SELECT должна быть создана для обозначения затронутой строки.</span><span class="sxs-lookup"><span data-stu-id="02c55-161">That is used if a return Select statement needs to be generated to identify the affected row.</span></span>

### <a name="dbconstantexpression"></a><span data-ttu-id="02c55-162">DbConstantExpression</span><span class="sxs-lookup"><span data-stu-id="02c55-162">DbConstantExpression</span></span>

<span data-ttu-id="02c55-163">Для каждой посещенной константы создается параметр.</span><span class="sxs-lookup"><span data-stu-id="02c55-163">For each visited constant a parameter is created.</span></span>

### <a name="dbpropertyexpression"></a><span data-ttu-id="02c55-164">DbPropertyExpression</span><span class="sxs-lookup"><span data-stu-id="02c55-164">DbPropertyExpression</span></span>

<span data-ttu-id="02c55-165">С учетом того, что экземпляр выражения DbPropertyExpression всегда представляет входную таблицу, при условии, что в ходе создания не был создан псевдоним (это происходит только при обновлении, когда используется табличная переменная), для входных данных не должен быть указан какой-либо псевдоним. В преобразовании по умолчанию применяется имя свойства.</span><span class="sxs-lookup"><span data-stu-id="02c55-165">Given that the Instance of the DbPropertyExpression always represents the input table, unless the generation has created an alias (which only happens in update scenarios when a table variable is used), no alias needs to be specified for the input; the translation defaults to the property name.</span></span>

## <a name="generating-an-insert-sql-command"></a><span data-ttu-id="02c55-166">Создание команд INSERT языка SQL</span><span class="sxs-lookup"><span data-stu-id="02c55-166">Generating an Insert SQL Command</span></span>

<span data-ttu-id="02c55-167">Для каждого конкретного объекта DbInsertCommandTree из образца поставщика созданная команда INSERT соответствует одному из двух приведенных далее шаблонов INSERT.</span><span class="sxs-lookup"><span data-stu-id="02c55-167">For a given DbInsertCommandTree in the sample provider, the generated insert command follows one of the two insert templates below.</span></span>

<span data-ttu-id="02c55-168">Первый шаблон имеет команду для выполнения оператора INSERT с учетом значений из списка SetClauses и инструкции SELECT для возврата свойств, указанных в свойстве Returning для вставленной строки, если свойство Returning не имело значение null.</span><span class="sxs-lookup"><span data-stu-id="02c55-168">The first template has a command to perform the insert given the values in the list of SetClauses, and a SELECT statement to return the properties specified in the Returning property for the inserted row if the Returning property was not null.</span></span> <span data-ttu-id="02c55-169">Элемент Predicate "\@ @ROWCOUNT > 0" имеет значение true, если строка была вставлена.</span><span class="sxs-lookup"><span data-stu-id="02c55-169">The predicate element "\@@ROWCOUNT > 0" is true if a row was inserted.</span></span> <span data-ttu-id="02c55-170">Элемент Predicate "Кэймембери = Кэйвалуеи &#124; SCOPE_IDENTITY ()" принимает фигуру "кэймембери = SCOPE_IDENTITY ()" только в том случае, если кэймембери является ключом, созданным для хранения, поскольку функция SCOPE_IDENTITY () возвращает последнее значение идентификатора, вставленное в удостоверение ( созданный хранилищем).</span><span class="sxs-lookup"><span data-stu-id="02c55-170">The predicate element "keyMemberI =  keyValueI &#124; scope_identity()" takes the shape  "keyMemberI =  scope_identity()" only if keyMemberI is a store-generated key, because scope_identity() returns the last identity value inserted into an identity (store-generated) column.</span></span>

```sql
-- first insert Template
INSERT <target>   [ (setClauseProperty0, .. setClausePropertyN)]
VALUES (setClauseValue0, .. setClauseValueN) |  DEFAULT VALUES

[SELECT <returning>
 FROM <target>
 WHERE @@ROWCOUNT > 0 AND keyMember0 = keyValue0 AND .. keyMemberI =  keyValueI | scope_identity()  .. AND  keyMemberN = keyValueN]
```

<span data-ttu-id="02c55-171">Необходимость во втором шаблоне возникает, если оператор INSERT задает вставку строки, для которой первичный ключ создается хранилищем, но не относится к целочисленному типу, поэтому его нельзя использовать с функцией scope_identity()).</span><span class="sxs-lookup"><span data-stu-id="02c55-171">The second template is needed if the insert specifies inserting a row where the primary key is store-generated but is not an integer type and therefore can't be used with scope_identity()).</span></span> <span data-ttu-id="02c55-172">Он также используется, если применяются составные ключи, созданные хранилищем.</span><span class="sxs-lookup"><span data-stu-id="02c55-172">It is also used if there is a compound store-generated key.</span></span>

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

<span data-ttu-id="02c55-173">Далее приведен пример использования модели, которая прилагается к образцу поставщика.</span><span class="sxs-lookup"><span data-stu-id="02c55-173">The following is an example that uses the model that is included with the sample provider.</span></span> <span data-ttu-id="02c55-174">В нем создается команда INSERT на основе объекта DbInsertCommandTree.</span><span class="sxs-lookup"><span data-stu-id="02c55-174">It generates an insert command from a DbInsertCommandTree.</span></span>

<span data-ttu-id="02c55-175">Следующий код производит вставку объекта Category.</span><span class="sxs-lookup"><span data-stu-id="02c55-175">The following code inserts a Category:</span></span>

```csharp
using (NorthwindEntities northwindContext = new NorthwindEntities()) {
   Category c = new Category();
   c.CategoryName = "Test Category";
   c.Description = "A new category for testing";
   northwindContext.AddObject("Categories", c);
   northwindContext.SaveChanges();
}
```

<span data-ttu-id="02c55-176">Этот код формирует следующее дерево команд, передаваемое поставщику.</span><span class="sxs-lookup"><span data-stu-id="02c55-176">This code produces the following command tree, which is passed to the provider:</span></span>

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

<span data-ttu-id="02c55-177">Далее приведен пример использования модели, которая прилагается к образцу поставщика.</span><span class="sxs-lookup"><span data-stu-id="02c55-177">The store command that the sample provider produces is the following SQL statement:</span></span>

```sql
insert [dbo].[Categories]([CategoryName], [Description], [Picture])
values (@p0, @p1, null)
select [CategoryID]
from [dbo].[Categories]
where @@ROWCOUNT > 0 and [CategoryID] = scope_identity()
```

## <a name="generating-an-update-sql-command"></a><span data-ttu-id="02c55-178">Создание команды UPDATE языка SQL</span><span class="sxs-lookup"><span data-stu-id="02c55-178">Generating an Update SQL Command</span></span>

<span data-ttu-id="02c55-179">Для данного объекта DbUpdateCommandTree созданная команда UPDATE основана на следующем шаблоне:</span><span class="sxs-lookup"><span data-stu-id="02c55-179">For a given DbUpdateCommandTree, the generated update command is based on the following template:</span></span>

```sql
-- UPDATE Template
UPDATE <target>
SET setClauseProperty0 = setClauseValue0, .. setClausePropertyN = setClauseValueN  | @i = 0
WHERE <predicate>

[SELECT <returning>
 FROM <target>
 WHERE @@ROWCOUNT > 0 AND keyMember0 = keyValue0 AND .. keyMemberI =  keyValueI | scope_identity()  .. AND  keyMemberN = keyValueN]
```

<span data-ttu-id="02c55-180">Предложение SET имеет поддельное предложение SET ("@i = 0") только в том случае, если не заданы предложения SET.</span><span class="sxs-lookup"><span data-stu-id="02c55-180">The set clause has the fake set clause ("@i = 0") only if no set clauses are specified.</span></span> <span data-ttu-id="02c55-181">Это должно гарантировать повторное вычисление всех вычисленных хранилищем столбцов.</span><span class="sxs-lookup"><span data-stu-id="02c55-181">This is to ensure that any store-computed columns are recomputed.</span></span>

<span data-ttu-id="02c55-182">Только если свойство Returning не равно null, создается инструкция SELECT для возврата свойств, указанных в свойстве Returning.</span><span class="sxs-lookup"><span data-stu-id="02c55-182">Only if the Returning property is not null, a select statement is generated to return the properties specified in the Returning property.</span></span>

<span data-ttu-id="02c55-183">В следующем примере используется модель, которая включена в образец поставщика для создания команды UPDATE.</span><span class="sxs-lookup"><span data-stu-id="02c55-183">The following example uses the model that is included with the sample provider to generate an update command.</span></span>

<span data-ttu-id="02c55-184">Следующий пользовательский код обновляет Category.</span><span class="sxs-lookup"><span data-stu-id="02c55-184">The following user code updates a Category:</span></span>

```csharp
using (NorthwindEntities northwindContext = new NorthwindEntities()) {
   Category c = northwindContext.Categories.Where(i => i.CategoryName == "Test Category").First();
   c.CategoryName = "New test name";
   northwindContext.SaveChanges();
}
```

<span data-ttu-id="02c55-185">Этот пользовательский код формирует следующее дерево команд, которое передается поставщику.</span><span class="sxs-lookup"><span data-stu-id="02c55-185">This user code produces the following command tree, which is passed to the provider:</span></span>

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

<span data-ttu-id="02c55-186">Образец поставщика формирует следующую команду хранилища:</span><span class="sxs-lookup"><span data-stu-id="02c55-186">The sample provider produces the following store command:</span></span>

```sql
update [dbo].[Categories]
set [CategoryName] = @p0
where ([CategoryID] = @p1)
```

### <a name="generating-a-delete-sql-command"></a><span data-ttu-id="02c55-187">Создание команды DELETE языка SQL</span><span class="sxs-lookup"><span data-stu-id="02c55-187">Generating a Delete SQL Command</span></span>

<span data-ttu-id="02c55-188">Для данного объекта DbDeleteCommandTree команда DELETE создается на основе следующего шаблона.</span><span class="sxs-lookup"><span data-stu-id="02c55-188">For a given DbDeleteCommandTree, the generated DELETE command is based on the following template:</span></span>

```sql
-- DELETE Template
DELETE <target>
WHERE <predicate>
```

<span data-ttu-id="02c55-189">В следующем примере используется модель, которая включена в образец поставщика для создания команды DELETE.</span><span class="sxs-lookup"><span data-stu-id="02c55-189">The following example uses the model that is included with the sample provider to generate a delete command.</span></span>

<span data-ttu-id="02c55-190">Следующий пользовательский код удаляет Category.</span><span class="sxs-lookup"><span data-stu-id="02c55-190">The following user code deletes a Category:</span></span>

```csharp
using (NorthwindEntities northwindContext = new NorthwindEntities()) {
   Category c = northwindContext.Categories.Where(i => i.CategoryName == "New test name").First();
   northwindContext.DeleteObject(c);
   northwindContext.SaveChanges();
}
```

<span data-ttu-id="02c55-191">Этот пользовательский код формирует следующее дерево команд, которое передается поставщику.</span><span class="sxs-lookup"><span data-stu-id="02c55-191">This user code produces the following command tree, which is passed to the provider.</span></span>

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

<span data-ttu-id="02c55-192">Следующая команда хранилища сформирована образцом поставщика.</span><span class="sxs-lookup"><span data-stu-id="02c55-192">The following store command is produced by the sample provider:</span></span>

```sql
delete [dbo].[Categories]
where ([CategoryID] = @p0)
```

## <a name="see-also"></a><span data-ttu-id="02c55-193">См. также</span><span class="sxs-lookup"><span data-stu-id="02c55-193">See also</span></span>

- [<span data-ttu-id="02c55-194">Создание поставщика данных Entity Framework</span><span class="sxs-lookup"><span data-stu-id="02c55-194">Writing an Entity Framework Data Provider</span></span>](writing-an-ef-data-provider.md)
