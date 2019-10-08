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
ms.openlocfilehash: 3df7e622f97a5a1291736180e3964b1b3deaea2f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005447"
---
# <a name="-netcf"></a><span data-ttu-id="0749f-102">-netcf</span><span class="sxs-lookup"><span data-stu-id="0749f-102">-netcf</span></span>

<span data-ttu-id="0749f-103">Задает компилятор, предназначенный для .NET Compact Framework.</span><span class="sxs-lookup"><span data-stu-id="0749f-103">Sets the compiler to target the .NET Compact Framework.</span></span>

## <a name="syntax"></a><span data-ttu-id="0749f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0749f-104">Syntax</span></span>

```console
-netcf
```

## <a name="remarks"></a><span data-ttu-id="0749f-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="0749f-105">Remarks</span></span>

<span data-ttu-id="0749f-106">Параметр `-netcf` заставляет компилятор Visual Basic нацелиться на .NET Compact Framework, а не на полный .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0749f-106">The `-netcf` option causes the Visual Basic compiler to target the .NET Compact Framework rather than the full .NET Framework.</span></span> <span data-ttu-id="0749f-107">Функции языка, существующие только в полной .NET Framework, отключены.</span><span class="sxs-lookup"><span data-stu-id="0749f-107">Language functionality that is present only in the full .NET Framework is disabled.</span></span>

<span data-ttu-id="0749f-108">Параметр `-netcf` предназначен для использования с [-сдкпас](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span><span class="sxs-lookup"><span data-stu-id="0749f-108">The `-netcf` option is designed to be used with [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span></span> <span data-ttu-id="0749f-109">Функции языка, отключенные `-netcf`, — это те же языковые возможности, которые отсутствуют в файлах, предназначенных для `-sdkpath`.</span><span class="sxs-lookup"><span data-stu-id="0749f-109">The language features disabled by `-netcf` are the same language features not present in the files targeted with `-sdkpath`.</span></span>

> [!NOTE]
> <span data-ttu-id="0749f-110">Параметр `-netcf` недоступен в среде разработки Visual Studio; Он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="0749f-110">The `-netcf` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="0749f-111">Параметр `-netcf` задается при загрузке проекта Visual Basic устройства.</span><span class="sxs-lookup"><span data-stu-id="0749f-111">The `-netcf` option is set when a Visual Basic device project is loaded.</span></span>

<span data-ttu-id="0749f-112">Параметр `-netcf` изменяет следующие языковые функции:</span><span class="sxs-lookup"><span data-stu-id="0749f-112">The `-netcf` option changes the following language features:</span></span>

- <span data-ttu-id="0749f-113">Ключевое слово [End \<keyword >](../../../visual-basic/language-reference/statements/end-keyword-statement.md) , которое завершает выполнение программы, отключено.</span><span class="sxs-lookup"><span data-stu-id="0749f-113">The [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) keyword, which terminates execution of a program, is disabled.</span></span> <span data-ttu-id="0749f-114">Следующая программа компилирует и выполняется без `-netcf`, но при этом происходит сбой во время компиляции с `-netcf`.</span><span class="sxs-lookup"><span data-stu-id="0749f-114">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]

- <span data-ttu-id="0749f-115">Позднее связывание во всех формах отключено.</span><span class="sxs-lookup"><span data-stu-id="0749f-115">Late binding, in all forms, is disabled.</span></span> <span data-ttu-id="0749f-116">Ошибки времени компиляции генерируются при обнаружении сценариев с поздним связыванием.</span><span class="sxs-lookup"><span data-stu-id="0749f-116">Compile-time errors are generated when recognized late-binding scenarios are encountered.</span></span> <span data-ttu-id="0749f-117">Следующая программа компилирует и выполняется без `-netcf`, но при этом происходит сбой во время компиляции с `-netcf`.</span><span class="sxs-lookup"><span data-stu-id="0749f-117">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]

- <span data-ttu-id="0749f-118">Модификаторы [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md)и [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) отключены.</span><span class="sxs-lookup"><span data-stu-id="0749f-118">The [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), and [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modifiers are disabled.</span></span> <span data-ttu-id="0749f-119">Синтаксис инструкции [Declare](../../../visual-basic/language-reference/statements/declare-statement.md) также изменяется на `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span><span class="sxs-lookup"><span data-stu-id="0749f-119">The syntax of the [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) statement is also modified to `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span></span> <span data-ttu-id="0749f-120">В следующем коде показан результат компиляции `-netcf`.</span><span class="sxs-lookup"><span data-stu-id="0749f-120">The following code shows the effect of `-netcf` on a compilation.</span></span>

  [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]

- <span data-ttu-id="0749f-121">При использовании ключевых слов Visual Basic 6,0, которые были удалены из Visual Basic, возникает другая ошибка при использовании `-netcf`.</span><span class="sxs-lookup"><span data-stu-id="0749f-121">Using Visual Basic 6.0 keywords that were removed from Visual Basic generates a different error when `-netcf` is used.</span></span> <span data-ttu-id="0749f-122">Это влияет на сообщения об ошибках для следующих ключевых слов:</span><span class="sxs-lookup"><span data-stu-id="0749f-122">This affects the error messages for the following keywords:</span></span>

  - `Open`

  - `Close`

  - `Put`

  - `Print`

  - `Write`

  - `Input`

  - `Lock`

  - `Unlock`

  - `Seek`

  - `Width`

  - `Name`

  - `FreeFile`

  - `EOF`

  - `Loc`

  - `LOF`

  - `Line`

## <a name="example"></a><span data-ttu-id="0749f-123">Пример</span><span class="sxs-lookup"><span data-stu-id="0749f-123">Example</span></span>

<span data-ttu-id="0749f-124">Следующий код компилирует `Myfile.vb` с .NET Compact Framework, используя версии mscorlib. dll и Microsoft. VisualBasic. dll, найденные в .NET Compact Framework каталоге установки по умолчанию на диске C.</span><span class="sxs-lookup"><span data-stu-id="0749f-124">The following code compiles `Myfile.vb` with the .NET Compact Framework, using the versions of mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the .NET Compact Framework on the C drive.</span></span> <span data-ttu-id="0749f-125">Как правило, используется самая последняя версия .NET Compact Framework.</span><span class="sxs-lookup"><span data-stu-id="0749f-125">Typically, you would use the most recent version of the .NET Compact Framework.</span></span>

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a><span data-ttu-id="0749f-126">См. также</span><span class="sxs-lookup"><span data-stu-id="0749f-126">See also</span></span>

- [<span data-ttu-id="0749f-127">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="0749f-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="0749f-128">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="0749f-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="0749f-129">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="0749f-129">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
