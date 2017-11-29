---
title: /optioncompare
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: /optioncompare
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a6f602e0b0b23345bf1f5aae843bd44bd2642bc9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="optioncompare"></a><span data-ttu-id="d0451-102">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="d0451-102">/optioncompare</span></span>
<span data-ttu-id="d0451-103">Задает способ сравнения строк.</span><span class="sxs-lookup"><span data-stu-id="d0451-103">Specifies how string comparisons are made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0451-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0451-104">Syntax</span></span>  
  
```  
/optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a><span data-ttu-id="d0451-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="d0451-105">Remarks</span></span>  
 <span data-ttu-id="d0451-106">Можно указать `/optioncompare` в одну из двух форм: `/optioncompare:binary` использовать двоичное сравнение строк, и `/optioncompare:text` использовать текстовое сравнение строк.</span><span class="sxs-lookup"><span data-stu-id="d0451-106">You can specify `/optioncompare` in one of two forms: `/optioncompare:binary` to use binary string comparisons, and `/optioncompare:text` to use text string comparisons.</span></span> <span data-ttu-id="d0451-107">По умолчанию компилятор использует `/optioncompare:binary`.</span><span class="sxs-lookup"><span data-stu-id="d0451-107">By default, the compiler uses `/optioncompare:binary`.</span></span>  
  
 <span data-ttu-id="d0451-108">В Microsoft Windows используется кодовая страница определяет двоичный порядок сортировки.</span><span class="sxs-lookup"><span data-stu-id="d0451-108">In Microsoft Windows, the code page being used determines the binary sort order.</span></span> <span data-ttu-id="d0451-109">Двоичный порядок сортировки выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d0451-109">A typical binary sort order is as follows:</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="d0451-110">Сравнение текстовых строк основано на порядок сортировки текста без учета регистра, определяемого языком вашей системы.</span><span class="sxs-lookup"><span data-stu-id="d0451-110">Text-based string comparisons are based on a case-insensitive text sort order determined by your system's locale.</span></span> <span data-ttu-id="d0451-111">Порядок сортировки текста обычно выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d0451-111">A typical text sort order is as follows:</span></span>  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set-optioncompare-in-the-visual-studio-ide"></a><span data-ttu-id="d0451-112">Чтобы задать дополнительные в Интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d0451-112">To set /optioncompare in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="d0451-113">Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="d0451-113">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="d0451-114">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="d0451-114">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="d0451-115">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="d0451-115">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="d0451-116">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="d0451-116">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="d0451-117">Измените значение в **Option Compare** поле.</span><span class="sxs-lookup"><span data-stu-id="d0451-117">Modify the value in the **Option Compare** box.</span></span>  
  
### <a name="to-set-optioncompare-programmatically"></a><span data-ttu-id="d0451-118">Чтобы установить дополнительные программными средствами</span><span class="sxs-lookup"><span data-stu-id="d0451-118">To set /optioncompare programmatically</span></span>  
  
-   <span data-ttu-id="d0451-119">В разделе [Option Compare-оператор](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d0451-119">See [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0451-120">Пример</span><span class="sxs-lookup"><span data-stu-id="d0451-120">Example</span></span>  
 <span data-ttu-id="d0451-121">Следующий код компилирует `ProjFile.vb` и использует двоичное сравнение строк.</span><span class="sxs-lookup"><span data-stu-id="d0451-121">The following code compiles `ProjFile.vb` and uses binary string comparisons.</span></span>  
  
```  
vbc /optioncompare:binary projFile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d0451-122">См. также</span><span class="sxs-lookup"><span data-stu-id="d0451-122">See Also</span></span>  
 [<span data-ttu-id="d0451-123">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="d0451-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="d0451-124">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="d0451-124">/optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [<span data-ttu-id="d0451-125">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="d0451-125">/optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [<span data-ttu-id="d0451-126">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="d0451-126">/optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="d0451-127">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="d0451-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="d0451-128">Оператор Option Compare</span><span class="sxs-lookup"><span data-stu-id="d0451-128">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [<span data-ttu-id="d0451-129">Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"</span><span class="sxs-lookup"><span data-stu-id="d0451-129">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
