---
title: Практическое руководство. Как генерировать настраиваемый код путем изменения DBML-файла
ms.date: 03/30/2017
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
ms.openlocfilehash: 01890e6b899db6b70049e2d6b8193e5b0f4095fb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781979"
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a><span data-ttu-id="a6ba0-102">Практическое руководство. Как генерировать настраиваемый код путем изменения DBML-файла</span><span class="sxs-lookup"><span data-stu-id="a6ba0-102">How to: Generate Customized Code by Modifying a DBML File</span></span>
<span data-ttu-id="a6ba0-103">Visual Basic или C# исходный код можно создать из файла метаданных на языке разметки базы данных (. DBML).</span><span class="sxs-lookup"><span data-stu-id="a6ba0-103">You can generate Visual Basic or C# source code from a database markup language (.dbml) metadata file.</span></span> <span data-ttu-id="a6ba0-104">Этот способ предоставляет возможность настройки заданного по умолчанию DBML-файла до создания кода сопоставления приложений.</span><span class="sxs-lookup"><span data-stu-id="a6ba0-104">This approach provides an opportunity to customize the default .dbml file before you generate the application mapping code.</span></span> <span data-ttu-id="a6ba0-105">Данная возможность является дополнительной.</span><span class="sxs-lookup"><span data-stu-id="a6ba0-105">This is an advanced feature.</span></span>  
  
 <span data-ttu-id="a6ba0-106">Ниже указаны действия, необходимые для выполнения данного процесса.</span><span class="sxs-lookup"><span data-stu-id="a6ba0-106">The steps in this process are as follows:</span></span>  
  
1. <span data-ttu-id="a6ba0-107">Создайте DBML-файл.</span><span class="sxs-lookup"><span data-stu-id="a6ba0-107">Generate a .dbml file.</span></span>  
  
2. <span data-ttu-id="a6ba0-108">Для изменения DBML-файла используйте редактор.</span><span class="sxs-lookup"><span data-stu-id="a6ba0-108">Use an editor to modify the .dbml file.</span></span> <span data-ttu-id="a6ba0-109">Обратите внимание, что DBML-файл должен проверяться на соответствие файлу [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] определения схемы (XSD) файлам. dbml.</span><span class="sxs-lookup"><span data-stu-id="a6ba0-109">Note that the .dbml file must validate against the schema definition (.xsd) file for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .dbml files.</span></span> <span data-ttu-id="a6ba0-110">Дополнительные сведения см. [в разделе Создание кода в LINQ to SQL](code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a6ba0-110">For more information, see [Code Generation in LINQ to SQL](code-generation-in-linq-to-sql.md).</span></span>  
  
3. <span data-ttu-id="a6ba0-111">Создание Visual Basic или C# исходного кода.</span><span class="sxs-lookup"><span data-stu-id="a6ba0-111">Generate the Visual Basic or C# source code.</span></span>  
  
 <span data-ttu-id="a6ba0-112">В следующих примерах используется средства командной строки SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="a6ba0-112">The following examples use the SQLMetal command-line tool.</span></span> <span data-ttu-id="a6ba0-113">Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="a6ba0-113">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6ba0-114">Пример</span><span class="sxs-lookup"><span data-stu-id="a6ba0-114">Example</span></span>  
 <span data-ttu-id="a6ba0-115">В следующем коде DBML-файл создается из учебной базы данных "Northwind".</span><span class="sxs-lookup"><span data-stu-id="a6ba0-115">The following code generates a .dbml file from the Northwind sample database.</span></span> <span data-ttu-id="a6ba0-116">В качестве источника метаданных база данных можно использовать либо имя базы данных, либо имя MDF-файла.</span><span class="sxs-lookup"><span data-stu-id="a6ba0-116">As source for the database metadata, you can use either the name of the database or the name of the .mdf file.</span></span>  
  
```  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a><span data-ttu-id="a6ba0-117">Пример</span><span class="sxs-lookup"><span data-stu-id="a6ba0-117">Example</span></span>  
 <span data-ttu-id="a6ba0-118">Следующий код создает Visual Basic или C# файл исходного кода из DBML-файла.</span><span class="sxs-lookup"><span data-stu-id="a6ba0-118">The following code generates Visual Basic or C# source code file from a .dbml file.</span></span>  
  
```  
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a><span data-ttu-id="a6ba0-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a6ba0-119">See also</span></span>

- [<span data-ttu-id="a6ba0-120">Создание кода в LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="a6ba0-120">Code Generation in LINQ to SQL</span></span>](code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="a6ba0-121">SqlMetal.exe (средство создания кода)</span><span class="sxs-lookup"><span data-stu-id="a6ba0-121">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- [<span data-ttu-id="a6ba0-122">Создание модели объектов</span><span class="sxs-lookup"><span data-stu-id="a6ba0-122">Creating the Object Model</span></span>](creating-the-object-model.md)
