---
title: Пошаговое руководство. Простая модель объекта и запрос (Visual Basic)
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: c878e457-f715-46e4-a136-ff14d6c86018
ms.openlocfilehash: a7d278dd424fbb3167a30d627379f78d0c65476f
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971786"
---
# <a name="walkthrough-simple-object-model-and-query-visual-basic"></a><span data-ttu-id="1f285-102">Пошаговое руководство. Простая модель объекта и запрос (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f285-102">Walkthrough: Simple Object Model and Query (Visual Basic)</span></span>

<span data-ttu-id="1f285-103">В данном пошаговом руководстве представлен основной и полный сценарий [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] с подробным объяснением выполняемых действий.</span><span class="sxs-lookup"><span data-stu-id="1f285-103">This walkthrough provides a fundamental end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario with minimal complexities.</span></span> <span data-ttu-id="1f285-104">В нем создается класс сущностей, который моделирует таблицу Customers в учебной базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="1f285-104">You will create an entity class that models the Customers table in the sample Northwind database.</span></span> <span data-ttu-id="1f285-105">После этого создается простой запрос на получение списка клиентов, находящихся в Лондоне.</span><span class="sxs-lookup"><span data-stu-id="1f285-105">You will then create a simple query to list customers who are located in London.</span></span>

