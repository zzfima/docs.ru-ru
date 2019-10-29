---
title: Архитектура и разработка
ms.date: 03/30/2017
ms.assetid: bd738d39-00e2-4bab-b387-90aac1a014bd
ms.openlocfilehash: 35fbc39db23a2b08ab926e122d2f1eb1806a369b
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040026"
---
# <a name="architecture-and-design"></a><span data-ttu-id="186fd-102">Архитектура и разработка</span><span class="sxs-lookup"><span data-stu-id="186fd-102">Architecture and Design</span></span>

<span data-ttu-id="186fd-103">Модуль создания SQL в [примере поставщика](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) реализуется как посетитель в дереве выражения, представляющем дерево команд.</span><span class="sxs-lookup"><span data-stu-id="186fd-103">The SQL generation module in the [Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) is implemented as a visitor on the expression tree that represents the command tree.</span></span> <span data-ttu-id="186fd-104">Создание кода выполняется за один проход по дереву выражения.</span><span class="sxs-lookup"><span data-stu-id="186fd-104">The generation is done in a single pass over the expression tree.</span></span>

<span data-ttu-id="186fd-105">Узлы дерева обрабатываются в порядке снизу вверх.</span><span class="sxs-lookup"><span data-stu-id="186fd-105">The nodes of the tree are processed from the bottom up.</span></span> <span data-ttu-id="186fd-106">Сначала создается промежуточная структура: SqlSelectStatement или SqlBuilder, в каждой из которых реализуется интерфейс ISqlFragment.</span><span class="sxs-lookup"><span data-stu-id="186fd-106">First, an intermediate structure is produced: SqlSelectStatement or SqlBuilder, both implementing ISqlFragment.</span></span> <span data-ttu-id="186fd-107">Затем из этой структуры создается строковая инструкция SQL.</span><span class="sxs-lookup"><span data-stu-id="186fd-107">Next, the string SQL statement is produced from that structure.</span></span> <span data-ttu-id="186fd-108">Промежуточная структура создается по двум причинам.</span><span class="sxs-lookup"><span data-stu-id="186fd-108">There are two reasons for the intermediate structure:</span></span>

- <span data-ttu-id="186fd-109">С логической точки зрения инструкция SQL SELECT заполняется не по порядку.</span><span class="sxs-lookup"><span data-stu-id="186fd-109">Logically, a SQL SELECT statement is populated out of order.</span></span> <span data-ttu-id="186fd-110">Узлы, участвующие в предложении FROM, обходятся раньше, чем узлы, участвующие в предложениях WHERE, GROUP BY и ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="186fd-110">The nodes that participate in the FROM clause are visited before the nodes that participate in the WHERE, GROUP BY, and the ORDER BY clause.</span></span>

- <span data-ttu-id="186fd-111">Для переименования псевдонимов необходимо определить все используемые псевдонимы, чтобы избежать конфликтов во время переименования.</span><span class="sxs-lookup"><span data-stu-id="186fd-111">To rename aliases, you must identify all used aliases to avoid collisions during renaming.</span></span> <span data-ttu-id="186fd-112">Чтобы определить варианты переименования в SqlBuilder, используйте объекты Symbol для представления столбцов-кандидатов на переименование.</span><span class="sxs-lookup"><span data-stu-id="186fd-112">To defer the renaming choices in SqlBuilder, use Symbol objects to represent the columns that are candidates for renaming.</span></span>

<span data-ttu-id="186fd-113">![Схема](./media/de1ca705-4f7c-4d2d-ace5-afefc6d3cefa.gif "de1ca705-4f7c-4d2d-ace5-afefc6d3cefa")</span><span class="sxs-lookup"><span data-stu-id="186fd-113">![Diagram](./media/de1ca705-4f7c-4d2d-ace5-afefc6d3cefa.gif "de1ca705-4f7c-4d2d-ace5-afefc6d3cefa")</span></span>

<span data-ttu-id="186fd-114">На первом этапе во время обхода дерева выражения группируются в объекты SqlSelectStatement, а соединения и псевдонимы соединений преобразуются в плоские.</span><span class="sxs-lookup"><span data-stu-id="186fd-114">In the first phase, while visiting the expression tree, expressions are grouped into SqlSelectStatements, joins are flattened, and join aliases are flattened.</span></span> <span data-ttu-id="186fd-115">На этом проходе объекты Symbol представляют столбцы или входные псевдонимы, которые можно переименовать.</span><span class="sxs-lookup"><span data-stu-id="186fd-115">During this pass, Symbol objects represent columns or input aliases that may be renamed.</span></span>

<span data-ttu-id="186fd-116">На втором этапе во время создания фактической строки происходит переименование псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="186fd-116">In the second phase, while producing the actual string, aliases are renamed.</span></span>

## <a name="data-structures"></a><span data-ttu-id="186fd-117">Структуры данных</span><span class="sxs-lookup"><span data-stu-id="186fd-117">Data Structures</span></span>

<span data-ttu-id="186fd-118">В этом разделе обсуждаются типы, используемые в [примере поставщика](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) , который используется для построения инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="186fd-118">This section discusses the types used in the [Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) that you use to build a SQL statement.</span></span>

### <a name="isqlfragment"></a><span data-ttu-id="186fd-119">ISqlFragment</span><span class="sxs-lookup"><span data-stu-id="186fd-119">ISqlFragment</span></span>

<span data-ttu-id="186fd-120">В этом разделе описаны классы, в которых реализован интерфейс ISqlFragment. Он выполняет две функции.</span><span class="sxs-lookup"><span data-stu-id="186fd-120">This section covers the classes that implement the ISqlFragment interface, which serves two purposes:</span></span>

- <span data-ttu-id="186fd-121">Общий тип возвращаемого значения для всех методов посетителя.</span><span class="sxs-lookup"><span data-stu-id="186fd-121">A common return type for all the visitor methods.</span></span>

- <span data-ttu-id="186fd-122">Предоставляет метод для записи окончательной строки SQL.</span><span class="sxs-lookup"><span data-stu-id="186fd-122">Gives a method to write the final SQL string.</span></span>

```csharp
internal interface ISqlFragment {
   void WriteSql(SqlWriter writer, SqlGenerator sqlGenerator);
}
```

#### <a name="sqlbuilder"></a><span data-ttu-id="186fd-123">SqlBuilder</span><span class="sxs-lookup"><span data-stu-id="186fd-123">SqlBuilder</span></span>

<span data-ttu-id="186fd-124">SqlBuilder - это устройство сбора окончательной строки SQL, аналогичное StringBuilder.</span><span class="sxs-lookup"><span data-stu-id="186fd-124">SqlBuilder is a gathering device for the final SQL string, similar to StringBuilder.</span></span> <span data-ttu-id="186fd-125">Оно состоит из строк, которые составляют окончательную строку SQL, вместе с объектами ISqlFragment, которые можно преобразовать в строки.</span><span class="sxs-lookup"><span data-stu-id="186fd-125">It consists of the strings that make up the final SQL, along with ISqlFragments that can be converted into strings.</span></span>

```csharp
internal sealed class SqlBuilder : ISqlFragment {
   public void Append(object s)
   public void AppendLine()
   public bool IsEmpty
}
```

#### <a name="sqlselectstatement"></a><span data-ttu-id="186fd-126">SqlSelectStatement</span><span class="sxs-lookup"><span data-stu-id="186fd-126">SqlSelectStatement</span></span>

<span data-ttu-id="186fd-127">SqlSelectStatement представляет каноническую инструкцию SQL SELECT для фигуры "SELECT...</span><span class="sxs-lookup"><span data-stu-id="186fd-127">SqlSelectStatement represents a canonical SQL SELECT statement of the shape "SELECT …</span></span> <span data-ttu-id="186fd-128">От..</span><span class="sxs-lookup"><span data-stu-id="186fd-128">FROM  ..</span></span> <span data-ttu-id="186fd-129">ГДЕ...</span><span class="sxs-lookup"><span data-stu-id="186fd-129">WHERE …</span></span> <span data-ttu-id="186fd-130">ГРУППИРОВАТЬ ПО...</span><span class="sxs-lookup"><span data-stu-id="186fd-130">GROUP BY …</span></span> <span data-ttu-id="186fd-131">УПОРЯДОЧИТЬ ПО ".</span><span class="sxs-lookup"><span data-stu-id="186fd-131">ORDER BY".</span></span>

