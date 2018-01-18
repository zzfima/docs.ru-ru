---
title: "Практическое руководство. Создание настраиваемого кода за счет изменения файла DBML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c9a2b382c84548d3226fe68531961e0f53033e7d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a><span data-ttu-id="34c47-102">Практическое руководство. Создание настраиваемого кода за счет изменения файла DBML</span><span class="sxs-lookup"><span data-stu-id="34c47-102">How to: Generate Customized Code by Modifying a DBML File</span></span>
<span data-ttu-id="34c47-103">Можно создать [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] или исходного кода C# из файла метаданных DBML-разметки базы данных.</span><span class="sxs-lookup"><span data-stu-id="34c47-103">You can generate [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] or C# source code from a database markup language (.dbml) metadata file.</span></span> <span data-ttu-id="34c47-104">Этот способ предоставляет возможность настройки заданного по умолчанию DBML-файла до создания кода сопоставления приложений.</span><span class="sxs-lookup"><span data-stu-id="34c47-104">This approach provides an opportunity to customize the default .dbml file before you generate the application mapping code.</span></span> <span data-ttu-id="34c47-105">Данная возможность является дополнительной.</span><span class="sxs-lookup"><span data-stu-id="34c47-105">This is an advanced feature.</span></span>  
  
 <span data-ttu-id="34c47-106">Ниже указаны действия, необходимые для выполнения данного процесса.</span><span class="sxs-lookup"><span data-stu-id="34c47-106">The steps in this process are as follows:</span></span>  
  
1.  <span data-ttu-id="34c47-107">Создайте DBML-файл.</span><span class="sxs-lookup"><span data-stu-id="34c47-107">Generate a .dbml file.</span></span>  
  
2.  <span data-ttu-id="34c47-108">Для изменения DBML-файла используйте редактор.</span><span class="sxs-lookup"><span data-stu-id="34c47-108">Use an editor to modify the .dbml file.</span></span> <span data-ttu-id="34c47-109">Обратите внимание, что DBML-файла необходимо проверить соответствие файлу определения (.xsd) схемы для [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] DBML-файлы.</span><span class="sxs-lookup"><span data-stu-id="34c47-109">Note that the .dbml file must validate against the schema definition (.xsd) file for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .dbml files.</span></span> <span data-ttu-id="34c47-110">Дополнительные сведения см. в разделе [создание кода в LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="34c47-110">For more information, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
3.  <span data-ttu-id="34c47-111">Создайте исходный код [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] или C#.</span><span class="sxs-lookup"><span data-stu-id="34c47-111">Generate the [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] or C# source code.</span></span>  
  
 <span data-ttu-id="34c47-112">В следующих примерах используется средства командной строки SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="34c47-112">The following examples use the SQLMetal command-line tool.</span></span> <span data-ttu-id="34c47-113">Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="34c47-113">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="34c47-114">Пример</span><span class="sxs-lookup"><span data-stu-id="34c47-114">Example</span></span>  
 <span data-ttu-id="34c47-115">В следующем коде DBML-файл создается из учебной базы данных "Northwind".</span><span class="sxs-lookup"><span data-stu-id="34c47-115">The following code generates a .dbml file from the Northwind sample database.</span></span> <span data-ttu-id="34c47-116">В качестве источника метаданных база данных можно использовать либо имя базы данных, либо имя MDF-файла.</span><span class="sxs-lookup"><span data-stu-id="34c47-116">As source for the database metadata, you can use either the name of the database or the name of the .mdf file.</span></span>  
  
```  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a><span data-ttu-id="34c47-117">Пример</span><span class="sxs-lookup"><span data-stu-id="34c47-117">Example</span></span>  
 <span data-ttu-id="34c47-118">В следующем коде исходный код [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] или C# создается из DBML-файла.</span><span class="sxs-lookup"><span data-stu-id="34c47-118">The following code generates [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] or C# source code file from a .dbml file.</span></span>  
  
```  
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a><span data-ttu-id="34c47-119">См. также</span><span class="sxs-lookup"><span data-stu-id="34c47-119">See Also</span></span>  
 [<span data-ttu-id="34c47-120">Создание кода в LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="34c47-120">Code Generation in LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)  
 [<span data-ttu-id="34c47-121">SqlMetal.exe (средство создания кода)</span><span class="sxs-lookup"><span data-stu-id="34c47-121">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)  
 [<span data-ttu-id="34c47-122">Создание модели объектов</span><span class="sxs-lookup"><span data-stu-id="34c47-122">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