<span data-ttu-id="1f285-106">Данное руководство ориентировано на создание кода, чтобы продемонстрировать основные понятия технологии [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f285-106">This walkthrough is code-oriented by design to help show [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] concepts.</span></span> <span data-ttu-id="1f285-107">Как правило, для создания объектной модели следует использовать реляционный конструктор объектов.</span><span class="sxs-lookup"><span data-stu-id="1f285-107">Normally speaking, you would use the Object Relational Designer to create your object model.</span></span>

[!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]

<span data-ttu-id="1f285-108">Это пошаговое руководство было написано с помощью параметров разработки Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1f285-108">This walkthrough was written by using Visual Basic Development Settings.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1f285-109">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="1f285-109">Prerequisites</span></span>

- <span data-ttu-id="1f285-110">Для хранения файлов используется выделенная папка ("c:\linqtest").</span><span class="sxs-lookup"><span data-stu-id="1f285-110">This walkthrough uses a dedicated folder ("c:\linqtest") to hold files.</span></span> <span data-ttu-id="1f285-111">Прежде чем приступить к выполнению задач, создайте такую папку.</span><span class="sxs-lookup"><span data-stu-id="1f285-111">Create this folder before you begin the walkthrough.</span></span>

- <span data-ttu-id="1f285-112">В данном пошаговом руководстве требуется доступ к учебной базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="1f285-112">This walkthrough requires the Northwind sample database.</span></span> <span data-ttu-id="1f285-113">Если база данных не установлена на компьютере разработчика, загрузите ее с веб-узла Центра загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1f285-113">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="1f285-114">Инструкции см. в разделе [Загрузка образцов баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="1f285-114">For instructions, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span> <span data-ttu-id="1f285-115">После загрузки базы данных скопируйте полученный файл в папку c:\linqtest.</span><span class="sxs-lookup"><span data-stu-id="1f285-115">After you have downloaded the database, copy the file to the c:\linqtest folder.</span></span>

## <a name="overview"></a><span data-ttu-id="1f285-116">Обзор</span><span class="sxs-lookup"><span data-stu-id="1f285-116">Overview</span></span>

<span data-ttu-id="1f285-117">Данное пошаговое руководство состоит из шести основных задач.</span><span class="sxs-lookup"><span data-stu-id="1f285-117">This walkthrough consists of six main tasks:</span></span>

- <span data-ttu-id="1f285-118">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Создание решения в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1f285-118">Creating a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>

- <span data-ttu-id="1f285-119">Сопоставление класса с таблицей базы данных.</span><span class="sxs-lookup"><span data-stu-id="1f285-119">Mapping a class to a database table.</span></span>

- <span data-ttu-id="1f285-120">Назначение свойств классу для представления столбцов базы данных.</span><span class="sxs-lookup"><span data-stu-id="1f285-120">Designating properties on the class to represent database columns.</span></span>

- <span data-ttu-id="1f285-121">Указание подключения к базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="1f285-121">Specifying the connection to the Northwind database.</span></span>

- <span data-ttu-id="1f285-122">Создание простого запроса к базе данных.</span><span class="sxs-lookup"><span data-stu-id="1f285-122">Creating a simple query to run against the database.</span></span>

- <span data-ttu-id="1f285-123">Выполнение запроса и просмотр результатов.</span><span class="sxs-lookup"><span data-stu-id="1f285-123">Executing the query and observing the results.</span></span>

## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="1f285-124">Создание решения LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="1f285-124">Creating a LINQ to SQL Solution</span></span>

<span data-ttu-id="1f285-125">В этой первой задаче вы создадите решение Visual Studio, содержащее необходимые ссылки для сборки и запуска [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] проекта.</span><span class="sxs-lookup"><span data-stu-id="1f285-125">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>

### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="1f285-126">Создание решения LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="1f285-126">To create a LINQ to SQL solution</span></span>

1. <span data-ttu-id="1f285-127">В меню **Файл** выберите пункт **Создать проект**.</span><span class="sxs-lookup"><span data-stu-id="1f285-127">On the **File** menu, click **New Project**.</span></span>

2. <span data-ttu-id="1f285-128">На панели **типы проектов** диалогового окна **Новый проект** нажмите кнопку **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="1f285-128">In the **Project types** pane of the **New Project** dialog box, click **Visual Basic**.</span></span>

3. <span data-ttu-id="1f285-129">В области **Шаблоны** щелкните **Консольное приложение**.</span><span class="sxs-lookup"><span data-stu-id="1f285-129">In the **Templates** pane, click **Console Application**.</span></span>

4. <span data-ttu-id="1f285-130">В поле **имя** введите **линкконсолеапп**.</span><span class="sxs-lookup"><span data-stu-id="1f285-130">In the **Name** box, type **LinqConsoleApp**.</span></span>

5. <span data-ttu-id="1f285-131">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1f285-131">Click **OK**.</span></span>

## <a name="adding-linq-references-and-directives"></a><span data-ttu-id="1f285-132">Добавление ссылок и директив LINQ</span><span class="sxs-lookup"><span data-stu-id="1f285-132">Adding LINQ References and Directives</span></span>

<span data-ttu-id="1f285-133">В этом пошаговом руководстве используются сборки, которые могут быть не установлены по умолчанию в проект.</span><span class="sxs-lookup"><span data-stu-id="1f285-133">This walkthrough uses assemblies that might not be installed by default in your project.</span></span> <span data-ttu-id="1f285-134">Если `System.Data.Linq` в проекте нет списка (щелкните **Показывать все файлы** в **Обозреватель решений** и разверните узел **ссылки** ), добавьте его, как описано в следующих шагах.</span><span class="sxs-lookup"><span data-stu-id="1f285-134">If `System.Data.Linq` is not listed as a reference in your project (click **Show All Files** in **Solution Explorer** and expand the **References** node), add it, as explained in the following steps.</span></span>

### <a name="to-add-systemdatalinq"></a><span data-ttu-id="1f285-135">Добавление сборки System.Data.Linq</span><span class="sxs-lookup"><span data-stu-id="1f285-135">To add System.Data.Linq</span></span>

1. <span data-ttu-id="1f285-136">В **Обозреватель решений**щелкните правой кнопкой мыши элемент **ссылки**и выберите команду **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="1f285-136">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>

2. <span data-ttu-id="1f285-137">В диалоговом окне **Добавление ссылки** щелкните **.NET**, выберите сборку System. Data. LINQ и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1f285-137">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>

     <span data-ttu-id="1f285-138">Сборка будет добавлена в проект.</span><span class="sxs-lookup"><span data-stu-id="1f285-138">The assembly is added to the project.</span></span>

3. <span data-ttu-id="1f285-139">Кроме того, в диалоговом окне **Добавление ссылки** щелкните **.NET**, прокрутите до и щелкните System. Windows. Forms, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1f285-139">Also in the **Add Reference** dialog box, click **.NET**, scroll to and click System.Windows.Forms, and then click **OK**.</span></span>

     <span data-ttu-id="1f285-140">Эта сборка, которая поддерживает окно сообщений в данном пошаговом руководстве, будет добавлена в проект.</span><span class="sxs-lookup"><span data-stu-id="1f285-140">This assembly, which supports the message box in the walkthrough, is added to the project.</span></span>

4. <span data-ttu-id="1f285-141">Добавьте следующие директивы перед `Module1`.</span><span class="sxs-lookup"><span data-stu-id="1f285-141">Add the following directives above `Module1`:</span></span>

     [!code-vb[DLinqWalk1VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#1)]

## <a name="mapping-a-class-to-a-database-table"></a><span data-ttu-id="1f285-142">Сопоставление класса с таблицей базы данных</span><span class="sxs-lookup"><span data-stu-id="1f285-142">Mapping a Class to a Database Table</span></span>

<span data-ttu-id="1f285-143">На этом этапе создается класс, который сопоставляется с таблицей базы данных.</span><span class="sxs-lookup"><span data-stu-id="1f285-143">In this step, you create a class and map it to a database table.</span></span> <span data-ttu-id="1f285-144">Такой класс называется классом сущностей.</span><span class="sxs-lookup"><span data-stu-id="1f285-144">Such a class is termed an *entity class*.</span></span> <span data-ttu-id="1f285-145">Обратите внимание, что сопоставление осуществляется простым добавлением атрибута <xref:System.Data.Linq.Mapping.TableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="1f285-145">Note that the mapping is accomplished by just adding the <xref:System.Data.Linq.Mapping.TableAttribute> attribute.</span></span> <span data-ttu-id="1f285-146">Свойство <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> задает имя таблицы в базе данных.</span><span class="sxs-lookup"><span data-stu-id="1f285-146">The <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property specifies the name of the table in the database.</span></span>

### <a name="to-create-an-entity-class-and-map-it-to-a-database-table"></a><span data-ttu-id="1f285-147">Создание класса сущностей и его сопоставление с таблицей базы данных</span><span class="sxs-lookup"><span data-stu-id="1f285-147">To create an entity class and map it to a database table</span></span>

- <span data-ttu-id="1f285-148">Введите или вставьте следующий код в файл Module1.vb непосредственно перед методом `Sub Main`.</span><span class="sxs-lookup"><span data-stu-id="1f285-148">Type or paste the following code into Module1.vb immediately above `Sub Main`:</span></span>

     [!code-vb[DLinqWalk1VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#2)]

## <a name="designating-properties-on-the-class-to-represent-database-columns"></a><span data-ttu-id="1f285-149">Назначение свойств классу для представления столбцов базы данных.</span><span class="sxs-lookup"><span data-stu-id="1f285-149">Designating Properties on the Class to Represent Database Columns</span></span>

<span data-ttu-id="1f285-150">На этом этапе выполняется несколько задач.</span><span class="sxs-lookup"><span data-stu-id="1f285-150">In this step, you accomplish several tasks.</span></span>

- <span data-ttu-id="1f285-151">Используется атрибут <xref:System.Data.Linq.Mapping.ColumnAttribute> для назначения классу сущностей свойств `CustomerID` и `City`, представляющих столбцы в таблице базы данных.</span><span class="sxs-lookup"><span data-stu-id="1f285-151">You use the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate `CustomerID` and `City` properties on the entity class as representing columns in the database table.</span></span>

- <span data-ttu-id="1f285-152">Назначается свойство `CustomerID`, представляющее столбец первичного ключа в базе данных.</span><span class="sxs-lookup"><span data-stu-id="1f285-152">You designate the `CustomerID` property as representing a primary key column in the database.</span></span>

- <span data-ttu-id="1f285-153">Назначаются поля `_CustomerID` и `_City` для закрытого хранения.</span><span class="sxs-lookup"><span data-stu-id="1f285-153">You designate `_CustomerID` and `_City` fields for private storage.</span></span> <span data-ttu-id="1f285-154">После этого [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] сможет напрямую сохранять и извлекать значения, вместо вызова открытых методов доступа, которые могут содержать бизнес-логику.</span><span class="sxs-lookup"><span data-stu-id="1f285-154">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can then store and retrieve values directly, instead of using public accessors that might include business logic.</span></span>

### <a name="to-represent-characteristics-of-two-database-columns"></a><span data-ttu-id="1f285-155">Представление характеристик двух столбцов базы данных</span><span class="sxs-lookup"><span data-stu-id="1f285-155">To represent characteristics of two database columns</span></span>

- <span data-ttu-id="1f285-156">Введите или вставьте следующий код в файл Module1.vb непосредственно перед методом `End Class`.</span><span class="sxs-lookup"><span data-stu-id="1f285-156">Type or paste the following code into Module1.vb just before `End Class`:</span></span>

     [!code-vb[DLinqWalk1VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#3)]

## <a name="specifying-the-connection-to-the-northwind-database"></a><span data-ttu-id="1f285-157">Указание подключения к базе данных Northwind</span><span class="sxs-lookup"><span data-stu-id="1f285-157">Specifying the Connection to the Northwind Database</span></span>

<span data-ttu-id="1f285-158">На этом этапе для установки подключения между основанными на коде структурами данных и самой базой данных используется объект <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="1f285-158">In this step you use a <xref:System.Data.Linq.DataContext> object to establish a connection between your code-based data structures and the database itself.</span></span> <span data-ttu-id="1f285-159">Основным каналом, через который извлекаются объекты из базы данных и отправляются изменения, является класс <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="1f285-159">The <xref:System.Data.Linq.DataContext> is the main channel through which you retrieve objects from the database and submit changes.</span></span>

<span data-ttu-id="1f285-160">Также объявляется объект `Table(Of Customer)`, который действует как логическая типизированная таблица для запросов к таблице Customers в базе данных.</span><span class="sxs-lookup"><span data-stu-id="1f285-160">You also declare a `Table(Of Customer)` to act as the logical, typed table for your queries against the Customers table in the database.</span></span> <span data-ttu-id="1f285-161">Эти запросы создаются и выполняются в последующих действиях.</span><span class="sxs-lookup"><span data-stu-id="1f285-161">You will create and execute these queries in later steps.</span></span>

### <a name="to-specify-the-database-connection"></a><span data-ttu-id="1f285-162">Указание подключения к базе данных</span><span class="sxs-lookup"><span data-stu-id="1f285-162">To specify the database connection</span></span>

- <span data-ttu-id="1f285-163">Введите или вставьте следующий код в метод `Sub Main`.</span><span class="sxs-lookup"><span data-stu-id="1f285-163">Type or paste the following code into the `Sub Main` method.</span></span>

     <span data-ttu-id="1f285-164">Обратите внимание: предполагается, что файл `northwnd.mdf` находится в папке "linqtest".</span><span class="sxs-lookup"><span data-stu-id="1f285-164">Note that the `northwnd.mdf` file is assumed to be in the linqtest folder.</span></span> <span data-ttu-id="1f285-165">Дополнительные сведения см. в разделе "Предварительные требования" ранее в этом руководстве.</span><span class="sxs-lookup"><span data-stu-id="1f285-165">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>

     [!code-vb[DLinqWalk1VB#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#4)]

## <a name="creating-a-simple-query"></a><span data-ttu-id="1f285-166">Создание простого запроса</span><span class="sxs-lookup"><span data-stu-id="1f285-166">Creating a Simple Query</span></span>

<span data-ttu-id="1f285-167">На этом этапе создается запрос для поиска клиентов из таблицы Customers базы данных, находящихся в Лондоне.</span><span class="sxs-lookup"><span data-stu-id="1f285-167">In this step, you create a query to find which customers in the database Customers table are located in London.</span></span> <span data-ttu-id="1f285-168">Код запроса, создаваемый на этом шаге, только описывает запрос.</span><span class="sxs-lookup"><span data-stu-id="1f285-168">The query code in this step just describes the query.</span></span> <span data-ttu-id="1f285-169">но не выполняет его.</span><span class="sxs-lookup"><span data-stu-id="1f285-169">It does not execute it.</span></span> <span data-ttu-id="1f285-170">Этот подход называется отложенным *выполнением*.</span><span class="sxs-lookup"><span data-stu-id="1f285-170">This approach is known as *deferred execution*.</span></span> <span data-ttu-id="1f285-171">Дополнительные сведения см. в разделе [Введение в запросы LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="1f285-171">For more information, see [Introduction to LINQ Queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>

<span data-ttu-id="1f285-172">Можно также записать выходные данные в журнал, чтобы продемонстрировать команды SQL, создаваемые технологией [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f285-172">You will also produce a log output to show the SQL commands that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates.</span></span> <span data-ttu-id="1f285-173">Возможность ведения журнала (которая использует метод <xref:System.Data.Linq.DataContext.Log%2A>) очень полезна при отладке, а также при проверке того, что команды, отправляемые в базу данных, точно соответствуют запросу.</span><span class="sxs-lookup"><span data-stu-id="1f285-173">This logging feature (which uses <xref:System.Data.Linq.DataContext.Log%2A>) is helpful in debugging, and in determining that the commands being sent to the database accurately represent your query.</span></span>

### <a name="to-create-a-simple-query"></a><span data-ttu-id="1f285-174">Создание простого запроса</span><span class="sxs-lookup"><span data-stu-id="1f285-174">To create a simple query</span></span>

- <span data-ttu-id="1f285-175">Введите или вставьте следующий код в метод `Sub Main` после объявления `Table(Of Customer)`.</span><span class="sxs-lookup"><span data-stu-id="1f285-175">Type or paste the following code into the `Sub Main` method after the `Table(Of Customer)` declaration:</span></span>

     [!code-vb[DLinqWalk1AVB#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1AVB/vb/Module1.vb#5)]

## <a name="executing-the-query"></a><span data-ttu-id="1f285-176">Выполнение запроса</span><span class="sxs-lookup"><span data-stu-id="1f285-176">Executing the Query</span></span>

<span data-ttu-id="1f285-177">На этом шаге производится фактическое выполнение запроса.</span><span class="sxs-lookup"><span data-stu-id="1f285-177">In this step, you actually execute the query.</span></span> <span data-ttu-id="1f285-178">Выражения запроса, созданные на предыдущем этапе, не оцениваются до тех пор, пока не понадобятся результаты.</span><span class="sxs-lookup"><span data-stu-id="1f285-178">The query expressions you created in the previous steps are not evaluated until the results are needed.</span></span> <span data-ttu-id="1f285-179">После начала итерации `For Each` выполняется команда SQL для базы данных и материализуются объекты.</span><span class="sxs-lookup"><span data-stu-id="1f285-179">When you begin the `For Each` iteration, a SQL command is executed against the database and objects are materialized.</span></span>

### <a name="to-execute-the-query"></a><span data-ttu-id="1f285-180">Порядок выполнения запроса</span><span class="sxs-lookup"><span data-stu-id="1f285-180">To execute the query</span></span>

1. <span data-ttu-id="1f285-181">Введите или вставьте следующий код в конце метода `Sub Main` (после описания запроса).</span><span class="sxs-lookup"><span data-stu-id="1f285-181">Type or paste the following code at the end of the `Sub Main` method (after the query description):</span></span>

     [!code-vb[DLinqWalk1AVB#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1AVB/vb/Module1.vb#6)]

2. <span data-ttu-id="1f285-182">Нажмите клавишу F5, чтобы начать отладку приложения.</span><span class="sxs-lookup"><span data-stu-id="1f285-182">Press F5 to debug the application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1f285-183">Если приложение создает ошибку во время выполнения, см. пошаговые [руководства](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)в разделе Устранение неполадок.</span><span class="sxs-lookup"><span data-stu-id="1f285-183">If your application generates a run-time error, see the Troubleshooting section of [Learning by Walkthroughs](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).</span></span>

     <span data-ttu-id="1f285-184">В окне сообщения отображается список из шести клиентов.</span><span class="sxs-lookup"><span data-stu-id="1f285-184">The message box displays a list of six customers.</span></span> <span data-ttu-id="1f285-185">В окне консоли отображается созданный код SQL.</span><span class="sxs-lookup"><span data-stu-id="1f285-185">The Console window displays the generated SQL code.</span></span>

3. <span data-ttu-id="1f285-186">Нажмите кнопку **ОК**, чтобы закрыть окно сообщения.</span><span class="sxs-lookup"><span data-stu-id="1f285-186">Click **OK** to dismiss the message box.</span></span>

     <span data-ttu-id="1f285-187">Приложение закрывается.</span><span class="sxs-lookup"><span data-stu-id="1f285-187">The application closes.</span></span>

4. <span data-ttu-id="1f285-188">В меню **Файл** выберите команду **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="1f285-188">On the **File** menu, click **Save All**.</span></span>

     <span data-ttu-id="1f285-189">Это приложение потребуется при выполнении следующего пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="1f285-189">You will need this application if you continue with the next walkthrough.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1f285-190">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="1f285-190">Next Steps</span></span>

<span data-ttu-id="1f285-191">В [этом пошаговом руководстве: В разделе "запросы по связям"](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-visual-basic.md) (Visual Basic) продолжение этого руководства завершается.</span><span class="sxs-lookup"><span data-stu-id="1f285-191">The [Walkthrough: Querying Across Relationships (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-visual-basic.md) topic continues where this walkthrough ends.</span></span> <span data-ttu-id="1f285-192">В пошаговом руководстве «запросы между [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] связями» показано, как можно выполнять запросы *к* нескольким таблицам, как и к объединениям в реляционной базе данных.</span><span class="sxs-lookup"><span data-stu-id="1f285-192">The Querying Across Relationships walkthrough demonstrates how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can query across tables, similar to *joins* in a relational database.</span></span>

<span data-ttu-id="1f285-193">Если требуется выполнить пошаговое руководство "Выполнение запросов в связях", необходимо сохранить решение, созданное в процессе только что завершенного пошагового руководства. Это обязательное условие.</span><span class="sxs-lookup"><span data-stu-id="1f285-193">If you want to do the Querying Across Relationships walkthrough, make sure to save the solution for the walkthrough you have just completed, which is a prerequisite.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f285-194">См. также</span><span class="sxs-lookup"><span data-stu-id="1f285-194">See also</span></span>

- [<span data-ttu-id="1f285-195">Обучение с использованием пошаговых руководств</span><span class="sxs-lookup"><span data-stu-id="1f285-195">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