<span data-ttu-id="186fd-132">Каждое из предложений SQL представляется объектом StringBuilder.</span><span class="sxs-lookup"><span data-stu-id="186fd-132">Each of the SQL clauses is represented by a StringBuilder.</span></span> <span data-ttu-id="186fd-133">Кроме того, он отслеживает, указано ли ключевое слово Distinct и является ли инструкция самой верхней.</span><span class="sxs-lookup"><span data-stu-id="186fd-133">In addition, it tracks whether Distinct has been specified and whether the statement is topmost.</span></span> <span data-ttu-id="186fd-134">Если это не так, то предложение ORDER BY не указывается, однако оно указывается, если инструкция также содержит предложение TOP.</span><span class="sxs-lookup"><span data-stu-id="186fd-134">If the statement is not topmost, the ORDER BY clause is omitted unless the statement also has a TOP clause.</span></span>

<span data-ttu-id="186fd-135">FromExtents содержит список входных данных для инструкции SELECT.</span><span class="sxs-lookup"><span data-stu-id="186fd-135">FromExtents contains the list of inputs for the SELECT statement.</span></span> <span data-ttu-id="186fd-136">Обычно это только один элемент.</span><span class="sxs-lookup"><span data-stu-id="186fd-136">There is usually just one element in this.</span></span> <span data-ttu-id="186fd-137">Инструкции SELECT для соединений могут временно иметь несколько элементов.</span><span class="sxs-lookup"><span data-stu-id="186fd-137">SELECT statements for joins may temporarily have more than one element.</span></span>

<span data-ttu-id="186fd-138">Если инструкция SELECT создается узлом соединения, то в SqlSelectStatement ведется список всех экстентов, которые были преобразованы в плоские в соединении в AllJoinExtents.</span><span class="sxs-lookup"><span data-stu-id="186fd-138">If the SELECT statement is created by a Join node, SqlSelectStatement maintains a list of all the extents that have been flattened in the join in AllJoinExtents.</span></span> <span data-ttu-id="186fd-139">OuterExtents представляет внешние ссылки SqlSelectStatement и используется для переименования входных псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="186fd-139">OuterExtents represents outer references of the SqlSelectStatement and is used for input alias renaming.</span></span>

```csharp
internal sealed class SqlSelectStatement : ISqlFragment {
   internal bool IsDistinct { get, set };
   internal bool IsTopMost

   internal List<Symbol> AllJoinExtents { get, set };
   internal List<Symbol> FromExtents { get};
   internal Dictionary<Symbol, bool> OuterExtents { get};

   internal TopClause Top { get, set };

   internal SqlBuilder Select {get};
   internal SqlBuilder From
   internal SqlBuilder Where
   internal SqlBuilder GroupBy
   public SqlBuilder OrderBy
}
```

#### <a name="topclause"></a><span data-ttu-id="186fd-140">TopClause</span><span class="sxs-lookup"><span data-stu-id="186fd-140">TopClause</span></span>

<span data-ttu-id="186fd-141">TopClause представляет выражение TOP в SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="186fd-141">TopClause represents the TOP expression in a SqlSelectStatement.</span></span> <span data-ttu-id="186fd-142">Свойство TopCount показывает, сколько нужно выбрать строк TOP.</span><span class="sxs-lookup"><span data-stu-id="186fd-142">The TopCount property indicates how many TOP rows should be selected.</span></span>  <span data-ttu-id="186fd-143">Если Вистиес имеет значение true, Топклаусе построен из Дблимитекспрессион.</span><span class="sxs-lookup"><span data-stu-id="186fd-143">When WithTies is true, the TopClause was built from a DbLimitExpression.</span></span>

```csharp
class TopClause : ISqlFragment {
   internal bool WithTies {get}
   internal ISqlFragment TopCount {get}
   internal TopClause(ISqlFragment topCount, bool withTies)
   internal TopClause(int topCount, bool withTies)
}
```

### <a name="symbols"></a><span data-ttu-id="186fd-144">Символы</span><span class="sxs-lookup"><span data-stu-id="186fd-144">Symbols</span></span>

<span data-ttu-id="186fd-145">Классы, связанные с Symbol, и таблица символов выполняют переименование входных псевдонимов, преобразование псевдонимов соединений в плоские и переименование псевдонимов столбцов.</span><span class="sxs-lookup"><span data-stu-id="186fd-145">The Symbol-related classes and the symbol table perform input alias renaming, join alias flattening, and column alias renaming.</span></span>

<span data-ttu-id="186fd-146">Класс Symbol представляет экстент, вложенную инструкцию SELECT или столбец.</span><span class="sxs-lookup"><span data-stu-id="186fd-146">The Symbol class represents an extent, a nested SELECT statement, or a column.</span></span> <span data-ttu-id="186fd-147">Он используется вместо фактического псевдонима, что позволяет переименовать его после использования, а также передает дополнительные сведения о представляемом артефакте (например, типе).</span><span class="sxs-lookup"><span data-stu-id="186fd-147">It is used instead of an actual alias to allow for renaming after it has been used and it also carries additional information for the artifact it represents (like the type).</span></span>

```csharp
class Symbol : ISqlFragment {
   internal Dictionary<string, Symbol> Columns {get}
   internal bool NeedsRenaming {get, set}
   internal bool IsUnnest {get, set}   //not used

   public string Name{get}
   public string NewName {get,set}
   internal TypeUsage Type {get, set}

   public Symbol(string name, TypeUsage type)
}
```

<span data-ttu-id="186fd-148">В объекте Name хранится исходный псевдоним для представляемого экстента, вложенной инструкции SELECT или столбца.</span><span class="sxs-lookup"><span data-stu-id="186fd-148">Name stores the original alias for the represented extent, nested SELECT statement, or a column.</span></span>

<span data-ttu-id="186fd-149">В объекте NewName хранится псевдоним, который будет использоваться в инструкции SQL SELECT.</span><span class="sxs-lookup"><span data-stu-id="186fd-149">NewName stores the alias that will be used in the SQL SELECT statement.</span></span> <span data-ttu-id="186fd-150">Вначале значение устанавливается равным Name и изменяется только в случае необходимости при создании окончательного строкового запроса.</span><span class="sxs-lookup"><span data-stu-id="186fd-150">It is originally set to Name, and only renamed if needed when generating the final string query.</span></span>

<span data-ttu-id="186fd-151">Объект Type используется только для символов, представляющих экстенты и вложенные инструкции SELECT.</span><span class="sxs-lookup"><span data-stu-id="186fd-151">Type is only useful for symbols representing extents and nested SELECT statements.</span></span>

#### <a name="symbolpair"></a><span data-ttu-id="186fd-152">SymbolPair</span><span class="sxs-lookup"><span data-stu-id="186fd-152">SymbolPair</span></span>

<span data-ttu-id="186fd-153">Класс SymbolPair отвечает за преобразование записей в плоские.</span><span class="sxs-lookup"><span data-stu-id="186fd-153">The SymbolPair class addresses record flattening.</span></span>

<span data-ttu-id="186fd-154">Рассмотрим выражение свойства D(v, "j3.j2.j1.a.x"), где v обозначает VarRef, j1, j2, j3 - соединения, a - экстент, а x - столбец.</span><span class="sxs-lookup"><span data-stu-id="186fd-154">Consider a property expression D(v, "j3.j2.j1.a.x") where v is a VarRef, j1, j2, j3 are joins, a is an extent, and x is a columns.</span></span>

<span data-ttu-id="186fd-155">Это выражение нужно преобразовать в {j'}.{x'}.</span><span class="sxs-lookup"><span data-stu-id="186fd-155">This has to be translated eventually into {j'}.{x'}.</span></span> <span data-ttu-id="186fd-156">Исходное поле представляет самую внешнюю SqlStatement, представляющую выражение соединения (например, j2). Это всегда символ соединения.</span><span class="sxs-lookup"><span data-stu-id="186fd-156">The source field represents the outermost SqlStatement, representing a join expression (say j2); this is always a Join symbol.</span></span> <span data-ttu-id="186fd-157">Поле столбца перемещается от одного символа соединения к другому, пока не останавливается на символе, который не относится к соединению.</span><span class="sxs-lookup"><span data-stu-id="186fd-157">The column field moves from one join symbol to the next until it stops at a non-join symbol.</span></span> <span data-ttu-id="186fd-158">Оно возвращается при обходе DbPropertyExpression, но никогда не добавляется в SqlBuilder.</span><span class="sxs-lookup"><span data-stu-id="186fd-158">This is returned when visiting a DbPropertyExpression but is never added to a SqlBuilder.</span></span>

```csharp
class SymbolPair : ISqlFragment {
   public Symbol Source;
   public Symbol Column;
   public SymbolPair(Symbol source, Symbol column)
}
```

