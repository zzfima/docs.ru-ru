---
title: Практическое руководство. Создание модели объектов в Visual Basic или C#
ms.date: 03/30/2017
ms.assetid: a0c73b33-5650-420c-b9dc-f49310c201ee
ms.openlocfilehash: 7d2c0600534c93f5884eec48a4bdaa3ce99945e9
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002803"
---
# <a name="how-to-generate-the-object-model-in-visual-basic-or-c"></a><span data-ttu-id="69ca8-102">Как создать объектную модель в Visual Basic или C\#</span><span class="sxs-lookup"><span data-stu-id="69ca8-102">How to: Generate the Object Model in Visual Basic or C\#</span></span>
<span data-ttu-id="69ca8-103">В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] объектная модель используемого языка программирования сопоставляется с реляционной базой данных.</span><span class="sxs-lookup"><span data-stu-id="69ca8-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], an object model in your own programming language is mapped to a relational database.</span></span> <span data-ttu-id="69ca8-104">Доступны два средства для автоматического создания Visual Basic или C# модели из метаданных существующей базы данных.</span><span class="sxs-lookup"><span data-stu-id="69ca8-104">Two tools are available for automatically generating a Visual Basic or C# model from the metadata of an existing database.</span></span>  
  
- <span data-ttu-id="69ca8-105">При использовании Visual Studio можно использовать реляционный конструктор объектов для создания объектной модели.</span><span class="sxs-lookup"><span data-stu-id="69ca8-105">If you are using Visual Studio, you can use the Object Relational Designer to generate an object model.</span></span> <span data-ttu-id="69ca8-106">Реляционный конструктор объектов (R) предоставляет богатый пользовательский интерфейс, помогающий создать [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] объектную модель.</span><span class="sxs-lookup"><span data-stu-id="69ca8-106">The O/R Designer provides a rich user interface to help you generate a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="69ca8-107">Дополнительные сведения см. [в разделе средства LINQ to SQL в Visual Studio](https://docs.microsoft.com/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span><span class="sxs-lookup"><span data-stu-id="69ca8-107">For more information see, [Linq to SQL Tools in Visual Studio](https://docs.microsoft.com/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>
  
- <span data-ttu-id="69ca8-108">Средство командной строки SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="69ca8-108">The SQLMetal command-line tool.</span></span> <span data-ttu-id="69ca8-109">Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="69ca8-109">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="69ca8-110">Если существующие базы данных отсутствуют и необходимо создать базу данных из объектной модели, можно создать объектную модель с помощью редактора кода и метода <xref:System.Data.Linq.DataContext.CreateDatabase%2A>.</span><span class="sxs-lookup"><span data-stu-id="69ca8-110">If you do not have an existing database and want to create one from an object model, you can create your object model by using your code editor and <xref:System.Data.Linq.DataContext.CreateDatabase%2A>.</span></span> <span data-ttu-id="69ca8-111">Дополнительные сведения см. [в разделе инструкции. динамическое создание базы данных](how-to-dynamically-create-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="69ca8-111">For more information, see [How to: Dynamically Create a Database](how-to-dynamically-create-a-database.md).</span></span>  
  
 <span data-ttu-id="69ca8-112">Документация для реляционного конструктора объектов содержит примеры создания Visual Basic или C# объектной модели с помощью реляционного конструктора объектов (r).</span><span class="sxs-lookup"><span data-stu-id="69ca8-112">Documentation for the O/R Designer provides examples of how to generate a Visual Basic or C# object model by using the O/R Designer.</span></span> <span data-ttu-id="69ca8-113">Ниже приведены примеры использования программы командной строки SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="69ca8-113">The following information provide examples of how to use the SQLMetal command-line tool.</span></span> <span data-ttu-id="69ca8-114">Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="69ca8-114">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="69ca8-115">Пример</span><span class="sxs-lookup"><span data-stu-id="69ca8-115">Example</span></span>  
 <span data-ttu-id="69ca8-116">Командная строка SQLMetal, показанная в следующем примере, создает Visual Basic код в качестве объектной модели на основе атрибутов образца базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="69ca8-116">The SQLMetal command line shown in the following example produces Visual Basic code as the attribute-based object model of the Northwind sample database.</span></span> <span data-ttu-id="69ca8-117">Также отображаются хранимые процедуры и функции.</span><span class="sxs-lookup"><span data-stu-id="69ca8-117">Stored procedures and functions are also rendered.</span></span>  
  
```console  
sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions  
```  
  
## <a name="example"></a><span data-ttu-id="69ca8-118">Пример</span><span class="sxs-lookup"><span data-stu-id="69ca8-118">Example</span></span>  
 <span data-ttu-id="69ca8-119">С помощью команды программы SQLMetal, представленной в следующем примере, создается код C# для основанной на атрибутах объектной модели базы данных "Northwind".</span><span class="sxs-lookup"><span data-stu-id="69ca8-119">The SQLMetal command line shown in the following example produces C# code as the attribute-based object model of the Northwind sample database.</span></span> <span data-ttu-id="69ca8-120">Также отображаются хранимые процедуры и функции и имена таблиц автоматически преобразуются в имена во множественном числе.</span><span class="sxs-lookup"><span data-stu-id="69ca8-120">Stored procedures and functions are also rendered, and table names are automatically pluralized.</span></span>  
  
```console  
sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize  
```  
  
## <a name="see-also"></a><span data-ttu-id="69ca8-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="69ca8-121">See also</span></span>

- [<span data-ttu-id="69ca8-122">Руководство по программированию</span><span class="sxs-lookup"><span data-stu-id="69ca8-122">Programming Guide</span></span>](programming-guide.md)
- [<span data-ttu-id="69ca8-123">Модель объектов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="69ca8-123">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="69ca8-124">Обучение с использованием пошаговых руководств</span><span class="sxs-lookup"><span data-stu-id="69ca8-124">Learning by Walkthroughs</span></span>](learning-by-walkthroughs.md)
- [<span data-ttu-id="69ca8-125">Практическое руководство. Настройка классов сущностей с использованием редактора кода</span><span class="sxs-lookup"><span data-stu-id="69ca8-125">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
- [<span data-ttu-id="69ca8-126">Сопоставление, основанное на атрибутах</span><span class="sxs-lookup"><span data-stu-id="69ca8-126">Attribute-Based Mapping</span></span>](attribute-based-mapping.md)
- [<span data-ttu-id="69ca8-127">SqlMetal.exe (средство создания кода)</span><span class="sxs-lookup"><span data-stu-id="69ca8-127">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- [<span data-ttu-id="69ca8-128">Внешнее сопоставление</span><span class="sxs-lookup"><span data-stu-id="69ca8-128">External Mapping</span></span>](external-mapping.md)
- [<span data-ttu-id="69ca8-129">Загрузка примеров баз данных</span><span class="sxs-lookup"><span data-stu-id="69ca8-129">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="69ca8-130">Создание модели объектов</span><span class="sxs-lookup"><span data-stu-id="69ca8-130">Creating the Object Model</span></span>](creating-the-object-model.md)
