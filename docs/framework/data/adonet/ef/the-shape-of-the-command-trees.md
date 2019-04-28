---
title: Форма деревьев команд
ms.date: 03/30/2017
ms.assetid: 2215585e-ca47-45f8-98d4-8cb982f8c1d3
ms.openlocfilehash: 08a67c8d181188cbc14c6f60876a7e26cd6de25a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763988"
---
# <a name="the-shape-of-the-command-trees"></a><span data-ttu-id="d4b6c-102">Форма деревьев команд</span><span class="sxs-lookup"><span data-stu-id="d4b6c-102">The Shape of the Command Trees</span></span>

<span data-ttu-id="d4b6c-103">Модуль создания кода SQL отвечает за создание кода SQL, зависящего от конкретного сервера запроса, на основе данного входного выражения дерева команд запроса.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-103">The SQL generation module is responsible for generating a backend specific SQL query based on a given input query command tree expression.</span></span> <span data-ttu-id="d4b6c-104">В этом разделе описываются характеристики, свойства и структура деревьев команд запроса.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-104">This section discusses the characteristics, properties, and structure of the query command trees.</span></span>

## <a name="query-command-trees-overview"></a><span data-ttu-id="d4b6c-105">Общие сведения о деревьях команд запроса</span><span class="sxs-lookup"><span data-stu-id="d4b6c-105">Query Command Trees Overview</span></span>

<span data-ttu-id="d4b6c-106">Дерево команд запроса является представлением объектной модели запроса.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-106">A query command tree is an object model representation of a query.</span></span> <span data-ttu-id="d4b6c-107">Деревья команд запроса используются для двух целей.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-107">Query command trees serve two purposes:</span></span>

- <span data-ttu-id="d4b6c-108">Представление входного запроса, который задан по отношению к [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d4b6c-108">To express an input query that is specified against the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>

- <span data-ttu-id="d4b6c-109">Представление выходного запроса, который передается поставщику и описывает запрос по отношению к серверу базы данных.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-109">To express an output query that is given to a provider and describes a query against the backend.</span></span>

<span data-ttu-id="d4b6c-110">Деревья команд запроса поддерживают более развитую семантику по сравнению с запросами, совместимыми с SQL:1999, включая поддержку работы с вложенными коллекциями и операциями типа, такими как проверка того, имеет ли сущность конкретный тип, или фильтрации наборов с учетом типа.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-110">Query command trees support richer semantics than SQL:1999 compliant queries, including support for working with nested collections and type operations, like checking whether an entity is of a particular type, or filtering sets based on a type.</span></span>

<span data-ttu-id="d4b6c-111">Свойство DBQueryCommandTree.Query является корнем дерева выражения, которое описывает логику запроса.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-111">The DBQueryCommandTree.Query property is the root of the expression tree that describes the query logic.</span></span> <span data-ttu-id="d4b6c-112">Свойство DBQueryCommandTree.Parameters содержит список параметров, которые используются в запросе.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-112">The DBQueryCommandTree.Parameters property contains a list of parameters that are used in the query.</span></span> <span data-ttu-id="d4b6c-113">Дерево выражения состоит из объектов DbExpression.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-113">The expression tree is composed of DbExpression objects.</span></span>

<span data-ttu-id="d4b6c-114">Объект DbExpression представляет некоторое вычисление.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-114">A DbExpression object represents some computation.</span></span> <span data-ttu-id="d4b6c-115">Для составления выражений запросов [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] предоставляет несколько видов выражений, включая константы, переменные, функции, конструкторы и стандартные реляционные операторы, такие как фильтрация и соединение.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-115">Several kinds of expressions are provided by the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] for composing query expressions, including constants, variables, functions, constructors, and standard relational operators like filter and join.</span></span> <span data-ttu-id="d4b6c-116">Каждый объект DbExpression имеет свойство ResultType, которое представляет тип результата, формируемого этим выражением.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-116">Every DbExpression object has a ResultType property that represents the type of the result produced by that expression.</span></span> <span data-ttu-id="d4b6c-117">Этот тип выражается как TypeUsage.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-117">This type is expressed as a TypeUsage.</span></span>

