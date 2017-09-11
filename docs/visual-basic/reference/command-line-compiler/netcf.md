---
title: "/ netcf | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /netcf
- netcf
dev_langs:
- VB
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
caps.latest.revision: 18
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
ms.openlocfilehash: 375ec79fe2bf63bc03988ecaad877eb27f43d55b
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="netcf"></a><span data-ttu-id="628ae-102">/netcf</span><span class="sxs-lookup"><span data-stu-id="628ae-102">/netcf</span></span>
<span data-ttu-id="628ae-103">Задает для компилятора целевой объект [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].</span><span class="sxs-lookup"><span data-stu-id="628ae-103">Sets the compiler to target the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="628ae-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="628ae-104">Syntax</span></span>  
  
```  
/netcf  
```  
  
## <a name="remarks"></a><span data-ttu-id="628ae-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="628ae-105">Remarks</span></span>  
 <span data-ttu-id="628ae-106">`/netcf` Предписывает [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятору целевой [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] вместо полного [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span><span class="sxs-lookup"><span data-stu-id="628ae-106">The `/netcf` option causes the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler to target the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] rather than the full [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span> <span data-ttu-id="628ae-107">Функциональность языка, имеющаяся только в полной [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] отключена.</span><span class="sxs-lookup"><span data-stu-id="628ae-107">Language functionality that is present only in the full [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] is disabled.</span></span>  
  
 <span data-ttu-id="628ae-108">`/netcf` Параметр предназначен для использования с [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span><span class="sxs-lookup"><span data-stu-id="628ae-108">The `/netcf` option is designed to be used with [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span></span> <span data-ttu-id="628ae-109">Языковые возможности, отключенные с `/netcf` же не присутствует в файлах с языковыми возможностями `/sdkpath`.</span><span class="sxs-lookup"><span data-stu-id="628ae-109">The language features disabled by `/netcf` are the same language features not present in the files targeted with `/sdkpath`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="628ae-110">`/netcf` Параметр недоступен из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="628ae-110">The `/netcf` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="628ae-111">`/netcf` Параметр задается при [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] загрузке проекта устройства.</span><span class="sxs-lookup"><span data-stu-id="628ae-111">The `/netcf` option is set when a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] device project is loaded.</span></span>  
  
 <span data-ttu-id="628ae-112">`/netcf` Параметр изменяет следующие функции языка:</span><span class="sxs-lookup"><span data-stu-id="628ae-112">The `/netcf` option changes the following language features:</span></span>  
  
-   <span data-ttu-id="628ae-113">[End \<ключевое слово настроек инструкции](../../../visual-basic/language-reference/statements/end-keyword-statement.md) ключевое слово, которое прекращает выполнение программы, отключено.</span><span class="sxs-lookup"><span data-stu-id="628ae-113">The [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) keyword, which terminates execution of a program, is disabled.</span></span> <span data-ttu-id="628ae-114">Следующая программа компилируется и выполняется без `/netcf` , но во время компиляции с `/netcf`.</span><span class="sxs-lookup"><span data-stu-id="628ae-114">The following program compiles and runs without `/netcf` but fails at compile time with `/netcf`.</span></span>  
  
     <span data-ttu-id="628ae-115">[!code-vb[VbVbalrCompiler&#34;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="628ae-115">[!code-vb[VbVbalrCompiler#34](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_1.vb)]</span></span>  
  
-   <span data-ttu-id="628ae-116">Позднее связывание во всех формах отключено.</span><span class="sxs-lookup"><span data-stu-id="628ae-116">Late binding, in all forms, is disabled.</span></span> <span data-ttu-id="628ae-117">При обнаружении распознанных сценариев позднего связывания, возникают ошибки во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="628ae-117">Compile-time errors are generated when recognized late-binding scenarios are encountered.</span></span> <span data-ttu-id="628ae-118">Следующая программа компилируется и выполняется без `/netcf` , но во время компиляции с `/netcf`.</span><span class="sxs-lookup"><span data-stu-id="628ae-118">The following program compiles and runs without `/netcf` but fails at compile time with `/netcf`.</span></span>  
  
     <span data-ttu-id="628ae-119">[!code-vb[VbVbalrCompiler&#35;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="628ae-119">[!code-vb[VbVbalrCompiler#35](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_2.vb)]</span></span>  
  
-   <span data-ttu-id="628ae-120">[Автоматически](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), и [Юникода](../../../visual-basic/language-reference/modifiers/unicode.md) модификаторы отключены.</span><span class="sxs-lookup"><span data-stu-id="628ae-120">The [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), and [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modifiers are disabled.</span></span> <span data-ttu-id="628ae-121">Синтаксис [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) инструкции также изменяется — `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span><span class="sxs-lookup"><span data-stu-id="628ae-121">The syntax of the [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) statement is also modified to `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span></span> <span data-ttu-id="628ae-122">В следующем коде показано влияние `/netcf` на процесс компиляции.</span><span class="sxs-lookup"><span data-stu-id="628ae-122">The following code shows the effect of `/netcf` on a compilation.</span></span>  
  
     <span data-ttu-id="628ae-123">[!code-vb[VbVbalrCompiler&#36;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="628ae-123">[!code-vb[VbVbalrCompiler#36](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_3.vb)]</span></span>  
  
-   <span data-ttu-id="628ae-124">Использование ключевых слов Visual Basic 6.0, которые были удалены из [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] создает различные ошибки при `/netcf` используется.</span><span class="sxs-lookup"><span data-stu-id="628ae-124">Using Visual Basic 6.0 keywords that were removed from [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] generates a different error when `/netcf` is used.</span></span> <span data-ttu-id="628ae-125">Это влияет на сообщения об ошибках для следующих ключевых слов:</span><span class="sxs-lookup"><span data-stu-id="628ae-125">This affects the error messages for the following keywords:</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="628ae-126">Пример</span><span class="sxs-lookup"><span data-stu-id="628ae-126">Example</span></span>  
 <span data-ttu-id="628ae-127">Следующий код компилирует `Myfile.vb` с [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)], с помощью версии Mscorlib.dll и Microsoft.VisualBasic.dll найти в каталоге установки по умолчанию [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] на диске C:.</span><span class="sxs-lookup"><span data-stu-id="628ae-127">The following code compiles `Myfile.vb` with the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)], using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] on the C drive.</span></span> <span data-ttu-id="628ae-128">Как правило, используется последней версии [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].</span><span class="sxs-lookup"><span data-stu-id="628ae-128">Typically, you would use the most recent version of the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].</span></span>  
  
```  
vbc /netcf /sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="628ae-129">См. также</span><span class="sxs-lookup"><span data-stu-id="628ae-129">See Also</span></span>  
 <span data-ttu-id="628ae-130">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="628ae-130">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="628ae-131"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="628ae-131"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="628ae-132"> [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)</span><span class="sxs-lookup"><span data-stu-id="628ae-132"> [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)</span></span>
