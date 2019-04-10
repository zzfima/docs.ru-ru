---
title: Практическое руководство. Как генерировать настраиваемый код путем изменения DBML-файла
ms.date: 03/30/2017
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
ms.openlocfilehash: c3fa4d9db4076309ab7d6066cc7072797eaead54
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59338427"
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a><span data-ttu-id="00da7-102">Практическое руководство. Как генерировать настраиваемый код путем изменения DBML-файла</span><span class="sxs-lookup"><span data-stu-id="00da7-102">How to: Generate Customized Code by Modifying a DBML File</span></span>
<span data-ttu-id="00da7-103">Вы можете создать Visual Basic или C# исходный код из файла метаданных DBML-разметки базы данных.</span><span class="sxs-lookup"><span data-stu-id="00da7-103">You can generate Visual Basic or C# source code from a database markup language (.dbml) metadata file.</span></span> <span data-ttu-id="00da7-104">Этот способ предоставляет возможность настройки заданного по умолчанию DBML-файла до создания кода сопоставления приложений.</span><span class="sxs-lookup"><span data-stu-id="00da7-104">This approach provides an opportunity to customize the default .dbml file before you generate the application mapping code.</span></span> <span data-ttu-id="00da7-105">Данная возможность является дополнительной.</span><span class="sxs-lookup"><span data-stu-id="00da7-105">This is an advanced feature.</span></span>  
  
 <span data-ttu-id="00da7-106">Ниже указаны действия, необходимые для выполнения данного процесса.</span><span class="sxs-lookup"><span data-stu-id="00da7-106">The steps in this process are as follows:</span></span>  
  
1. <span data-ttu-id="00da7-107">Создайте DBML-файл.</span><span class="sxs-lookup"><span data-stu-id="00da7-107">Generate a .dbml file.</span></span>  
  
2. <span data-ttu-id="00da7-108">Для изменения DBML-файла используйте редактор.</span><span class="sxs-lookup"><span data-stu-id="00da7-108">Use an editor to modify the .dbml file.</span></span> <span data-ttu-id="00da7-109">Обратите внимание, что DBML-файл проверен на соответствие файлу определения схемы (XSD) для [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] DBML-файлы.</span><span class="sxs-lookup"><span data-stu-id="00da7-109">Note that the .dbml file must validate against the schema definition (.xsd) file for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .dbml files.</span></span> <span data-ttu-id="00da7-110">Дополнительные сведения см. в разделе [создание кода в LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="00da7-110">For more information, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
3. <span data-ttu-id="00da7-111">Создать в Visual Basic или C# исходный код.</span><span class="sxs-lookup"><span data-stu-id="00da7-111">Generate the Visual Basic or C# source code.</span></span>  
  
 <span data-ttu-id="00da7-112">В следующих примерах используется средства командной строки SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="00da7-112">The following examples use the SQLMetal command-line tool.</span></span> <span data-ttu-id="00da7-113">Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="00da7-113">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="00da7-114">Пример</span><span class="sxs-lookup"><span data-stu-id="00da7-114">Example</span></span>  
 <span data-ttu-id="00da7-115">В следующем коде DBML-файл создается из учебной базы данных "Northwind".</span><span class="sxs-lookup"><span data-stu-id="00da7-115">The following code generates a .dbml file from the Northwind sample database.</span></span> <span data-ttu-id="00da7-116">В качестве источника метаданных база данных можно использовать либо имя базы данных, либо имя MDF-файла.</span><span class="sxs-lookup"><span data-stu-id="00da7-116">As source for the database metadata, you can use either the name of the database or the name of the .mdf file.</span></span>  
  
```  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a><span data-ttu-id="00da7-117">Пример</span><span class="sxs-lookup"><span data-stu-id="00da7-117">Example</span></span>  
 <span data-ttu-id="00da7-118">Следующий код приводит к возникновению ошибки Visual Basic или C# файл исходного кода из DBML-файла.</span><span class="sxs-lookup"><span data-stu-id="00da7-118">The following code generates Visual Basic or C# source code file from a .dbml file.</span></span>  
  
```  
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a><span data-ttu-id="00da7-119">См. также</span><span class="sxs-lookup"><span data-stu-id="00da7-119">See also</span></span>

- [<span data-ttu-id="00da7-120">Создание кода в LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="00da7-120">Code Generation in LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="00da7-121">SqlMetal.exe (средство создания кода)</span><span class="sxs-lookup"><span data-stu-id="00da7-121">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)
- [<span data-ttu-id="00da7-122">Создание модели объектов</span><span class="sxs-lookup"><span data-stu-id="00da7-122">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
