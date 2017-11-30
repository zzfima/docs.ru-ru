---
title: /imports (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e8e9cd761263b3b61a4e6d3e33c5f7f875be7a1d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imports-visual-basic"></a><span data-ttu-id="8154d-102">/imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8154d-102">/imports (Visual Basic)</span></span>
<span data-ttu-id="8154d-103">Импортирует пространство имен из указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="8154d-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8154d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8154d-104">Syntax</span></span>  
  
```  
/imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="8154d-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="8154d-105">Arguments</span></span>  
  
|<span data-ttu-id="8154d-106">Термин</span><span class="sxs-lookup"><span data-stu-id="8154d-106">Term</span></span>|<span data-ttu-id="8154d-107">Определение</span><span class="sxs-lookup"><span data-stu-id="8154d-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="8154d-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="8154d-108">Required.</span></span> <span data-ttu-id="8154d-109">Разделенный запятыми список пространств имен для импорта.</span><span class="sxs-lookup"><span data-stu-id="8154d-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8154d-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="8154d-110">Remarks</span></span>  
 <span data-ttu-id="8154d-111">`/imports` Параметр импортирует любое пространство имен, определенных в текущем наборе исходных файлов или из любой сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="8154d-111">The `/imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="8154d-112">Члены пространства имен, указанные с `/imports` доступны для всех файлов исходного кода при компиляции.</span><span class="sxs-lookup"><span data-stu-id="8154d-112">The members in a namespace specified with `/imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="8154d-113">Используйте [оператор Imports (пространство имен .NET и тип)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) для использования пространства имен в файле одного исходного кода.</span><span class="sxs-lookup"><span data-stu-id="8154d-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="8154d-114">Чтобы задать/imports в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8154d-114">To set /imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="8154d-115">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="8154d-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="8154d-116">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="8154d-116">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="8154d-117">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="8154d-117">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="8154d-118">2.  Перейдите на вкладку **Ссылки**.</span><span class="sxs-lookup"><span data-stu-id="8154d-118">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="8154d-119">3.  Введите имя пространства имен в поле рядом с **добавить пользовательский импорт** кнопки.</span><span class="sxs-lookup"><span data-stu-id="8154d-119">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="8154d-120">4.  Нажмите кнопку **добавить пользовательский импорт** кнопки.</span><span class="sxs-lookup"><span data-stu-id="8154d-120">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8154d-121">Пример</span><span class="sxs-lookup"><span data-stu-id="8154d-121">Example</span></span>  
 <span data-ttu-id="8154d-122">Следующий код компилируется при `/imports:system` указано.</span><span class="sxs-lookup"><span data-stu-id="8154d-122">The following code compiles when `/imports:system` is specified.</span></span>  
  
 [!code-vb[VbVbalrCompiler#21](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/imports_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8154d-123">См. также</span><span class="sxs-lookup"><span data-stu-id="8154d-123">See Also</span></span>  
 [<span data-ttu-id="8154d-124">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="8154d-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="8154d-125">Ссылки и оператор Imports</span><span class="sxs-lookup"><span data-stu-id="8154d-125">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [<span data-ttu-id="8154d-126">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="8154d-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