## <a name="shapes-of-the-output-query-command-tree"></a><span data-ttu-id="d4b6c-118">Формы деревьев команд выходного запроса</span><span class="sxs-lookup"><span data-stu-id="d4b6c-118">Shapes of the Output Query Command Tree</span></span>

<span data-ttu-id="d4b6c-119">Деревья команд выходного запроса подробно представляют реляционные запросы (SQL) и соответствуют намного более строгим правилам по сравнению с теми, которые применяются к деревьям команд запроса.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-119">Output query command trees closely represent relational (SQL) queries and adhere to much stricter rules than those that apply to query command trees.</span></span> <span data-ttu-id="d4b6c-120">Они обычно содержат конструкции, которые легко преобразуются в код SQL.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-120">They typically contain constructs that are easily translated to SQL.</span></span>

<span data-ttu-id="d4b6c-121">Деревья входных команд выражаются применительно к концептуальной модели, которая поддерживает свойства навигации, ассоциации среди сущностей и наследование.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-121">Input command trees are expressed against the conceptual model, which supports navigation properties, associations among entities, and inheritance.</span></span> <span data-ttu-id="d4b6c-122">Деревья выходных команд выражаются применительно к модели хранения.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-122">Output command trees are expressed against the storage model.</span></span> <span data-ttu-id="d4b6c-123">Деревья входных команд позволяют проецировать вложенные коллекции, а деревья выходных команд - нет.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-123">Input command trees allow you to project nested collections, but output command trees do not.</span></span>

<span data-ttu-id="d4b6c-124">Деревья выходных команд запроса формируются с использованием подмножества доступных объектов DbExpression, и даже некоторые выражения в этом подмножестве имеют ограниченное использование.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-124">Output query command trees are built using a subset of the available DbExpression objects and even some expressions in that subset have restricted usage.</span></span>

<span data-ttu-id="d4b6c-125">Операции типа, такие как проверка того, имеет ли данное выражение конкретный тип, или фильтрация наборов с учетом типа, отсутствуют в деревьях выходных команд.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-125">Type operations, like checking whether a given expression is of a particular type or filtering sets based on a type, are not present in output command trees.</span></span>

<span data-ttu-id="d4b6c-126">В деревьях выходных команд для проекций используются только выражения, которые возвращают значения типа Boolean, и только для предикатов в выражениях, требующих предиката, таких как фильтр или инструкция CASE.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-126">In output command trees, only expressions that return Boolean values are used for projections and only for predicates in expressions requiring a predicate, like a filter or a case statement.</span></span>

<span data-ttu-id="d4b6c-127">Корнем деревьев выходных команд запроса является объект DbProjectExpression.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-127">The root of an output query command trees is a DbProjectExpression object.</span></span>

### <a name="expression-types-not-present-in-output-query-command-trees"></a><span data-ttu-id="d4b6c-128">Типы выражений, не присутствующих в деревьях выходных команд запроса</span><span class="sxs-lookup"><span data-stu-id="d4b6c-128">Expression Types Not Present in Output Query Command Trees</span></span>

<span data-ttu-id="d4b6c-129">Следующие типы выражений не допускаются в дереве выходных команд запроса и не требуют обработки поставщиками.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-129">The following expression types are not valid in an output query command tree and do not need to be handled by providers:</span></span>

- <span data-ttu-id="d4b6c-130">DbDerefExpression</span><span class="sxs-lookup"><span data-stu-id="d4b6c-130">DbDerefExpression</span></span>

- <span data-ttu-id="d4b6c-131">DbEntityRefExpression</span><span class="sxs-lookup"><span data-stu-id="d4b6c-131">DbEntityRefExpression</span></span>

- <span data-ttu-id="d4b6c-132">DbRefKeyExpression</span><span class="sxs-lookup"><span data-stu-id="d4b6c-132">DbRefKeyExpression</span></span>

