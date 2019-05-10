---
title: Анализ исходного кода LINQ to SQL
ms.date: 03/30/2017
ms.assetid: cba3eef8-e108-4478-b588-ad59580e133e
ms.openlocfilehash: 35bc4988b8b9845ce6f45bab6849cd4b53a858ec
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592488"
---
# <a name="analyzing-linq-to-sql-source-code"></a><span data-ttu-id="dea6d-102">Анализ исходного кода LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="dea6d-102">Analyzing LINQ to SQL Source Code</span></span>
<span data-ttu-id="dea6d-103">С помощью описанных ниже действий можно создать исходный код [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] из учебной базы данных "Northwind".</span><span class="sxs-lookup"><span data-stu-id="dea6d-103">By using the following steps, you can produce [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] source code from the Northwind sample database.</span></span> <span data-ttu-id="dea6d-104">Чтобы лучше понять, как сопоставлены различные элементы, можно сравнить элементы модели объектов с элементами базы данных.</span><span class="sxs-lookup"><span data-stu-id="dea6d-104">You can compare elements of the object model with elements of the database to better see how different items are mapped.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dea6d-105">С помощью Visual Studio разработчики могут использовать [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] для создания этого кода.</span><span class="sxs-lookup"><span data-stu-id="dea6d-105">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] to produce this code.</span></span>  
  
1. <span data-ttu-id="dea6d-106">Если образец базы данных Northwind еще не установлен на компьютере разработчика, его можно загрузить бесплатно.</span><span class="sxs-lookup"><span data-stu-id="dea6d-106">If you do not already have the Northwind sample database on your development computer, you can download it free of charge.</span></span> <span data-ttu-id="dea6d-107">Дополнительные сведения см. в разделе [Загрузка примеров баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="dea6d-107">For more information, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
2. <span data-ttu-id="dea6d-108">Для создания файла с исходным кодом Visual Basic или C# используется программа командной строки SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="dea6d-108">Use the SqlMetal command-line tool to generate a Visual Basic or C# source file.</span></span> <span data-ttu-id="dea6d-109">Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="dea6d-109">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span> <span data-ttu-id="dea6d-110">Ниже показаны команды, которые необходимо ввести в командной строке для создания файлов с исходным кодом Visual Basic и C#, включающих хранимые процедуры и функции.</span><span class="sxs-lookup"><span data-stu-id="dea6d-110">By typing the following commands at a command prompt, you can generate Visual Basic and C# source files that include stored procedures and functions:</span></span>  
  
    - `sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
    - `sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
## <a name="see-also"></a><span data-ttu-id="dea6d-111">См. также</span><span class="sxs-lookup"><span data-stu-id="dea6d-111">See also</span></span>

- [<span data-ttu-id="dea6d-112">Ссылки</span><span class="sxs-lookup"><span data-stu-id="dea6d-112">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
- [<span data-ttu-id="dea6d-113">Основные сведения</span><span class="sxs-lookup"><span data-stu-id="dea6d-113">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
