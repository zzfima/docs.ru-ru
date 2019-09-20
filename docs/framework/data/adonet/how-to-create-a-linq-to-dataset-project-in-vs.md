---
title: Создание проекта LINQ to DataSet в Visual Studio
ms.date: 08/15/2018
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
ms.openlocfilehash: 8b905c65575c3c567459d843b2a5d1606bc63228
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783776"
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a><span data-ttu-id="0ae04-102">Практическое руководство. Создание проекта LINQ to DataSet в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0ae04-102">How to: Create a LINQ to DataSet project In Visual Studio</span></span>

<span data-ttu-id="0ae04-103">Для различных типов проектов LINQ требуются определенные ссылки на сборки и импортированные пространства имен (Visual Basic) или директивы [using](../../../csharp/language-reference/keywords/using-directive.md) (C#).</span><span class="sxs-lookup"><span data-stu-id="0ae04-103">The different types of LINQ projects require certain assembly references and imported namespaces (Visual Basic) or [using](../../../csharp/language-reference/keywords/using-directive.md) directives (C#).</span></span> <span data-ttu-id="0ae04-104">Минимальным требованием для LINQ является ссылка на *библиотеку System. Core. dll* и `using` директиву <xref:System.Linq>для.</span><span class="sxs-lookup"><span data-stu-id="0ae04-104">The minimum requirement for LINQ is a reference to *System.Core.dll* and a `using` directive for <xref:System.Linq>.</span></span>

<span data-ttu-id="0ae04-105">Эти требования предоставляются по умолчанию при создании нового C# проекта консольного приложения в Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="0ae04-105">These requirements are supplied by default if you create a new C# console app project in Visual Studio 2017.</span></span> <span data-ttu-id="0ae04-106">Если вы обновляете проект с более ранней версии Visual Studio, вам может потребоваться предоставить эти ссылки, связанные с LINQ, вручную.</span><span class="sxs-lookup"><span data-stu-id="0ae04-106">If you're upgrading a project from an earlier version of Visual Studio, you might have to supply these LINQ-related references manually.</span></span>

<span data-ttu-id="0ae04-107">LINQ to DataSet требуется две дополнительные ссылки на *System. Data. dll* и *System. Data. DataSetExtensions. dll*.</span><span class="sxs-lookup"><span data-stu-id="0ae04-107">LINQ to DataSet requires two additional references to *System.Data.dll* and *System.Data.DataSetExtensions.dll*.</span></span>

> [!NOTE]
> <span data-ttu-id="0ae04-108">При построении из командной строки необходимо вручную ссылаться на библиотеки DLL, связанные с LINQ, в *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*.</span><span class="sxs-lookup"><span data-stu-id="0ae04-108">If you're building from a command prompt, you must manually reference the LINQ-related DLLs in *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*.</span></span>

## <a name="to-enable-linq-to-dataset-functionality"></a><span data-ttu-id="0ae04-109">Включение функциональности LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="0ae04-109">To enable LINQ to DataSet functionality</span></span>

<span data-ttu-id="0ae04-110">Выполните следующие действия, чтобы включить LINQ to DataSet функциональности в существующем проекте.</span><span class="sxs-lookup"><span data-stu-id="0ae04-110">Follow these steps to enable LINQ to DataSet functionality in an existing project.</span></span>

1. <span data-ttu-id="0ae04-111">Добавьте ссылки на **System. Core**, **System. Data**и **System. Data. DataSetExtensions**.</span><span class="sxs-lookup"><span data-stu-id="0ae04-111">Add references to **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span>

   <span data-ttu-id="0ae04-112">В **Обозреватель решений**щелкните правой кнопкой мыши узел **ссылки** и выберите команду **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="0ae04-112">In **Solution Explorer**, right-click on the **References** node and select **Add Reference**.</span></span> <span data-ttu-id="0ae04-113">В диалоговом окне **Диспетчер ссылок** выберите **System. Core**, **System. Data**и **System. Data. DataSetExtensions**.</span><span class="sxs-lookup"><span data-stu-id="0ae04-113">In the **Reference Manager** dialog box, select **System.Core**, **System.Data**, and **System.Data.DataSetExtensions**.</span></span> <span data-ttu-id="0ae04-114">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0ae04-114">Select **OK**.</span></span>

1. <span data-ttu-id="0ae04-115">Добавьте директивы [using](../../../csharp/language-reference/keywords/using-directive.md) (или [импортирует операторы](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) в Visual Basic) для **System. Data** и **System. LINQ**.</span><span class="sxs-lookup"><span data-stu-id="0ae04-115">Add [using](../../../csharp/language-reference/keywords/using-directive.md) directives (or [Imports statements](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) in Visual Basic) for **System.Data** and **System.Linq**.</span></span>

   ```csharp
   using System.Data;
   using System.Linq;
   ```

1. <span data-ttu-id="0ae04-116">При необходимости `using` добавьте директиву ( `Imports` или оператор) для **System. Data. Common** или **System. Data. SqlClient**в зависимости от способа подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="0ae04-116">Optionally, add a `using` directive (or `Imports` statement) for **System.Data.Common** or **System.Data.SqlClient**, depending on how you connect to the database.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ae04-117">См. также</span><span class="sxs-lookup"><span data-stu-id="0ae04-117">See also</span></span>

- [<span data-ttu-id="0ae04-118">Начало работы с LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="0ae04-118">Get started with LINQ to DataSet</span></span>](getting-started-linq-to-dataset.md)