- <span data-ttu-id="d4b6c-133">DbIsOfExpression</span><span class="sxs-lookup"><span data-stu-id="d4b6c-133">DbIsOfExpression</span></span>

- <span data-ttu-id="d4b6c-134">DbOfTypeExpression</span><span class="sxs-lookup"><span data-stu-id="d4b6c-134">DbOfTypeExpression</span></span>

- <span data-ttu-id="d4b6c-135">DbRefExpression</span><span class="sxs-lookup"><span data-stu-id="d4b6c-135">DbRefExpression</span></span>

- <span data-ttu-id="d4b6c-136">DbRelationshipNavigationExpression</span><span class="sxs-lookup"><span data-stu-id="d4b6c-136">DbRelationshipNavigationExpression</span></span>

- <span data-ttu-id="d4b6c-137">DbTreatExpression</span><span class="sxs-lookup"><span data-stu-id="d4b6c-137">DbTreatExpression</span></span>

### <a name="expression-restrictions-and-notes"></a><span data-ttu-id="d4b6c-138">Ограничения выражений и примечания</span><span class="sxs-lookup"><span data-stu-id="d4b6c-138">Expression Restrictions and Notes</span></span>

<span data-ttu-id="d4b6c-139">В деревьях выходных команд запроса многие выражения могут использоваться только в ограниченном виде.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-139">Many expressions can only be used in a restricted manner in output query command trees:</span></span>

#### <a name="dbfunctionexpression"></a><span data-ttu-id="d4b6c-140">DbFunctionExpression</span><span class="sxs-lookup"><span data-stu-id="d4b6c-140">DbFunctionExpression</span></span>

<span data-ttu-id="d4b6c-141">Могут передаваться следующие типы функций:</span><span class="sxs-lookup"><span data-stu-id="d4b6c-141">The following function types can be passed:</span></span>

- <span data-ttu-id="d4b6c-142">Канонические функции, распознаваемые в пространстве имен Edm.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-142">Canonical functions that are recognized by the Edm namespace.</span></span>

- <span data-ttu-id="d4b6c-143">Встроенные функции (хранилища), которые распознаются BuiltInAttribute.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-143">Built-in (store) functions that are recognized by the BuiltInAttribute.</span></span>

- <span data-ttu-id="d4b6c-144">Определяемые пользователем функции.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-144">User-defined functions.</span></span>

<span data-ttu-id="d4b6c-145">Канонические функции (см. в разделе [канонические функции](../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) подробнее) указываются как часть [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], а поставщики должны предоставлять реализации для канонических функций на основе этих спецификаций.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-145">Canonical functions (see [Canonical Functions](../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) for more information) are specified as part of the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], and providers should supply implementations for canonical functions based on those specifications.</span></span> <span data-ttu-id="d4b6c-146">Функции хранилища основаны на спецификациях из соответствующего манифеста поставщика.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-146">Store functions are based on the specifications in the corresponding provider manifest.</span></span> <span data-ttu-id="d4b6c-147">Определяемые пользователем функции основаны на спецификациях из языка SSDL.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-147">User defined functions are based on specifications in the SSDL.</span></span>

<span data-ttu-id="d4b6c-148">Кроме того, функции с атрибутом NiladicFunction не имеют аргументов и должны преобразовываться без круглой скобки в конце.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-148">Also, functions having the NiladicFunction attribute have no arguments and should be translated without the parenthesis at the end.</span></span>  <span data-ttu-id="d4b6c-149">То есть,  *\<functionName >* вместо  *\<functionName > ()*.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-149">That is, to *\<functionName>* instead of *\<functionName>()*.</span></span>

#### <a name="dbnewinstanceexpression"></a><span data-ttu-id="d4b6c-150">DbNewInstanceExpression</span><span class="sxs-lookup"><span data-stu-id="d4b6c-150">DbNewInstanceExpression</span></span>

