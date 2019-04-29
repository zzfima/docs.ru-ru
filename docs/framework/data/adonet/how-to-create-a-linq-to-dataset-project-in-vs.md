---
title: Создание проектов LINQ to DataSet в Visual Studio
ms.date: 08/15/2018
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
ms.openlocfilehash: 22763d3b9581d09d7bdda0c09480f8d36bb8e2ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667055"
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a><span data-ttu-id="ff95a-102">Практическое руководство. Создание проектов LINQ to DataSet в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ff95a-102">How to: Create a LINQ to DataSet project In Visual Studio</span></span>

<span data-ttu-id="ff95a-103">Различные типы проектов LINQ требуются некоторые ссылки на сборки и импортируемых пространств имен (Visual Basic) или [с помощью](../../../csharp/language-reference/keywords/using-directive.md) директивы (C#).</span><span class="sxs-lookup"><span data-stu-id="ff95a-103">The different types of LINQ projects require certain assembly references and imported namespaces (Visual Basic) or [using](../../../csharp/language-reference/keywords/using-directive.md) directives (C#).</span></span> <span data-ttu-id="ff95a-104">Минимальным требованием для LINQ — это ссылка на *System.Core.dll* и `using` директив для <xref:System.Linq>.</span><span class="sxs-lookup"><span data-stu-id="ff95a-104">The minimum requirement for LINQ is a reference to *System.Core.dll* and a `using` directive for <xref:System.Linq>.</span></span>

<span data-ttu-id="ff95a-105">Эти требования предоставляются по умолчанию при создании C# консольного приложения проекта в Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="ff95a-105">These requirements are supplied by default if you create a new C# console app project in Visual Studio 2017.</span></span> <span data-ttu-id="ff95a-106">Если вы обновляете проект с более ранней версии Visual Studio, может потребоваться вручную ввести эти ссылки, связанные с LINQ.</span><span class="sxs-lookup"><span data-stu-id="ff95a-106">If you're upgrading a project from an earlier version of Visual Studio, you might have to supply these LINQ-related references manually.</span></span>

<span data-ttu-id="ff95a-107">LINQ to DataSet требуются две дополнительные ссылки на *System.Data.dll* и *System.Data.DataSetExtensions.dll*.</span><span class="sxs-lookup"><span data-stu-id="ff95a-107">LINQ to DataSet requires two additional references to *System.Data.dll* and *System.Data.DataSetExtensions.dll*.</span></span>

> [!NOTE]
> <span data-ttu-id="ff95a-108">Если вы выполняете сборку из командной строки, необходимо вручную указать связанные с LINQ библиотеки DLL в *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*.</span><span class="sxs-lookup"><span data-stu-id="ff95a-108">If you're building from a command prompt, you must manually reference the LINQ-related DLLs in *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*.</span></span>

## <a name="to-enable-linq-to-dataset-functionality"></a><span data-ttu-id="ff95a-109">Включение функциональности LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="ff95a-109">To enable LINQ to DataSet functionality</span></span>

<span data-ttu-id="ff95a-110">Выполните следующие шаги для включения функциональных возможностей набора данных в существующий проект LINQ.</span><span class="sxs-lookup"><span data-stu-id="ff95a-110">Follow these steps to enable LINQ to DataSet functionality in an existing project.</span></span>

1. <span data-ttu-id="ff95a-111">Добавьте ссылки на **System.Core**, **System.Data**, и **System.Data.DataSetExtensions**.</span><span class="sxs-lookup"><span data-stu-id="ff95a-111">Add references to **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span>

   <span data-ttu-id="ff95a-112">В **обозревателе решений**, щелкните правой кнопкой мыши **ссылки** узел и выберите **добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="ff95a-112">In **Solution Explorer**, right-click on the **References** node and select **Add Reference**.</span></span> <span data-ttu-id="ff95a-113">В **диспетчер ссылок** выберите **System.Core**, **System.Data**, и **System.Data.DataSetExtensions**.</span><span class="sxs-lookup"><span data-stu-id="ff95a-113">In the **Reference Manager** dialog box, select **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span> <span data-ttu-id="ff95a-114">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ff95a-114">Select **OK**.</span></span>

1. <span data-ttu-id="ff95a-115">Добавить [с помощью](../../../csharp/language-reference/keywords/using-directive.md) директивы (или [инструкции импорта](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) в Visual Basic) для **System.Data** и **System.Linq**.</span><span class="sxs-lookup"><span data-stu-id="ff95a-115">Add [using](../../../csharp/language-reference/keywords/using-directive.md) directives (or [Imports statements](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) in Visual Basic) for **System.Data** and **System.Linq**.</span></span>

   ```csharp
   using System.Data;
   using System.Linq;
   ```

1. <span data-ttu-id="ff95a-116">При необходимости добавьте `using` директивы (или `Imports` инструкции) для **System.Data.Common** или **System.Data.SqlClient**, в зависимости от способа подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="ff95a-116">Optionally, add a `using` directive (or `Imports` statement) for **System.Data.Common** or **System.Data.SqlClient**, depending on how you connect to the database.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff95a-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ff95a-117">See also</span></span>

- [<span data-ttu-id="ff95a-118">Начало работы с LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="ff95a-118">Get started with LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)
