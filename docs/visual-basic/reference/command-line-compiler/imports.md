---
title: "/ imports (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e994e94dcc3cd00f868b6ae90e4c019eb5b9e2eb
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="imports-visual-basic"></a><span data-ttu-id="0e7e7-102">/imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e7e7-102">/imports (Visual Basic)</span></span>
<span data-ttu-id="0e7e7-103">Импортирует пространство имен из указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e7e7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0e7e7-104">Syntax</span></span>  
  
```  
/imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="0e7e7-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="0e7e7-105">Arguments</span></span>  
  
|<span data-ttu-id="0e7e7-106">Термин</span><span class="sxs-lookup"><span data-stu-id="0e7e7-106">Term</span></span>|<span data-ttu-id="0e7e7-107">Определение</span><span class="sxs-lookup"><span data-stu-id="0e7e7-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="0e7e7-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-108">Required.</span></span> <span data-ttu-id="0e7e7-109">Разделенный запятыми список пространств имен для импорта.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e7e7-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="0e7e7-110">Remarks</span></span>  
 <span data-ttu-id="0e7e7-111">`/imports` Параметр импортирует любое пространство имен, определенное в текущем наборе исходных файлов или из любой сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-111">The `/imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="0e7e7-112">Члены пространства имен, указанные с `/imports` доступны для всех файлов исходного кода при компиляции.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-112">The members in a namespace specified with `/imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="0e7e7-113">Используйте [оператор Imports (пространство имен .NET и тип)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) для использования пространства имен в файле одного исходного кода.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="0e7e7-114">Чтобы задать и импортирует в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0e7e7-114">To set /imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="0e7e7-115">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="0e7e7-116">На **проекта** меню, щелкните **свойства**.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-116">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="0e7e7-117">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="0e7e7-117">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="0e7e7-118">2.  Щелкните **ссылки** вкладки.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-118">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="0e7e7-119">3.  Введите имя пространства имен в поле рядом с **добавить пользовательский импорт** кнопки.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-119">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="0e7e7-120">4.  Щелкните **добавить пользовательский импорт** кнопки.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-120">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0e7e7-121">Пример</span><span class="sxs-lookup"><span data-stu-id="0e7e7-121">Example</span></span>  
 <span data-ttu-id="0e7e7-122">Следующий код компилируется при `/imports:system` указано.</span><span class="sxs-lookup"><span data-stu-id="0e7e7-122">The following code compiles when `/imports:system` is specified.</span></span>  
  
 <span data-ttu-id="0e7e7-123">[!code-vb[VbVbalrCompiler&#21;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/imports_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="0e7e7-123">[!code-vb[VbVbalrCompiler#21](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/imports_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e7e7-124">См. также</span><span class="sxs-lookup"><span data-stu-id="0e7e7-124">See Also</span></span>  
 <span data-ttu-id="0e7e7-125">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="0e7e7-125">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="0e7e7-126"> [Ссылки и оператор Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span><span class="sxs-lookup"><span data-stu-id="0e7e7-126"> [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span></span>  
<span data-ttu-id="0e7e7-127"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="0e7e7-127"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