<span data-ttu-id="d4b6c-151">Выражение DbNewInstanceExpression может встречаться только в следующих двух случаях.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-151">DbNewInstanceExpression can only occur in the following two cases:</span></span>

- <span data-ttu-id="d4b6c-152">Как свойство Projection объекта DbProjectExpression.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-152">As the Projection property of DbProjectExpression.</span></span>  <span data-ttu-id="d4b6c-153">При его использовании в этом качестве виде применяются следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-153">When used as such the following restrictions apply:</span></span>

  - <span data-ttu-id="d4b6c-154">Тип результата должен быть типом строки.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-154">The result type must be a row type.</span></span>

  - <span data-ttu-id="d4b6c-155">Каждый из его аргументов представляет собой выражение, которое формирует результат с примитивным типом.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-155">Each of its arguments is an expression that produces a result with a primitive type.</span></span> <span data-ttu-id="d4b6c-156">Как правило, каждый аргумент является скалярным выражением, таким как PropertyExpression на основе DbVariableReferenceExpression, вызовом функции или арифметическим вычислением DbPropertyExpression на основе DbVariableReferenceExpression или вызова функции.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-156">Typically, each argument is a scalar expression, like a PropertyExpression over a DbVariableReferenceExpression, a function invocation, or an arithmetic computation of the DbPropertyExpression over a DbVariableReferenceExpression or a function invocation.</span></span> <span data-ttu-id="d4b6c-157">Однако выражение, представляющее скалярный вложенный запрос, может также встретиться в списке аргументов для выражения DbNewInstanceExpression.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-157">However, an expression representing a scalar subquery can also occur in the list of arguments for a DbNewInstanceExpression.</span></span> <span data-ttu-id="d4b6c-158">Выражение, представляющее скалярный вложенный запрос — это дерево выражения, которое представляет вложенный запрос, который возвращает только одну строку и один столбец типа-примитива с корнем объекта DbElementExpression</span><span class="sxs-lookup"><span data-stu-id="d4b6c-158">An expression that represents a scalar subquery is an expression tree that represents a subquery that returns exactly one row and one column of a primitive type with a DbElementExpression object root</span></span>

- <span data-ttu-id="d4b6c-159">С типом возвращаемого значения коллекции, и в этом случае он определяет новую коллекцию выражений, предоставленных как аргументы.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-159">With a collection return type, in which case it defines a new collection of the expressions provided as arguments.</span></span>

#### <a name="dbvariablereferenceexpression"></a><span data-ttu-id="d4b6c-160">DbVariableReferenceExpression</span><span class="sxs-lookup"><span data-stu-id="d4b6c-160">DbVariableReferenceExpression</span></span>

<span data-ttu-id="d4b6c-161">Выражение DbVariableReferenceExpression должно быть дочерним элементом узла DbPropertyExpression.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-161">A DbVariableReferenceExpression has to be a child of DbPropertyExpression node.</span></span>

#### <a name="dbgroupbyexpression"></a><span data-ttu-id="d4b6c-162">DbGroupByExpression</span><span class="sxs-lookup"><span data-stu-id="d4b6c-162">DbGroupByExpression</span></span>

<span data-ttu-id="d4b6c-163">Свойство Aggregates выражения DbGroupByExpression может иметь только элементы типа DbFunctionAggregate.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-163">The Aggregates property of a DbGroupByExpression can only have elements of type DbFunctionAggregate.</span></span> <span data-ttu-id="d4b6c-164">Никакие прочие типы агрегатов не предусмотрены.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-164">There are no other aggregate types.</span></span>

#### <a name="dblimitexpression"></a><span data-ttu-id="d4b6c-165">DbLimitExpression</span><span class="sxs-lookup"><span data-stu-id="d4b6c-165">DbLimitExpression</span></span>