#### <a name="joinsymbol"></a><span data-ttu-id="186fd-159">JoinSymbol</span><span class="sxs-lookup"><span data-stu-id="186fd-159">JoinSymbol</span></span>

<span data-ttu-id="186fd-160">Символ соединения - это объект Symbol, представляющий вложенную инструкцию SELECT с соединением или входом соединения.</span><span class="sxs-lookup"><span data-stu-id="186fd-160">A Join symbol is a Symbol that represents a nested SELECT statement with a join or a join input.</span></span>

```csharp
internal sealed class JoinSymbol : Symbol {
   internal List<Symbol> ColumnList {get, set}
   internal List<Symbol> ExtentList {get}
   internal List<Symbol> FlattenedExtentList {get, set}
   internal Dictionary<string, Symbol> NameToExtent {get}
   internal bool IsNestedJoin {get, set}

   public JoinSymbol(string name, TypeUsage type, List<Symbol> extents)
}
```

<span data-ttu-id="186fd-161">ColumnList представляет список столбцов в предложении SELECT, если этот символ представляет инструкцию SQL SELECT.</span><span class="sxs-lookup"><span data-stu-id="186fd-161">ColumnList represents the list of columns in the SELECT clause if this symbol represents a SQL SELECT statement.</span></span> <span data-ttu-id="186fd-162">ExtentList - это список экстентов в предложении SELECT.</span><span class="sxs-lookup"><span data-stu-id="186fd-162">ExtentList is the list of extents in the SELECT clause.</span></span> <span data-ttu-id="186fd-163">Если соединение содержит несколько плоских экстентов на верхнем уровне, то FlattenedExtentList отслеживает эти экстенты, чтобы обеспечить правильное переименование псевдонимов экстентов.</span><span class="sxs-lookup"><span data-stu-id="186fd-163">If the join has multiple extents flattened at the top level, FlattenedExtentList tracks the extents to ensure that extent aliases are renamed correctly.</span></span>

<span data-ttu-id="186fd-164">NameToExtent использует все экстенты из ExtentList в качестве словаря.</span><span class="sxs-lookup"><span data-stu-id="186fd-164">NameToExtent has all the extents in ExtentList as a dictionary.</span></span> <span data-ttu-id="186fd-165">IsNestedJoin используется для определения типа JoinSymbol: обычный символ соединения или символ, для которого существует соответствующая SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="186fd-165">IsNestedJoin is used to determine whether a JoinSymbol is an ordinary join symbol or one that has a corresponding SqlSelectStatement.</span></span>

<span data-ttu-id="186fd-166">Все списки задаются ровно один раз, а затем используются для уточняющих запросов и для перечисления.</span><span class="sxs-lookup"><span data-stu-id="186fd-166">All the lists are set exactly once and then used for lookups or enumeration.</span></span>

#### <a name="symboltable"></a><span data-ttu-id="186fd-167">SymbolTable</span><span class="sxs-lookup"><span data-stu-id="186fd-167">SymbolTable</span></span>

<span data-ttu-id="186fd-168">SymbolTable используется для разрешения имен переменных в объекты Symbol.</span><span class="sxs-lookup"><span data-stu-id="186fd-168">SymbolTable is used to resolve variable names to Symbols.</span></span> <span data-ttu-id="186fd-169">SymbolTable реализуется в виде стека с новой записью для каждой области.</span><span class="sxs-lookup"><span data-stu-id="186fd-169">SymbolTable is implemented as a stack with a new entry for each scope.</span></span> <span data-ttu-id="186fd-170">Поиск в уточняющих запросах ведется по стеку сверху вниз, пока не будет найдена запись.</span><span class="sxs-lookup"><span data-stu-id="186fd-170">Lookups search from the top of the stack to the bottom until an entry is found.</span></span>

```csharp
internal sealed class SymbolTable {
   internal void EnterScope()
   internal void ExitScope()
   internal void Add(string name, Symbol value)
   internal Symbol Lookup(string name)
}
```

<span data-ttu-id="186fd-171">Для каждого экземпляра модуля создания SQL существует только одна SymbolTable.</span><span class="sxs-lookup"><span data-stu-id="186fd-171">There is only one SymbolTable per one instance of the Sql Generation module.</span></span> <span data-ttu-id="186fd-172">Для каждого реляционного узла выполняется вход и выход из области.</span><span class="sxs-lookup"><span data-stu-id="186fd-172">Scopes are entered and exited for each relational node.</span></span> <span data-ttu-id="186fd-173">Все символы в ранних областях видны поздним областям, если они не скрыты другими символами с таким же именем.</span><span class="sxs-lookup"><span data-stu-id="186fd-173">All symbols in earlier scopes are visible to later scopes unless hidden by other symbols with the same name.</span></span>

### <a name="global-state-for-the-visitor"></a><span data-ttu-id="186fd-174">Глобальное состояние для посетителя</span><span class="sxs-lookup"><span data-stu-id="186fd-174">Global State for the Visitor</span></span>

<span data-ttu-id="186fd-175">Чтобы упростить переименование псевдонимов и столбцов, ведите список всех имен столбцов (AllColumnNames) и псевдонимов экстентов (AllExtentNames), которые использованы в первом проходе по дереву запроса.</span><span class="sxs-lookup"><span data-stu-id="186fd-175">To assist in renaming of aliases and columns, maintain a list of all the column names (AllColumnNames) and extent aliases (AllExtentNames) that have been used in the first pass over the query tree.</span></span>  <span data-ttu-id="186fd-176">Таблица символов разрешает имена переменных в объекты Symbol.</span><span class="sxs-lookup"><span data-stu-id="186fd-176">The symbol table resolves variable names to Symbols.</span></span> <span data-ttu-id="186fd-177">IsVarRefSingle используется только для проверки и не является безусловно необходимым.</span><span class="sxs-lookup"><span data-stu-id="186fd-177">IsVarRefSingle is only used for verification purposes, it is not strictly necessary.</span></span>

<span data-ttu-id="186fd-178">Два стека, используемые посредством CurrentSelectStatement и IsParentAJoin, служат для передачи параметров от родительских узлов в дочерние, поскольку схема посетителя не позволяет передавать параметры.</span><span class="sxs-lookup"><span data-stu-id="186fd-178">The two stacks used via CurrentSelectStatement and IsParentAJoin are used to pass "parameters" from parent to child nodes, since the visitor pattern does not allow us to pass parameters.</span></span>

```csharp
internal Dictionary<string, int> AllExtentNames {get}
internal Dictionary<string, int> AllColumnNames {get}
SymbolTable symbolTable = new SymbolTable();
bool isVarRefSingle = false;

Stack<SqlSelectStatement> selectStatementStack;
private SqlSelectStatement CurrentSelectStatement{get}

Stack<bool> isParentAJoinStack;
private bool IsParentAJoin{get}
```

## <a name="common-scenarios"></a><span data-ttu-id="186fd-179">Стандартные сценарии</span><span class="sxs-lookup"><span data-stu-id="186fd-179">Common Scenarios</span></span>

<span data-ttu-id="186fd-180">В этом разделе описаны распространенные сценарии использования поставщика.</span><span class="sxs-lookup"><span data-stu-id="186fd-180">This section discusses common provider scenarios.</span></span>

### <a name="grouping-expression-nodes-into-sql-statements"></a><span data-ttu-id="186fd-181">Группирование узлов выражения в инструкции SQL</span><span class="sxs-lookup"><span data-stu-id="186fd-181">Grouping Expression Nodes into SQL Statements</span></span>

<span data-ttu-id="186fd-182">Объект SqlSelectStatement создается, когда при обходе дерева снизу вверх встречается первый реляционный узел (обычно экстент DbScanExpression).</span><span class="sxs-lookup"><span data-stu-id="186fd-182">A SqlSelectStatement is created when the first relational node is encountered (typically a DbScanExpression extent) when visiting the tree from the bottom up.</span></span> <span data-ttu-id="186fd-183">Чтобы создать инструкцию SQL SELECT с минимально возможным количеством вложенных запросов, объедините максимальное число родительских узлов в этой SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="186fd-183">To produce a SQL SELECT statement with as few nested queries as possible, aggregate as many of its parent nodes as possible in that SqlSelectStatement.</span></span>

