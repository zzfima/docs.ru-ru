---
title: -netcf
ms.date: 03/13/2018
f1_keywords:
- /netcf
- -netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
ms.openlocfilehash: d213f0f95d047a3758a4c85e4dc8263f82dcac8a
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53130211"
---
# <a name="-netcf"></a><span data-ttu-id="c2d21-102">-netcf</span><span class="sxs-lookup"><span data-stu-id="c2d21-102">-netcf</span></span>
<span data-ttu-id="c2d21-103">Задает для компилятора целевой объект [!INCLUDE[Compact](~/includes/compact-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2d21-103">Sets the compiler to target the [!INCLUDE[Compact](~/includes/compact-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2d21-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2d21-104">Syntax</span></span>  
  
```  
-netcf  
```  
  
## <a name="remarks"></a><span data-ttu-id="c2d21-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="c2d21-105">Remarks</span></span>  
 <span data-ttu-id="c2d21-106">`-netcf` Компилятору Visual Basic к целевому объекту [!INCLUDE[Compact](~/includes/compact-md.md)] вместо полной [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2d21-106">The `-netcf` option causes the Visual Basic compiler to target the [!INCLUDE[Compact](~/includes/compact-md.md)] rather than the full [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="c2d21-107">Функциональные возможности языка, которая присутствует только в полной [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] отключена.</span><span class="sxs-lookup"><span data-stu-id="c2d21-107">Language functionality that is present only in the full [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] is disabled.</span></span>  
  
 <span data-ttu-id="c2d21-108">`-netcf` Параметр предназначен для использования с [- sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span><span class="sxs-lookup"><span data-stu-id="c2d21-108">The `-netcf` option is designed to be used with [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span></span> <span data-ttu-id="c2d21-109">Языковые возможности, отключенные по `-netcf` являются те же функции языка, не представленным в файлах `-sdkpath`.</span><span class="sxs-lookup"><span data-stu-id="c2d21-109">The language features disabled by `-netcf` are the same language features not present in the files targeted with `-sdkpath`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2d21-110">`-netcf` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="c2d21-110">The `-netcf` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="c2d21-111">`-netcf` Был установлен при загрузке проекта Visual Basic для устройства.</span><span class="sxs-lookup"><span data-stu-id="c2d21-111">The `-netcf` option is set when a Visual Basic device project is loaded.</span></span>  
  
 <span data-ttu-id="c2d21-112">`-netcf` Параметр изменяет следующие функции языка:</span><span class="sxs-lookup"><span data-stu-id="c2d21-112">The `-netcf` option changes the following language features:</span></span>  
  
-   <span data-ttu-id="c2d21-113">[Окончания \<ключевое слово > инструкции](../../../visual-basic/language-reference/statements/end-keyword-statement.md) ключевое слово, которое завершает выполнение программы, отключен.</span><span class="sxs-lookup"><span data-stu-id="c2d21-113">The [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) keyword, which terminates execution of a program, is disabled.</span></span> <span data-ttu-id="c2d21-114">Следующая программа компилируется и выполняется без `-netcf` , но во время компиляции с `-netcf`.</span><span class="sxs-lookup"><span data-stu-id="c2d21-114">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>  
  
     [!code-vb[VbVbalrCompiler#34](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_1.vb)]  
  
-   <span data-ttu-id="c2d21-115">Позднее связывание, во всех формах, отключен.</span><span class="sxs-lookup"><span data-stu-id="c2d21-115">Late binding, in all forms, is disabled.</span></span> <span data-ttu-id="c2d21-116">Ошибки времени компиляции создаются при обнаружении распознанных сценариев позднего связывания.</span><span class="sxs-lookup"><span data-stu-id="c2d21-116">Compile-time errors are generated when recognized late-binding scenarios are encountered.</span></span> <span data-ttu-id="c2d21-117">Следующая программа компилируется и выполняется без `-netcf` , но во время компиляции с `-netcf`.</span><span class="sxs-lookup"><span data-stu-id="c2d21-117">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>  
  
     [!code-vb[VbVbalrCompiler#35](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_2.vb)]  
  
-   <span data-ttu-id="c2d21-118">[Автоматически](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), и [Юникода](../../../visual-basic/language-reference/modifiers/unicode.md) модификаторы отключены.</span><span class="sxs-lookup"><span data-stu-id="c2d21-118">The [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), and [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modifiers are disabled.</span></span> <span data-ttu-id="c2d21-119">Синтаксис [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) инструкции также изменяется — `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span><span class="sxs-lookup"><span data-stu-id="c2d21-119">The syntax of the [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) statement is also modified to `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span></span> <span data-ttu-id="c2d21-120">В следующем коде показано влияние `-netcf` на процесс компиляции.</span><span class="sxs-lookup"><span data-stu-id="c2d21-120">The following code shows the effect of `-netcf` on a compilation.</span></span>  
  
     [!code-vb[VbVbalrCompiler#36](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_3.vb)]  
  
-   <span data-ttu-id="c2d21-121">Использование ключевых слов Visual Basic 6.0, которые были удалены из Visual Basic создает различные ошибки при `-netcf` используется.</span><span class="sxs-lookup"><span data-stu-id="c2d21-121">Using Visual Basic 6.0 keywords that were removed from Visual Basic generates a different error when `-netcf` is used.</span></span> <span data-ttu-id="c2d21-122">Это влияет на сообщения об ошибках для следующих ключевых слов:</span><span class="sxs-lookup"><span data-stu-id="c2d21-122">This affects the error messages for the following keywords:</span></span>  
  
    -   `Open`  
  
    -   `Close`  
  
    -   `Put`  
  
    -   `Print`  
  
    -   `Write`  
  
    -   `Input`  
  
    -   `Lock`  
  
    -   `Unlock`  
  
    -   `Seek`  
  
    -   `Width`  
  
    -   `Name`  
  
    -   `FreeFile`  
  
    -   `EOF`  
  
    -   `Loc`  
  
    -   `LOF`  
  
    -   `Line`  
  
## <a name="example"></a><span data-ttu-id="c2d21-123">Пример</span><span class="sxs-lookup"><span data-stu-id="c2d21-123">Example</span></span>  
 <span data-ttu-id="c2d21-124">Следующий код компилирует `Myfile.vb` с [!INCLUDE[Compact](~/includes/compact-md.md)], с помощью версии библиотеки mscorlib.dll и Microsoft.VisualBasic.dll см. в каталог установки по умолчанию для [!INCLUDE[Compact](~/includes/compact-md.md)] на диске C:.</span><span class="sxs-lookup"><span data-stu-id="c2d21-124">The following code compiles `Myfile.vb` with the [!INCLUDE[Compact](~/includes/compact-md.md)], using the versions of mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the [!INCLUDE[Compact](~/includes/compact-md.md)] on the C drive.</span></span> <span data-ttu-id="c2d21-125">Как правило, используется самую последнюю версию [!INCLUDE[Compact](~/includes/compact-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2d21-125">Typically, you would use the most recent version of the [!INCLUDE[Compact](~/includes/compact-md.md)].</span></span>  
  
```console  
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c2d21-126">См. также</span><span class="sxs-lookup"><span data-stu-id="c2d21-126">See Also</span></span>  
 [<span data-ttu-id="c2d21-127">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="c2d21-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="c2d21-128">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="c2d21-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="c2d21-129">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="c2d21-129">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
