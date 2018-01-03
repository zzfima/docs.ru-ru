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
ms.openlocfilehash: 6cdb7cff2221930113d6b49a640da0844f175f1b
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="imports-visual-basic"></a><span data-ttu-id="3487c-102">/imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3487c-102">/imports (Visual Basic)</span></span>
<span data-ttu-id="3487c-103">Импортирует пространство имен из указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="3487c-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3487c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3487c-104">Syntax</span></span>  
  
```  
/imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="3487c-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="3487c-105">Arguments</span></span>  
  
|<span data-ttu-id="3487c-106">Термин</span><span class="sxs-lookup"><span data-stu-id="3487c-106">Term</span></span>|<span data-ttu-id="3487c-107">Определение</span><span class="sxs-lookup"><span data-stu-id="3487c-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="3487c-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="3487c-108">Required.</span></span> <span data-ttu-id="3487c-109">Разделенный запятыми список пространств имен для импорта.</span><span class="sxs-lookup"><span data-stu-id="3487c-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3487c-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="3487c-110">Remarks</span></span>  
 <span data-ttu-id="3487c-111">`/imports` Параметр импортирует любое пространство имен, определенных в текущем наборе исходных файлов или из любой сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="3487c-111">The `/imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="3487c-112">Члены пространства имен, указанные с `/imports` доступны для всех файлов исходного кода при компиляции.</span><span class="sxs-lookup"><span data-stu-id="3487c-112">The members in a namespace specified with `/imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="3487c-113">Используйте [оператор Imports (пространство имен .NET и тип)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) для использования пространства имен в файле одного исходного кода.</span><span class="sxs-lookup"><span data-stu-id="3487c-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="3487c-114">Чтобы задать/imports в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3487c-114">To set /imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="3487c-115">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="3487c-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="3487c-116">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="3487c-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="3487c-117">2.  Перейдите на вкладку **Ссылки**.</span><span class="sxs-lookup"><span data-stu-id="3487c-117">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="3487c-118">3.  Введите имя пространства имен в поле рядом с **добавить пользовательский импорт** кнопки.</span><span class="sxs-lookup"><span data-stu-id="3487c-118">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="3487c-119">4.  Нажмите кнопку **добавить пользовательский импорт** кнопки.</span><span class="sxs-lookup"><span data-stu-id="3487c-119">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3487c-120">Пример</span><span class="sxs-lookup"><span data-stu-id="3487c-120">Example</span></span>  
 <span data-ttu-id="3487c-121">Следующий код компилируется при `/imports:system` указано.</span><span class="sxs-lookup"><span data-stu-id="3487c-121">The following code compiles when `/imports:system` is specified.</span></span>  
  
 [!code-vb[VbVbalrCompiler#21](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/imports_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3487c-122">См. также</span><span class="sxs-lookup"><span data-stu-id="3487c-122">See Also</span></span>  
 [<span data-ttu-id="3487c-123">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="3487c-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="3487c-124">Ссылки и оператор Imports</span><span class="sxs-lookup"><span data-stu-id="3487c-124">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [<span data-ttu-id="3487c-125">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="3487c-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