<span data-ttu-id="186fd-184">Метод IsCompatible определяет, можно ли добавить заданный (реляционный) узел в текущую SqlSelectStatement (возвращенную при обходе входных данных), или нужно запустить новую инструкцию. Решение зависит от узлов, которые уже входят в SqlSelectStatement (и в свою очередь зависят от узлов, располагавшихся под заданным).</span><span class="sxs-lookup"><span data-stu-id="186fd-184">The decision of whether a given (relational) node can be added to the current SqlSelectStatement (the one returned when visiting the input) or if a new statement needs to be started is computed by the method IsCompatible and depends on what is already in the SqlSelectStatement, which depends on what nodes were below the given node.</span></span>

<span data-ttu-id="186fd-185">Обычно, если предложения инструкции SQL вычисляются после предложений, где узлы, планируемые к объединению, не пусты, то узел нельзя добавить в текущую инструкцию.</span><span class="sxs-lookup"><span data-stu-id="186fd-185">Typically, if SQL statement clauses are evaluated after clauses where the nodes being considered for merging are not empty, the node cannot be added to the current statement.</span></span> <span data-ttu-id="186fd-186">Например, если следующий узел является фильтром, то его можно включить в текущую SqlSelectStatement, только если выполняются следующие условия.</span><span class="sxs-lookup"><span data-stu-id="186fd-186">For example, if the next node is a Filter, that node can be incorporated into the current SqlSelectStatement only if the following is true:</span></span>

- <span data-ttu-id="186fd-187">Список SELECT пуст.</span><span class="sxs-lookup"><span data-stu-id="186fd-187">The SELECT list is empty.</span></span> <span data-ttu-id="186fd-188">Если список SELECT не пуст, значит он создан узлом, предшествующим фильтру, и предикат может ссылаться на столбцы, созданные этим списком SELECT.</span><span class="sxs-lookup"><span data-stu-id="186fd-188">If the SELECT list is not empty, the select list was produced by a node preceding the filter and the predicate may refer to columns produced by that SELECT list.</span></span>

- <span data-ttu-id="186fd-189">Предложение GROUPBY пусто.</span><span class="sxs-lookup"><span data-stu-id="186fd-189">The GROUPBY is empty.</span></span> <span data-ttu-id="186fd-190">Если предложение GROUPBY не пусто, то добавление фильтра соответствует фильтрации перед группирования, а такой порядок недопустим.</span><span class="sxs-lookup"><span data-stu-id="186fd-190">If the GROUPBY is not empty, adding the filter would mean filtering before grouping, which is not correct.</span></span>

- <span data-ttu-id="186fd-191">Предложение TOP пусто.</span><span class="sxs-lookup"><span data-stu-id="186fd-191">The TOP clause is empty.</span></span> <span data-ttu-id="186fd-192">Если предложение TOP не пусто, то добавление фильтра соответствует фильтрации перед операцией TOP, а такой порядок недопустим.</span><span class="sxs-lookup"><span data-stu-id="186fd-192">If the TOP clause is not empty, adding the filter would mean filtering before doing TOP, which is not correct.</span></span>

<span data-ttu-id="186fd-193">Эти ограничения не применяются к нереляционным узлам, таким как DbConstantExpression, а также к арифметическим выражениям, которые всегда включаются в существующую SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="186fd-193">This does not apply to non-relational nodes like DbConstantExpression or arithmetic expressions, because these are always included as part of an existing SqlSelectStatement.</span></span>

<span data-ttu-id="186fd-194">Кроме того, после достижение корневого элемента дерева соединения (узла соединения, для которого отсутствует родительский узел), запускается новая SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="186fd-194">Also, when encountering the root of join tree (a join node that does not have a join parent), a new SqlSelectStatement is started.</span></span> <span data-ttu-id="186fd-195">В эту SqlSelectStatement объединяются все дочерние узлы соединения с левой стороны.</span><span class="sxs-lookup"><span data-stu-id="186fd-195">All of its left spine join children are aggregated into that SqlSelectStatement.</span></span>

<span data-ttu-id="186fd-196">Когда запускается новая SqlSelectStatement, а текущая инструкция добавляется во входные данные, может понадобиться завершить текущую SqlSelectStatement путем добавления столбцов проекции (предложение SELECT), если она еще не существует.</span><span class="sxs-lookup"><span data-stu-id="186fd-196">Whenever a new SqlSelectStatement is started, and the current one is added to the input, the current SqlSelectStatement may need to be completed by adding projection columns (a SELECT clause) if one does not exist.</span></span> <span data-ttu-id="186fd-197">Это выполняется методом AddDefaultColumns, который проверяет FromExtents в SqlSelectStatement и добавляет все столбцы из списка экстентов, представленного FromExtents, которые попадают в область в список проецируемых столбцов.</span><span class="sxs-lookup"><span data-stu-id="186fd-197">This is done with the method AddDefaultColumns, which looks at the FromExtents of the SqlSelectStatement and adds all the columns that the list of extents represented by FromExtents brings in scope to the list of projected columns.</span></span> <span data-ttu-id="186fd-198">Эта операция необходима, поскольку на данном этапе неизвестно, на какие столбцы ссылаются другие узлы.</span><span class="sxs-lookup"><span data-stu-id="186fd-198">This is done, because at that point, it is unknown which columns are referenced by the other nodes.</span></span> <span data-ttu-id="186fd-199">Операцию можно оптимизировать так, чтобы проецировать только те столбцы, которые можно использовать в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="186fd-199">This can be optimized to only project the columns that can later be used.</span></span>

### <a name="join-flattening"></a><span data-ttu-id="186fd-200">Преобразование соединений в плоские</span><span class="sxs-lookup"><span data-stu-id="186fd-200">Join Flattening</span></span>

<span data-ttu-id="186fd-201">Свойство IsParentAJoin позволяет определить, можно ли преобразовать заданное соединение в плоское.</span><span class="sxs-lookup"><span data-stu-id="186fd-201">The IsParentAJoin property helps determine whether a given join can be flattened.</span></span> <span data-ttu-id="186fd-202">В частности, IsParentAJoin возвращает значение `true` только для дочернего элемента с левой стороны соединения и для каждого DbScanExpression, которое является непосредственным входом соединения, и в этом случае дочерний узел использует ту же SqlSelectStatement, которую затем будет использовать родительский узел.</span><span class="sxs-lookup"><span data-stu-id="186fd-202">In particular, IsParentAJoin returns `true` only for the left child of a join and for each DbScanExpression that is an immediate input to a join, in which case that child node reuses the same SqlSelectStatement that the parent would later use.</span></span> <span data-ttu-id="186fd-203">Дополнительные сведения см. в разделе «Выражения соединения».</span><span class="sxs-lookup"><span data-stu-id="186fd-203">For more information, see "Join Expressions".</span></span>

### <a name="input-alias-redirecting"></a><span data-ttu-id="186fd-204">Перенаправление входных псевдонимов</span><span class="sxs-lookup"><span data-stu-id="186fd-204">Input Alias Redirecting</span></span>

<span data-ttu-id="186fd-205">Перенаправление входных псевдонимов реализуется с помощью таблицы символов.</span><span class="sxs-lookup"><span data-stu-id="186fd-205">Input alias redirecting is accomplished with the symbol table.</span></span>

