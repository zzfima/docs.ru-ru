---
title: -optionexplicit
ms.date: 07/20/2015
f1_keywords:
- /optionexplicit
- -optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
ms.openlocfilehash: 37ccd14dae0ebba2535185f2646e312d9bb70390
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266733"
---
# <a name="-optionexplicit"></a><span data-ttu-id="ec631-102">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="ec631-102">-optionexplicit</span></span>
<span data-ttu-id="ec631-103">Вызывает сообщение об ошибках компилятора, если переменные не объявляются до их использования.</span><span class="sxs-lookup"><span data-stu-id="ec631-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec631-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec631-104">Syntax</span></span>  
  
```console  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="ec631-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="ec631-105">Arguments</span></span>  
 <span data-ttu-id="ec631-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="ec631-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="ec631-107">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="ec631-107">Optional.</span></span> <span data-ttu-id="ec631-108">Указать, `-optionexplicit+` чтобы требовать явного объявления переменных.</span><span class="sxs-lookup"><span data-stu-id="ec631-108">Specify `-optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="ec631-109">Опция `-optionexplicit+` по умолчанию и `-optionexplicit`такая же, как .</span><span class="sxs-lookup"><span data-stu-id="ec631-109">The `-optionexplicit+` option is the default and is the same as `-optionexplicit`.</span></span> <span data-ttu-id="ec631-110">Опция `-optionexplicit-` позволяет неявно декларирование переменных.</span><span class="sxs-lookup"><span data-stu-id="ec631-110">The `-optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec631-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="ec631-111">Remarks</span></span>  
 <span data-ttu-id="ec631-112">Если файл исходного кода содержит [заявление Option Explicit,](../../../visual-basic/language-reference/statements/option-explicit-statement.md)заявление переопределяет настройки `-optionexplicit` компилятора командной строки.</span><span class="sxs-lookup"><span data-stu-id="ec631-112">If the source code file contains an [Option Explicit statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md), the statement overrides the `-optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="ec631-113">Установить -опцию в Visual Studio IDE</span><span class="sxs-lookup"><span data-stu-id="ec631-113">To set -optionexplicit in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="ec631-114">Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="ec631-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="ec631-115">В меню **Проект** выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="ec631-115">On the **Project** menu, click **Properties**.</span></span>
  
2. <span data-ttu-id="ec631-116">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="ec631-116">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="ec631-117">Измените значение в поле **Option Explicit.**</span><span class="sxs-lookup"><span data-stu-id="ec631-117">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec631-118">Пример</span><span class="sxs-lookup"><span data-stu-id="ec631-118">Example</span></span>  
 <span data-ttu-id="ec631-119">Следующий код компилируется при `-optionexplicit-` использовании.</span><span class="sxs-lookup"><span data-stu-id="ec631-119">The following code compiles when `-optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="ec631-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ec631-120">See also</span></span>

- [<span data-ttu-id="ec631-121">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="ec631-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="ec631-122">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="ec631-122">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="ec631-123">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="ec631-123">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="ec631-124">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="ec631-124">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="ec631-125">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="ec631-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="ec631-126">Оператор Option Explicit</span><span class="sxs-lookup"><span data-stu-id="ec631-126">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="ec631-127">Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"</span><span class="sxs-lookup"><span data-stu-id="ec631-127">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
