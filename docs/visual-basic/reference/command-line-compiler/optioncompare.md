---
title: -optioncompare
ms.date: 07/20/2015
f1_keywords:
- /optioncompare
- -optioncompare
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1906710ef10634187782f9355146dfa7ccb7748
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-optioncompare"></a><span data-ttu-id="97f0d-102">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="97f0d-102">-optioncompare</span></span>
<span data-ttu-id="97f0d-103">Задает способ сравнения строк.</span><span class="sxs-lookup"><span data-stu-id="97f0d-103">Specifies how string comparisons are made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97f0d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="97f0d-104">Syntax</span></span>  
  
```  
-optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a><span data-ttu-id="97f0d-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="97f0d-105">Remarks</span></span>  
 <span data-ttu-id="97f0d-106">Можно указать `-optioncompare` в одну из двух форм: `-optioncompare:binary` использовать двоичное сравнение строк, и `-optioncompare:text` использовать текстовое сравнение строк.</span><span class="sxs-lookup"><span data-stu-id="97f0d-106">You can specify `-optioncompare` in one of two forms: `-optioncompare:binary` to use binary string comparisons, and `-optioncompare:text` to use text string comparisons.</span></span> <span data-ttu-id="97f0d-107">По умолчанию компилятор использует `-optioncompare:binary`.</span><span class="sxs-lookup"><span data-stu-id="97f0d-107">By default, the compiler uses `-optioncompare:binary`.</span></span>  
  
 <span data-ttu-id="97f0d-108">В Microsoft Windows текущая кодовая страница определяет двоичный порядок сортировки.</span><span class="sxs-lookup"><span data-stu-id="97f0d-108">In Microsoft Windows, the current code page determines the binary sort order.</span></span> <span data-ttu-id="97f0d-109">Двоичный порядок сортировки выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="97f0d-109">A typical binary sort order is as follows:</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="97f0d-110">Сравнение текстовых строк основано на порядок сортировки текста без учета регистра, определяемого языком вашей системы.</span><span class="sxs-lookup"><span data-stu-id="97f0d-110">Text-based string comparisons are based on a case-insensitive text sort order determined by your system's locale.</span></span> <span data-ttu-id="97f0d-111">Порядок сортировки текста обычно выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="97f0d-111">A typical text sort order is as follows:</span></span>  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set--optioncompare-in-the-visual-studio-ide"></a><span data-ttu-id="97f0d-112">Чтобы задать - optioncompare в Интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="97f0d-112">To set -optioncompare in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="97f0d-113">Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="97f0d-113">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="97f0d-114">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="97f0d-114">On the **Project** menu, click **Properties**.</span></span>   
  
2.  <span data-ttu-id="97f0d-115">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="97f0d-115">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="97f0d-116">Измените значение в **Option Compare** поле.</span><span class="sxs-lookup"><span data-stu-id="97f0d-116">Modify the value in the **Option Compare** box.</span></span>  
  
### <a name="to-set--optioncompare-programmatically"></a><span data-ttu-id="97f0d-117">Установка - optioncompare программным способом</span><span class="sxs-lookup"><span data-stu-id="97f0d-117">To set -optioncompare programmatically</span></span>  
  
-   <span data-ttu-id="97f0d-118">В разделе [Option Compare-оператор](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="97f0d-118">See [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="97f0d-119">Пример</span><span class="sxs-lookup"><span data-stu-id="97f0d-119">Example</span></span>  
 <span data-ttu-id="97f0d-120">Следующий код компилирует `ProjFile.vb` и использует двоичное сравнение строк.</span><span class="sxs-lookup"><span data-stu-id="97f0d-120">The following code compiles `ProjFile.vb` and uses binary string comparisons.</span></span>  
  
```console
vbc -optioncompare:binary projFile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="97f0d-121">См. также</span><span class="sxs-lookup"><span data-stu-id="97f0d-121">See Also</span></span>  
 [<span data-ttu-id="97f0d-122">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="97f0d-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="97f0d-123">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="97f0d-123">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [<span data-ttu-id="97f0d-124">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="97f0d-124">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [<span data-ttu-id="97f0d-125">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="97f0d-125">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="97f0d-126">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="97f0d-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="97f0d-127">Оператор Option Compare</span><span class="sxs-lookup"><span data-stu-id="97f0d-127">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [<span data-ttu-id="97f0d-128">Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"</span><span class="sxs-lookup"><span data-stu-id="97f0d-128">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
