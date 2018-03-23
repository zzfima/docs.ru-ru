---
title: -imports (Visual Basic)
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d81e9d2bd55e6e38e337805b950a0b85680d129b
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="-imports-visual-basic"></a><span data-ttu-id="7addf-102">-imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7addf-102">-imports (Visual Basic)</span></span>
<span data-ttu-id="7addf-103">Импортирует пространство имен из указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="7addf-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7addf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7addf-104">Syntax</span></span>  
  
```  
-imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="7addf-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="7addf-105">Arguments</span></span>  
  
|<span data-ttu-id="7addf-106">Термин</span><span class="sxs-lookup"><span data-stu-id="7addf-106">Term</span></span>|<span data-ttu-id="7addf-107">Определение</span><span class="sxs-lookup"><span data-stu-id="7addf-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="7addf-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="7addf-108">Required.</span></span> <span data-ttu-id="7addf-109">Разделенный запятыми список пространств имен для импорта.</span><span class="sxs-lookup"><span data-stu-id="7addf-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7addf-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="7addf-110">Remarks</span></span>  
 <span data-ttu-id="7addf-111">`-imports` Параметр импортирует любое пространство имен, определенных в текущем наборе исходных файлов или из любой сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="7addf-111">The `-imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="7addf-112">Члены пространства имен, указанные с `-imports` доступны для всех файлов исходного кода при компиляции.</span><span class="sxs-lookup"><span data-stu-id="7addf-112">The members in a namespace specified with `-imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="7addf-113">Используйте [оператор Imports (пространство имен .NET и тип)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) для использования пространства имен в файле одного исходного кода.</span><span class="sxs-lookup"><span data-stu-id="7addf-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="7addf-114">Чтобы задать/imports в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7addf-114">To set /imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="7addf-115">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="7addf-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="7addf-116">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7addf-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="7addf-117">2.  Перейдите на вкладку **Ссылки**.</span><span class="sxs-lookup"><span data-stu-id="7addf-117">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="7addf-118">3.  Введите имя пространства имен в поле рядом с **добавить пользовательский импорт** кнопки.</span><span class="sxs-lookup"><span data-stu-id="7addf-118">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="7addf-119">4.  Нажмите кнопку **добавить пользовательский импорт** кнопки.</span><span class="sxs-lookup"><span data-stu-id="7addf-119">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7addf-120">Пример</span><span class="sxs-lookup"><span data-stu-id="7addf-120">Example</span></span>  
 <span data-ttu-id="7addf-121">Следующий код компилируется при `/imports:system.globalization` указано.</span><span class="sxs-lookup"><span data-stu-id="7addf-121">The following code compiles when `/imports:system.globalization` is specified.</span></span> <span data-ttu-id="7addf-122">Без него, требует успешной компиляции `Imports System.Globalization` инструкции включаться в начале файла исходного кода, или свойство быть полностью квалифицирован как `System.Globalization.CultureInfo.CurrentCulture.Name`.</span><span class="sxs-lookup"><span data-stu-id="7addf-122">Without it, successful compilation requires either that an `Imports System.Globalization` statement be included at the beginning of the source code file, or that the property be fully qualified as `System.Globalization.CultureInfo.CurrentCulture.Name`.</span></span> 
  
 [!code-vb[imports example](codesnippet/VisualBasic/imports_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7addf-123">См. также</span><span class="sxs-lookup"><span data-stu-id="7addf-123">See Also</span></span>  
 [<span data-ttu-id="7addf-124">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="7addf-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="7addf-125">Ссылки и оператор Imports</span><span class="sxs-lookup"><span data-stu-id="7addf-125">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [<span data-ttu-id="7addf-126">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="7addf-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
