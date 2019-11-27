---
title: -imports
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: 380e71e462f736d4564a37b83567007fa9461b05
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332957"
---
# <a name="-imports-visual-basic"></a><span data-ttu-id="c468e-102">-Imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c468e-102">-imports (Visual Basic)</span></span>
<span data-ttu-id="c468e-103">Импортирует пространства имен из указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="c468e-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c468e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c468e-104">Syntax</span></span>  
  
```console  
-imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="c468e-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c468e-105">Arguments</span></span>  
  
|<span data-ttu-id="c468e-106">Термин</span><span class="sxs-lookup"><span data-stu-id="c468e-106">Term</span></span>|<span data-ttu-id="c468e-107">Определение</span><span class="sxs-lookup"><span data-stu-id="c468e-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="c468e-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="c468e-108">Required.</span></span> <span data-ttu-id="c468e-109">Разделенный запятыми список пространств имен для импорта.</span><span class="sxs-lookup"><span data-stu-id="c468e-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c468e-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="c468e-110">Remarks</span></span>  
 <span data-ttu-id="c468e-111">Параметр `-imports` импортирует любое пространство имен, определенное в текущем наборе исходных файлов или в любой связанной сборке.</span><span class="sxs-lookup"><span data-stu-id="c468e-111">The `-imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="c468e-112">Элементы в пространстве имен, заданном с помощью `-imports`, доступны для всех файлов исходного кода в компиляции.</span><span class="sxs-lookup"><span data-stu-id="c468e-112">The members in a namespace specified with `-imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="c468e-113">Используйте [оператор Imports (пространство имен .NET и тип)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) , чтобы использовать пространство имен в одном файле исходного кода.</span><span class="sxs-lookup"><span data-stu-id="c468e-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="c468e-114">Установка/Imports в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c468e-114">To set /imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="c468e-115">1. Выберите проект в **Обозреватель решений**.</span><span class="sxs-lookup"><span data-stu-id="c468e-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c468e-116">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="c468e-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="c468e-117">2. Перейдите на вкладку **ссылки** .</span><span class="sxs-lookup"><span data-stu-id="c468e-117">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="c468e-118">3. Введите имя пространства имен в поле рядом с кнопкой **Добавить пользовательский импорт** .</span><span class="sxs-lookup"><span data-stu-id="c468e-118">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="c468e-119">4. Нажмите кнопку **Добавить пользовательский импорт** .</span><span class="sxs-lookup"><span data-stu-id="c468e-119">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c468e-120">Пример</span><span class="sxs-lookup"><span data-stu-id="c468e-120">Example</span></span>  
 <span data-ttu-id="c468e-121">Следующий код компилируется при указании `/imports:system.globalization`.</span><span class="sxs-lookup"><span data-stu-id="c468e-121">The following code compiles when `/imports:system.globalization` is specified.</span></span> <span data-ttu-id="c468e-122">В противном случае для успешной компиляции требуется, чтобы инструкция `Imports System.Globalization` была включена в начало файла исходного кода или что свойство полностью определено как `System.Globalization.CultureInfo.CurrentCulture.Name`.</span><span class="sxs-lookup"><span data-stu-id="c468e-122">Without it, successful compilation requires either that an `Imports System.Globalization` statement be included at the beginning of the source code file, or that the property be fully qualified as `System.Globalization.CultureInfo.CurrentCulture.Name`.</span></span>

```vb
Module Example
   Public Sub Main()
      Console.WriteLine($"The current culture is {CultureInfo.CurrentCulture.Name}")
   End Sub
End Module
```

## <a name="see-also"></a><span data-ttu-id="c468e-123">См. также</span><span class="sxs-lookup"><span data-stu-id="c468e-123">See also</span></span>

- [<span data-ttu-id="c468e-124">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="c468e-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="c468e-125">Ссылки и оператор Imports</span><span class="sxs-lookup"><span data-stu-id="c468e-125">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="c468e-126">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="c468e-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