<span data-ttu-id="186fd-206">Чтобы объяснить Перенаправление входных псевдонимов, ознакомьтесь с первым примером в разделе [Создание SQL из деревьев команд — рекомендации](generating-sql-from-command-trees-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="186fd-206">To explain input alias redirecting, refer to the first example in [Generating SQL from Command Trees - Best Practices](generating-sql-from-command-trees-best-practices.md).</span></span>  <span data-ttu-id="186fd-207">Символ «a» нужно перенаправить на символ «b» в проекции.</span><span class="sxs-lookup"><span data-stu-id="186fd-207">There "a" needed to be redirected to "b" in the projection.</span></span>

<span data-ttu-id="186fd-208">Когда создается объект SqlSelectStatement, экстент, который является входом узла, помещается в свойство From объекта SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="186fd-208">When a SqlSelectStatement object is created, the extent that is the input to the node is put in the From property of the SqlSelectStatement.</span></span> <span data-ttu-id="186fd-209">Символ (\<symbol_b >) создается на основе имени входной привязки ("b") для представления этого экстента, а "AS" + \<symbol_b > добавляется в предложение FROM.</span><span class="sxs-lookup"><span data-stu-id="186fd-209">A Symbol (\<symbol_b>) is created based on the input binding name ("b") to represent that extent and "AS  " + \<symbol_b> is appended to the From Clause.</span></span>  <span data-ttu-id="186fd-210">Символ также добавляется в свойство FromExtents.</span><span class="sxs-lookup"><span data-stu-id="186fd-210">The symbol is also added to the FromExtents property.</span></span>

<span data-ttu-id="186fd-211">Символ также добавляется в таблицу символов, чтобы связать с ней имя входной привязки ("b", \<symbol_b >).</span><span class="sxs-lookup"><span data-stu-id="186fd-211">The symbol is also added to the symbol table to link the input binding name to it ("b", \<symbol_b>).</span></span>

<span data-ttu-id="186fd-212">Если эта SqlSelectStatement используется в следующем узле, то этот узел добавляет запись в таблицу символов, чтобы связать имя входной привязки с данным символом.</span><span class="sxs-lookup"><span data-stu-id="186fd-212">If a subsequent node reuses that SqlSelectStatement, it adds an entry to the symbol table to link its input binding name to that symbol.</span></span> <span data-ttu-id="186fd-213">В нашем примере Дбпрожектекспрессион с именем входной привязки "a" будет повторно использовать SqlSelectStatement и добавить ("a", \< symbol_b >) в таблицу.</span><span class="sxs-lookup"><span data-stu-id="186fd-213">In our example, the DbProjectExpression with the input binding name of "a" would reuse the SqlSelectStatement and add ("a", \< symbol_b>) to the table.</span></span>

<span data-ttu-id="186fd-214">Когда выражения ссылаются на имя входной привязки узла, который использует SqlSelectStatement, такая ссылка разрешается в нужный перенаправленный символ по таблице символов.</span><span class="sxs-lookup"><span data-stu-id="186fd-214">When expressions reference the input binding name of the node that is reusing the SqlSelectStatement, that reference is resolved using the symbol table to the correct redirected symbol.</span></span> <span data-ttu-id="186fd-215">При разрешении "a" из "a. x" во время посещения Дбвариаблереференцеекспрессион, представляющего "a", он будет разрешаться в символ \<symbol_b >.</span><span class="sxs-lookup"><span data-stu-id="186fd-215">When "a" from "a.x" is resolved while visiting the DbVariableReferenceExpression representing "a" it will resolve to the Symbol \<symbol_b>.</span></span>

### <a name="join-alias-flattening"></a><span data-ttu-id="186fd-216">Преобразование псевдонимов соединений в плоские</span><span class="sxs-lookup"><span data-stu-id="186fd-216">Join Alias Flattening</span></span>

<span data-ttu-id="186fd-217">Преобразование псевдонимов соединений в плоские выполняется при обходе DbPropertyExpression, как описано в разделе «DbPropertyExpression».</span><span class="sxs-lookup"><span data-stu-id="186fd-217">Join alias flattening is achieved when visiting a DbPropertyExpression as described in the section titled DbPropertyExpression.</span></span>

### <a name="column-name-and-extent-alias-renaming"></a><span data-ttu-id="186fd-218">Переименование столбцов и псевдонимов экстентов</span><span class="sxs-lookup"><span data-stu-id="186fd-218">Column Name and Extent Alias Renaming</span></span>

<span data-ttu-id="186fd-219">Задача переименования столбцов и псевдонимов экстентов решается с помощью символов, которые заменяются псевдонимами только на втором этапе создания кода, как описано в разделе «Второй этап формирования SQL: создание строковой команды».</span><span class="sxs-lookup"><span data-stu-id="186fd-219">The issue of column name and extent alias renaming is addressed by using symbols that only get substituted with aliases in the second phase of the generation described in the section titled Second Phase of SQL Generation: Generating the String Command.</span></span>

## <a name="first-phase-of-the-sql-generation-visiting-the-expression-tree"></a><span data-ttu-id="186fd-220">Первый этап формирования SQL: обход дерева выражения</span><span class="sxs-lookup"><span data-stu-id="186fd-220">First Phase of the SQL Generation: Visiting the Expression Tree</span></span>

<span data-ttu-id="186fd-221">В этом разделе описывается первый этап формирования SQL, на котором выполняется обход выражения, представляющего запрос, и создается промежуточная структура: SqlSelectStatement или SqlBuilder.</span><span class="sxs-lookup"><span data-stu-id="186fd-221">This section describes the first phase of SQL generation, when the expression representing the query is visited and an intermediate structure is produced, either a SqlSelectStatement or a SqlBuilder.</span></span>

<span data-ttu-id="186fd-222">В этом разделе описываются правила обхода различных категорий узлов выражения и данные, относящиеся к обходу различных типов выражения.</span><span class="sxs-lookup"><span data-stu-id="186fd-222">This section describes the principles of visiting different expression node categories, and details of visiting specific expression types.</span></span>

### <a name="relational-non-join-nodes"></a><span data-ttu-id="186fd-223">Реляционные узлы (не связанные с соединением)</span><span class="sxs-lookup"><span data-stu-id="186fd-223">Relational (Non-Join) Nodes</span></span>

<span data-ttu-id="186fd-224">Следующие типы выражений поддерживают узлы, не связанные с соединением:</span><span class="sxs-lookup"><span data-stu-id="186fd-224">The following expression types support non-join nodes:</span></span>

- <span data-ttu-id="186fd-225">DbDistinctExpression</span><span class="sxs-lookup"><span data-stu-id="186fd-225">DbDistinctExpression</span></span>

- <span data-ttu-id="186fd-226">DbFilterExpression</span><span class="sxs-lookup"><span data-stu-id="186fd-226">DbFilterExpression</span></span>

- <span data-ttu-id="186fd-227">DbGroupByExpression</span><span class="sxs-lookup"><span data-stu-id="186fd-227">DbGroupByExpression</span></span>

- <span data-ttu-id="186fd-228">DbLimitExpression</span><span class="sxs-lookup"><span data-stu-id="186fd-228">DbLimitExpression</span></span>

- <span data-ttu-id="186fd-229">DbProjectExpression</span><span class="sxs-lookup"><span data-stu-id="186fd-229">DbProjectExpression</span></span>

- <span data-ttu-id="186fd-230">DbSkipExpression</span><span class="sxs-lookup"><span data-stu-id="186fd-230">DbSkipExpression</span></span>

- <span data-ttu-id="186fd-231">DbSortExpression</span><span class="sxs-lookup"><span data-stu-id="186fd-231">DbSortExpression</span></span>

<span data-ttu-id="186fd-232">Обход этих узлов выполняется по следующей схеме:</span><span class="sxs-lookup"><span data-stu-id="186fd-232">Visiting these nodes follows the following pattern:</span></span>

1. <span data-ttu-id="186fd-233">Обход реляционного входа и получение результирующей SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="186fd-233">Visit the relational input and get the resulting SqlSelectStatement.</span></span> <span data-ttu-id="186fd-234">Входом реляционного узла может быть один из следующих объектов:</span><span class="sxs-lookup"><span data-stu-id="186fd-234">The input to a relational node could be one of the following:</span></span>

    - <span data-ttu-id="186fd-235">Реляционный узел, включающий экстент (например, DbScanExpression).</span><span class="sxs-lookup"><span data-stu-id="186fd-235">A relational node, including an extent (a DbScanExpression, for example).</span></span> <span data-ttu-id="186fd-236">При обходе такого узла возвращается SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="186fd-236">Visiting such a node returns a SqlSelectStatement.</span></span>

    - <span data-ttu-id="186fd-237">Выражение операции с наборами (например, UNION ALL).</span><span class="sxs-lookup"><span data-stu-id="186fd-237">A set operation expression (UNION ALL, for example).</span></span> <span data-ttu-id="186fd-238">Результат необходимо заключить в квадратные скобки и поместить в предложение FROM новой SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="186fd-238">The result has to be wrapped in brackets and put in the FROM clause of a new SqlSelectStatement.</span></span>

2. <span data-ttu-id="186fd-239">Проверьте, можно ли добавить текущий узел в SqlSelectStatement, созданную по входным данным.</span><span class="sxs-lookup"><span data-stu-id="186fd-239">Check whether the current node can be added to the SqlSelectStatement produced by the input.</span></span> <span data-ttu-id="186fd-240">Это описано в разделе «Выражение группирования в инструкции SQL».</span><span class="sxs-lookup"><span data-stu-id="186fd-240">The section titled Grouping Expressions into SQL Statements describes this.</span></span> <span data-ttu-id="186fd-241">Если добавление невозможно,</span><span class="sxs-lookup"><span data-stu-id="186fd-241">If not,</span></span>

    - <span data-ttu-id="186fd-242">удалите из стека текущий объект SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="186fd-242">Pop the current SqlSelectStatement object.</span></span>

    - <span data-ttu-id="186fd-243">Создайте новый объект SqlSelectStatement и добавьте удаленный из стека объект SqlSelectStatement в качестве предложения FROM нового объекта SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="186fd-243">Create a new SqlSelectStatement object and add the popped SqlSelectStatement as the FROM of the new SqlSelectStatement object.</span></span>

    - <span data-ttu-id="186fd-244">Поместите новый объект на верх стека.</span><span class="sxs-lookup"><span data-stu-id="186fd-244">Put the new object on top of the stack.</span></span>

3. <span data-ttu-id="186fd-245">Перенаправьте входную привязку выражения к правильному символу из входа.</span><span class="sxs-lookup"><span data-stu-id="186fd-245">Redirect the input expression binding to the correct symbol from the input.</span></span> <span data-ttu-id="186fd-246">Эти сведения хранятся в объекте SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="186fd-246">This information is maintained in the SqlSelectStatement object.</span></span>

4. <span data-ttu-id="186fd-247">Добавьте новую область SymbolTable.</span><span class="sxs-lookup"><span data-stu-id="186fd-247">Add a new SymbolTable scope.</span></span>

5. <span data-ttu-id="186fd-248">Выполните обход части выражения, не связанной с входом (например, проекция и предикат).</span><span class="sxs-lookup"><span data-stu-id="186fd-248">Visit the non-input part of the expression (for example, Projection and Predicate).</span></span>

6. <span data-ttu-id="186fd-249">Удалите из стека все объекты, добавленные в глобальные стеки.</span><span class="sxs-lookup"><span data-stu-id="186fd-249">Pop all the objects added to the global stacks.</span></span>

 <span data-ttu-id="186fd-250">Для DbSkipExpression отсутствуют прямой эквивалент в SQL.</span><span class="sxs-lookup"><span data-stu-id="186fd-250">DbSkipExpression not have a direct equivalent in SQL.</span></span> <span data-ttu-id="186fd-251">Логическим образом он преобразуется в:</span><span class="sxs-lookup"><span data-stu-id="186fd-251">Logically, it is translated into:</span></span>

```sql
SELECT Y.x1, Y.x2, ..., Y.xn
FROM (
   SELECT X.x1, X.x2, ..., X.xn, row_number() OVER (ORDER BY sk1, sk2, ...) AS [row_number]
   FROM input as X
   ) as Y
WHERE Y.[row_number] > count
ORDER BY sk1, sk2, ...
```

### <a name="join-expressions"></a><span data-ttu-id="186fd-252">Выражения соединения</span><span class="sxs-lookup"><span data-stu-id="186fd-252">Join Expressions</span></span>

<span data-ttu-id="186fd-253">Следующие выражения считаются выражениями соединения и обрабатываются методом VisitJoinExpression одинаковым образом:</span><span class="sxs-lookup"><span data-stu-id="186fd-253">The following are considered join expressions and they are processed in a common way, by the VisitJoinExpression method:</span></span>

- <span data-ttu-id="186fd-254">DbApplyExpression</span><span class="sxs-lookup"><span data-stu-id="186fd-254">DbApplyExpression</span></span>

- <span data-ttu-id="186fd-255">DbJoinExpression</span><span class="sxs-lookup"><span data-stu-id="186fd-255">DbJoinExpression</span></span>

- <span data-ttu-id="186fd-256">DbCrossJoinExpression</span><span class="sxs-lookup"><span data-stu-id="186fd-256">DbCrossJoinExpression</span></span>

<span data-ttu-id="186fd-257">Далее перечислены этапы обхода.</span><span class="sxs-lookup"><span data-stu-id="186fd-257">The following are the visit steps:</span></span>

<span data-ttu-id="186fd-258">Сначала, перед обходом дочерних элементов, вызывается метод IsParentAJoin, чтобы определить, является ли узел соединения дочерним элементом соединения с левой стороны.</span><span class="sxs-lookup"><span data-stu-id="186fd-258">First, before visiting the children, IsParentAJoin is invoked to check whether the join node is a child of a join along a left spine.</span></span> <span data-ttu-id="186fd-259">Если этот метод возвращает значение false, запускается новая SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="186fd-259">If it returns false, a new SqlSelectStatement is started.</span></span> <span data-ttu-id="186fd-260">С этой точки зрения обход соединений выполняется иначе, чем остальных узлов, поскольку родительский элемент (узел соединения) создает SqlSelectStatement, которую могут использовать дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="186fd-260">In that sense, joins are visited differently from the rest of the nodes, as the parent (the join node) creates the SqlSelectStatement for the children to possibly use.</span></span>

<span data-ttu-id="186fd-261">Затем поочередно обрабатываются входы.</span><span class="sxs-lookup"><span data-stu-id="186fd-261">Second, process the inputs one at a time.</span></span> <span data-ttu-id="186fd-262">Для каждого входа выполняются следующие действия.</span><span class="sxs-lookup"><span data-stu-id="186fd-262">For each input:</span></span>

1. <span data-ttu-id="186fd-263">Обход входа.</span><span class="sxs-lookup"><span data-stu-id="186fd-263">Visit the input.</span></span>

2. <span data-ttu-id="186fd-264">Дополнительная обработка результатов обхода входа путем вызова метода ProcessJoinInputResult, который отвечает за ведение таблицы символов после обхода дочернего элемента выражения соединения и возможное завершение SqlSelectStatement, созданной дочерним элементом.</span><span class="sxs-lookup"><span data-stu-id="186fd-264">Post process the result of visiting the input by invoking ProcessJoinInputResult, which is responsible for maintaining the symbol table after visiting a child of a join expression and possibly finishing the SqlSelectStatement produced by the child.</span></span> <span data-ttu-id="186fd-265">Результатом дочернего элемента может быть один из следующих объектов:</span><span class="sxs-lookup"><span data-stu-id="186fd-265">The child's result could be one of the following:</span></span>

    - <span data-ttu-id="186fd-266">Объект SqlSelectStatement, отличный от объекта, в который будет добавлен родительский элемент.</span><span class="sxs-lookup"><span data-stu-id="186fd-266">A SqlSelectStatement different from the one to which the parent will be added.</span></span> <span data-ttu-id="186fd-267">В этом случае может понадобиться завершить инструкцию, добавив столбцы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="186fd-267">In such case, it may need to be completed by adding default columns.</span></span> <span data-ttu-id="186fd-268">Если вход представлял соединение, необходимо создать новый символ соединения.</span><span class="sxs-lookup"><span data-stu-id="186fd-268">If the input was a Join, you need to create a new join symbol.</span></span> <span data-ttu-id="186fd-269">В противном случае создайте обычный символ.</span><span class="sxs-lookup"><span data-stu-id="186fd-269">Otherwise, create a normal symbol.</span></span>

    - <span data-ttu-id="186fd-270">Экстент (например, DbScanExpression). В этом случае он просто добавляется в список входов родительской SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="186fd-270">An extent (a DbScanExpression, for example), in which case it is simply added to the list of inputs of the parent’s SqlSelectStatement.</span></span>

    - <span data-ttu-id="186fd-271">Объект, отличный от SqlSelectStatement. В этом случае он заключается в квадратные скобки.</span><span class="sxs-lookup"><span data-stu-id="186fd-271">Not a SqlSelectStatement, in which case it is wrapped with brackets.</span></span>

    - <span data-ttu-id="186fd-272">Объект SqlSelectStatement, в который добавляется родительский элемент.</span><span class="sxs-lookup"><span data-stu-id="186fd-272">The same SqlSelectStatement to which the parent is added.</span></span> <span data-ttu-id="186fd-273">В этом случае символы из списка FromExtents необходимо заменить единичным новым JoinSymbol, который представляет сразу все символы.</span><span class="sxs-lookup"><span data-stu-id="186fd-273">In such case, the symbols in the FromExtents list need to be replaced with a single new JoinSymbol representing them all.</span></span>

    - <span data-ttu-id="186fd-274">В первых трех случаях вызывается метод AddFromSymbol для добавления предложения AS и обновления таблицы символов.</span><span class="sxs-lookup"><span data-stu-id="186fd-274">For the first three cases, AddFromSymbol is called to add the AS clause, and update the symbol table.</span></span>

<span data-ttu-id="186fd-275">Затем выполняется обход условия соединения (если таковое присутствует).</span><span class="sxs-lookup"><span data-stu-id="186fd-275">Third, the join condition (if any) is visited.</span></span>

### <a name="set-operations"></a><span data-ttu-id="186fd-276">Операции над множествами</span><span class="sxs-lookup"><span data-stu-id="186fd-276">Set Operations</span></span>

<span data-ttu-id="186fd-277">Операции с наборами DbUnionAllExpression, DbExceptExpression и DbIntersectExpression обрабатываются методом VisitSetOpExpression.</span><span class="sxs-lookup"><span data-stu-id="186fd-277">The set operations DbUnionAllExpression, DbExceptExpression, and DbIntersectExpression are processed by the method VisitSetOpExpression.</span></span> <span data-ttu-id="186fd-278">Он создает SqlBuilder формы</span><span class="sxs-lookup"><span data-stu-id="186fd-278">It creates a SqlBuilder of the shape</span></span>

```xml
<leftSqlSelectStatement> <setOp> <rightSqlSelectStatement>
```

<span data-ttu-id="186fd-279">Где \<Лефтсклселектстатемент > и \<Ригхтсклселектстатемент > Склселектстатементс получены путем посещения каждого из входных данных, а \<Сетоп > — соответствующей операцией (например, UNION ALL).</span><span class="sxs-lookup"><span data-stu-id="186fd-279">Where \<leftSqlSelectStatement> and \<rightSqlSelectStatement> are SqlSelectStatements obtained by visiting each of the inputs, and \<setOp> is the corresponding operation (UNION ALL for example).</span></span>

### <a name="dbscanexpression"></a><span data-ttu-id="186fd-280">DbScanExpression</span><span class="sxs-lookup"><span data-stu-id="186fd-280">DbScanExpression</span></span>

<span data-ttu-id="186fd-281">Если обход выполняется в контексте соединения (в качестве входа соединения, которое является левым дочерним элементом другого соединения), то DbScanExpression возвращает SqlBuilder с целевым кодом SQL для соответствующей цели (определяющий запрос, таблицу или представление).</span><span class="sxs-lookup"><span data-stu-id="186fd-281">If visited in a join context (as an input to a join that is a left child of another join), DbScanExpression returns a SqlBuilder with the target SQL for the corresponding target, which is either a defining query, table, or a view.</span></span> <span data-ttu-id="186fd-282">В противном случае создается новый объект SqlSelectStatement с набором полей FROM в соответствии с целью.</span><span class="sxs-lookup"><span data-stu-id="186fd-282">Otherwise, a new SqlSelectStatement is created with the FROM field set to correspond to the corresponding target.</span></span>

### <a name="dbvariablereferenceexpression"></a><span data-ttu-id="186fd-283">DbVariableReferenceExpression</span><span class="sxs-lookup"><span data-stu-id="186fd-283">DbVariableReferenceExpression</span></span>

<span data-ttu-id="186fd-284">При обходе DbVariableReferenceExpression возвращается объект Symbol, соответствующей этому выражению со ссылкой на переменную на основе уточняющего запроса в таблице символов.</span><span class="sxs-lookup"><span data-stu-id="186fd-284">The visit of a DbVariableReferenceExpression returns the Symbol corresponding to that variable reference expression based on a look up in the symbol table.</span></span>

### <a name="dbpropertyexpression"></a><span data-ttu-id="186fd-285">DbPropertyExpression</span><span class="sxs-lookup"><span data-stu-id="186fd-285">DbPropertyExpression</span></span>

<span data-ttu-id="186fd-286">Преобразование псевдонимов соединения в плоские определяется и обрабатывается при обходе DbPropertyExpression.</span><span class="sxs-lookup"><span data-stu-id="186fd-286">Join alias flattening is identified and processed when visiting a DbPropertyExpression.</span></span>

<span data-ttu-id="186fd-287">Сначала выполняется обход свойства Instance, и результатом является объект Symbol, JoinSymbol или SymbolPair.</span><span class="sxs-lookup"><span data-stu-id="186fd-287">The Instance property is first visited and the result is a Symbol, a JoinSymbol, or a SymbolPair.</span></span> <span data-ttu-id="186fd-288">Эти три случая обрабатываются следующим образом.</span><span class="sxs-lookup"><span data-stu-id="186fd-288">Here is how these three cases are handled:</span></span>

- <span data-ttu-id="186fd-289">Если возвращается JoinSymbol, то его свойство NameToExtent содержит символ для нужного свойства.</span><span class="sxs-lookup"><span data-stu-id="186fd-289">If a JoinSymbol is returned, than its NameToExtent property contains a symbol for the needed property.</span></span> <span data-ttu-id="186fd-290">Если символ соединения представляет вложенное соединения, то возвращается новая пара символов с символом соединения для отслеживания символа, который будет использоваться в качестве псевдонима экземпляра, и символом, представляющим фактическое свойство для дальнейшего разрешения.</span><span class="sxs-lookup"><span data-stu-id="186fd-290">If the join symbol represents a nested join, a new Symbol pair is returned with the join symbol to track the symbol that would be used as the instance alias, and the symbol representing the actual property for further resolving.</span></span>

- <span data-ttu-id="186fd-291">Если возвращается SymbolPair, в которой часть Column является символом соединения, то снова возвращается символ соединения, однако теперь свойство столбца обновляется и указывает на свойство, представляемое текущим выражением свойства.</span><span class="sxs-lookup"><span data-stu-id="186fd-291">If a SymbolPair is returned and the Column part is a join symbol, a join symbol is again returned, but now the column property is updated to point to the property represented by the current property expression.</span></span> <span data-ttu-id="186fd-292">В противном случае возвращается SqlBuilder с источником SymbolPair в качестве псевдонима и символом для текущего свойства в качестве столбца.</span><span class="sxs-lookup"><span data-stu-id="186fd-292">Otherwise a SqlBuilder is returned with the SymbolPair source as the alias, and the symbol for the current property as the column.</span></span>

- <span data-ttu-id="186fd-293">Если возвращается объект Symbol, то метод Visit возвращает объект SqlBuilder с этим экземпляром в качестве псевдонима и именем свойства в качестве имени столбца.</span><span class="sxs-lookup"><span data-stu-id="186fd-293">If a Symbol is returned, the Visit method returns a SqlBuilder method with that instance as the alias, and the property name as column name.</span></span>

### <a name="dbnewinstanceexpression"></a><span data-ttu-id="186fd-294">DbNewInstanceExpression</span><span class="sxs-lookup"><span data-stu-id="186fd-294">DbNewInstanceExpression</span></span>

<span data-ttu-id="186fd-295">Если DbNewInstanceExpression используется в качестве свойства Projection объекта DbProjectExpression, то создается список аргументов с разделителями-запятыми, представляющий проецируемые столбцы.</span><span class="sxs-lookup"><span data-stu-id="186fd-295">When used as the Projection property of DbProjectExpression, DbNewInstanceExpression produces a comma-separated list of the arguments to represent the projected columns.</span></span>

<span data-ttu-id="186fd-296">Если DbNewInstanceExpression имеет тип возвращаемого значения коллекции и определяет новую коллекцию выражений, предоставляемых в качестве аргументов, то следующие три случая обрабатываются отдельно.</span><span class="sxs-lookup"><span data-stu-id="186fd-296">When DbNewInstanceExpression has a collection return type, and defines a new collection of the expressions provided as arguments, the following three cases are handled separately:</span></span>

- <span data-ttu-id="186fd-297">Если единственным аргументом DbNewInstanceExpression является DbElementExpression, он преобразуется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="186fd-297">If DbNewInstanceExpression has DbElementExpression as the only argument, it is translated as follows:</span></span>

```sql
NewInstance(Element(X)) =>  SELECT TOP 1 …FROM X
```

<span data-ttu-id="186fd-298">Если DbNewInstanceExpression не имеет аргументов (представляет пустую таблицу), то DbNewInstanceExpression преобразуется в следующее выражение:</span><span class="sxs-lookup"><span data-stu-id="186fd-298">If DbNewInstanceExpression has no arguments (represents an empty table), DbNewInstanceExpression is translated into:</span></span>

```sql
SELECT CAST(NULL AS <primitiveType>) as X
FROM (SELECT 1) AS Y WHERE 1=0
```

<span data-ttu-id="186fd-299">В противном случае DbNewInstanceExpression выстраивает лестницу аргументов UNION ALL.</span><span class="sxs-lookup"><span data-stu-id="186fd-299">Otherwise DbNewInstanceExpression builds a union-all ladder of the arguments:</span></span>

```sql
SELECT <visit-result-arg1> as X
UNION ALL SELECT <visit-result-arg2> as X
UNION ALL …
UNION ALL SELECT <visit-result-argN> as X
```

### <a name="dbfunctionexpression"></a><span data-ttu-id="186fd-300">DbFunctionExpression</span><span class="sxs-lookup"><span data-stu-id="186fd-300">DbFunctionExpression</span></span>

<span data-ttu-id="186fd-301">Канонические и встроенные функции обрабатываются одинаково: если требуется специальная обработка (например, преобразование TRIM(string) в LTRIM(RTRIM(string))), то вызывается нужный обработчик.</span><span class="sxs-lookup"><span data-stu-id="186fd-301">Canonical and built-in functions are processed the same way: if they need special handling (TRIM(string) to  LTRIM(RTRIM(string), for example), the appropriate handler is invoked.</span></span> <span data-ttu-id="186fd-302">В противном случае такие функции преобразуются в формат Имя_функции(аргумент1, аргумент2, ..., аргументN).</span><span class="sxs-lookup"><span data-stu-id="186fd-302">Otherwise they are translated to FunctionName(arg1, arg2, ..., argn).</span></span>

<span data-ttu-id="186fd-303">Словари используются для отслеживания функций, которым требуется специальная обработка, и соответствующих обработчиков.</span><span class="sxs-lookup"><span data-stu-id="186fd-303">Dictionaries are used to keep track of which functions need special handling and their appropriate handlers.</span></span>

<span data-ttu-id="186fd-304">Определяемые пользователем функции переводятся в самое правое. FunctionName (arg1, arg2,..., argN).</span><span class="sxs-lookup"><span data-stu-id="186fd-304">User-defined functions are translated to NamespaceName.FunctionName(arg1, arg2, ..., argn).</span></span>

### <a name="dbelementexpression"></a><span data-ttu-id="186fd-305">DbElementExpression</span><span class="sxs-lookup"><span data-stu-id="186fd-305">DbElementExpression</span></span>

<span data-ttu-id="186fd-306">Метод, выполняющий обход DbElementExpression, вызывается, только если DbElementExpression представляет скалярный вложенный запрос.</span><span class="sxs-lookup"><span data-stu-id="186fd-306">The method that visits DbElementExpression is only invoked for visiting a DbElementExpression when used to represent a scalar subquery.</span></span> <span data-ttu-id="186fd-307">Поэтому DbElementExpression преобразуется в законченную SqlSelectStatement и заключается в квадратные скобки.</span><span class="sxs-lookup"><span data-stu-id="186fd-307">Therefore, DbElementExpression translates into a complete SqlSelectStatement and adds brackets around it.</span></span>

### <a name="dbquantifierexpression"></a><span data-ttu-id="186fd-308">DbQuantifierExpression</span><span class="sxs-lookup"><span data-stu-id="186fd-308">DbQuantifierExpression</span></span>

<span data-ttu-id="186fd-309">В зависимости от типа выражения (Any или ALL) Дбкуантифиерекспрессион преобразуется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="186fd-309">Depending on the expression type (Any or All), DbQuantifierExpression is translated as:</span></span>

```sql
Any(input, x) => Exists(Filter(input,x))
All(input, x) => Not Exists(Filter(input, not(x))
```

### <a name="dbnotexpression"></a><span data-ttu-id="186fd-310">DbNotExpression</span><span class="sxs-lookup"><span data-stu-id="186fd-310">DbNotExpression</span></span>

<span data-ttu-id="186fd-311">В некоторых случаях можно свернуть преобразование DbNotExpression с входным выражением.</span><span class="sxs-lookup"><span data-stu-id="186fd-311">In some cases it is possible to collapse the translation of DbNotExpression with its input expression.</span></span> <span data-ttu-id="186fd-312">Пример:</span><span class="sxs-lookup"><span data-stu-id="186fd-312">For example:</span></span>

```sql
Not(IsNull(a)) =>  "a IS NOT NULL"
Not(All(input, x) => Not (Not Exists(Filter(input, not(x))) => Exists(Filter(input, not(x))
```

<span data-ttu-id="186fd-313">Второе свертывание выполняется, поскольку поставщик неэффективным образом преобразует DbQuantifierExpression типа «все».</span><span class="sxs-lookup"><span data-stu-id="186fd-313">The reason the second collapse is performed is because inefficiencies were introduced by the provider when translating DbQuantifierExpression of type All.</span></span> <span data-ttu-id="186fd-314">Поэтому платформа Entity Framework не может выполнить упрощение.</span><span class="sxs-lookup"><span data-stu-id="186fd-314">Thus the Entity Framework could not have done the simplification.</span></span>

### <a name="dbisemptyexpression"></a><span data-ttu-id="186fd-315">DbIsEmptyExpression</span><span class="sxs-lookup"><span data-stu-id="186fd-315">DbIsEmptyExpression</span></span>

<span data-ttu-id="186fd-316">DbIsEmptyExpression преобразуется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="186fd-316">DbIsEmptyExpression is translated as:</span></span>

```sql
IsEmpty(input) = Not Exists(input)
```

## <a name="second-phase-of-sql-generation-generating-the-string-command"></a><span data-ttu-id="186fd-317">Второй этап формирования SQL: создание строковой команды</span><span class="sxs-lookup"><span data-stu-id="186fd-317">Second Phase of SQL Generation: Generating the String Command</span></span>

<span data-ttu-id="186fd-318">При создании строковой команды SQL объект SqlSelectStatement создает фактические псевдонимы для символов, чтобы решить задачу переименования столбцов и псевдонимов экстентов.</span><span class="sxs-lookup"><span data-stu-id="186fd-318">When generating a string SQL command, the SqlSelectStatement produces actual aliases for the symbols, which addresses the issue of column name and extent alias renaming.</span></span>

<span data-ttu-id="186fd-319">Переименование псевдонимов экстентов происходит при записи объекта SqlSelectStatement в строку.</span><span class="sxs-lookup"><span data-stu-id="186fd-319">Extent alias renaming occurs while writing the SqlSelectStatement object into a string.</span></span> <span data-ttu-id="186fd-320">Сначала создайте список всех псевдонимов, используемых внешними экстентами.</span><span class="sxs-lookup"><span data-stu-id="186fd-320">First create a list of all the aliases used by the outer extents.</span></span> <span data-ttu-id="186fd-321">Каждый символ в списке FromExtents (или AllJoinExtents, если его значение отлично от null) проходит переименование, если он вызывает конфликт с любым из внешних экстентов.</span><span class="sxs-lookup"><span data-stu-id="186fd-321">Each symbol in the FromExtents (or AllJoinExtents if it is non-null), gets renamed if it collides with any of the outer extents.</span></span> <span data-ttu-id="186fd-322">Если требуется переименование, то исключается конфликт с экстентами, собранными в AllExtentNames.</span><span class="sxs-lookup"><span data-stu-id="186fd-322">If renaming is needed, it will not conflict with any of the extents collected in AllExtentNames.</span></span>

<span data-ttu-id="186fd-323">Переименование столбцов происходит при записи объекта Symbol в строку.</span><span class="sxs-lookup"><span data-stu-id="186fd-323">Column renaming occurs while writing a Symbol object to a string.</span></span> <span data-ttu-id="186fd-324">Метод AddDefaultColumns на первом этапе определяет необходимость переименования каждого символа столбца.</span><span class="sxs-lookup"><span data-stu-id="186fd-324">AddDefaultColumns in the first phase has determined if a certain column symbol has to be renamed.</span></span> <span data-ttu-id="186fd-325">На втором этапе выполняется только переименование. Это гарантирует, что созданное имя не вызывает конфликт с именами, используемыми в AllColumnNames</span><span class="sxs-lookup"><span data-stu-id="186fd-325">In the second phase only the rename occurs making sure that the name produced does not conflict with any name used in AllColumnNames</span></span>

<span data-ttu-id="186fd-326">Чтобы создать уникальные имена для псевдонимов экстентов и для столбцов, используйте \<existing_name > _N, где n — самый маленький псевдоним, который еще не использовался.</span><span class="sxs-lookup"><span data-stu-id="186fd-326">To produce unique names both for extent aliases and for columns, use \<existing_name>_n where n is the smallest alias that has not been used yet.</span></span> <span data-ttu-id="186fd-327">Наличие глобального списка всех псевдонимов усиливает потребность в каскадном переименовании.</span><span class="sxs-lookup"><span data-stu-id="186fd-327">The global list of all aliases increases the need for cascading renames.</span></span>

## <a name="see-also"></a><span data-ttu-id="186fd-328">См. также</span><span class="sxs-lookup"><span data-stu-id="186fd-328">See also</span></span>

- [<span data-ttu-id="186fd-329">Создание кода SQL в образце поставщика</span><span class="sxs-lookup"><span data-stu-id="186fd-329">SQL Generation in the Sample Provider</span></span>](sql-generation-in-the-sample-provider.md)