<span data-ttu-id="d4b6c-166">Значением свойства Limit может быть только DbConstantExpression или DbParameterReferenceExpression.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-166">The property Limit can only be a DbConstantExpression or a DbParameterReferenceExpression.</span></span> <span data-ttu-id="d4b6c-167">Кроме того, начиная с версии 3.5 платформы .NET Framework, свойство WithTies всегда имеет значение false.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-167">Also property WithTies is always false as of version 3.5 of the .NET Framework.</span></span>

#### <a name="dbscanexpression"></a><span data-ttu-id="d4b6c-168">DbScanExpression</span><span class="sxs-lookup"><span data-stu-id="d4b6c-168">DbScanExpression</span></span>

<span data-ttu-id="d4b6c-169">При использовании в деревьях выходных команд выражение DbScanExpression фактически представляет проверку через таблицу, представление или запрос хранилища, представленный EntitySetBase::Target.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-169">When used in output command trees, the DbScanExpression effectively represents a scan over a table, a view, or a store query, represented by EntitySetBase::Target.</span></span>

<span data-ttu-id="d4b6c-170">Если свойство метаданных «Defining Query» цели не равно null, то он представляет запрос, текст запроса, для которого предоставляется в этом свойстве метаданных поставщика конкретного языка (или диалекте), как указано в определении схемы хранилища.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-170">If the metadata property "Defining Query" of the target is non-null, then it represents a query, the query text for which is provided in that metadata property in the provider’s specific language (or dialect) as specified in the store schema definition.</span></span>

<span data-ttu-id="d4b6c-171">В противном случае цель представляет таблицу или представление.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-171">Otherwise, the target represents a table or a view.</span></span> <span data-ttu-id="d4b6c-172">Его префиксом схемы находится либо в свойство метаданных «Schema», в противном случае значение null, в противном случае является именем контейнера сущностей.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-172">Its schema prefix is either in the "Schema" metadata property, if not null, otherwise is the entity container name.</span></span>  <span data-ttu-id="d4b6c-173">Имя таблицы или представления является либо свойство метаданных «Table», если не null, в противном случае свойство Name сущности задать базовый.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-173">The table or view name is either the "Table" metadata property, if not null, otherwise the Name property of the entity set base.</span></span>

<span data-ttu-id="d4b6c-174">Все эти свойства происходят из определения соответствующего набора EntitySet, которое приведено в файле SSDL.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-174">All these properties originate from the definition of the corresponding EntitySet in the store schema definition file (the SSDL).</span></span>

### <a name="using-primitive-types"></a><span data-ttu-id="d4b6c-175">Использование примитивных типов</span><span class="sxs-lookup"><span data-stu-id="d4b6c-175">Using Primitive Types</span></span>

<span data-ttu-id="d4b6c-176">Если в деревьях выходных команд имеются ссылки на примитивные типы, они, как правило, упоминаются в примитивных типах концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-176">When primitive types are referenced in output command trees, they are typically referenced in the conceptual model's primitive types.</span></span> <span data-ttu-id="d4b6c-177">Однако, применительно к определенным выражениям, поставщикам требуется соответствующий примитивный тип хранилища.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-177">However, for certain expressions, providers need the corresponding store primitive type.</span></span> <span data-ttu-id="d4b6c-178">Примеры таких выражений включают DbCastExpression и, возможно, DbNullExpression, если поставщик должен привести значение NULL к соответствующему типу.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-178">Examples of such expressions include DbCastExpression and possibly DbNullExpression, if the provider needs to cast the null to the corresponding type.</span></span> <span data-ttu-id="d4b6c-179">В этих случаях поставщики должны выполнить сопоставление с типом поставщика с учетом разновидности примитивного типа и его аспектов.</span><span class="sxs-lookup"><span data-stu-id="d4b6c-179">In these cases, providers should do the mapping to the provider type based on the primitive type kind and its facets.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4b6c-180">См. также</span><span class="sxs-lookup"><span data-stu-id="d4b6c-180">See also</span></span>

- [<span data-ttu-id="d4b6c-181">Создание SQL</span><span class="sxs-lookup"><span data-stu-id="d4b6c-181">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
