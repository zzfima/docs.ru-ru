---
title: "Дополнительные | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optioncompare
dev_langs:
- VB
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
caps.latest.revision: 17
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
ms.openlocfilehash: c9512427cda0b6a3bcb0c1fe338b47ff9f779d19
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="optioncompare"></a><span data-ttu-id="b731d-102">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="b731d-102">/optioncompare</span></span>
<span data-ttu-id="b731d-103">Задает способ сравнения строк.</span><span class="sxs-lookup"><span data-stu-id="b731d-103">Specifies how string comparisons are made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b731d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b731d-104">Syntax</span></span>  
  
```  
/optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a><span data-ttu-id="b731d-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="b731d-105">Remarks</span></span>  
 <span data-ttu-id="b731d-106">Можно указать `/optioncompare` в одну из двух форм: `/optioncompare:binary` использовать двоичное сравнение строк, и `/optioncompare:text` использовать текстовое сравнение строк.</span><span class="sxs-lookup"><span data-stu-id="b731d-106">You can specify `/optioncompare` in one of two forms: `/optioncompare:binary` to use binary string comparisons, and `/optioncompare:text` to use text string comparisons.</span></span> <span data-ttu-id="b731d-107">По умолчанию компилятор использует `/optioncompare:binary`.</span><span class="sxs-lookup"><span data-stu-id="b731d-107">By default, the compiler uses `/optioncompare:binary`.</span></span>  
  
 <span data-ttu-id="b731d-108">В Microsoft Windows используется кодовая страница определяет двоичный порядок сортировки.</span><span class="sxs-lookup"><span data-stu-id="b731d-108">In Microsoft Windows, the code page being used determines the binary sort order.</span></span> <span data-ttu-id="b731d-109">Двоичный порядок сортировки выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b731d-109">A typical binary sort order is as follows:</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="b731d-110">Сравнение текстовых строк основано на порядке сортировки текста без учета регистра определяются языком вашей системы.</span><span class="sxs-lookup"><span data-stu-id="b731d-110">Text-based string comparisons are based on a case-insensitive text sort order determined by your system's locale.</span></span> <span data-ttu-id="b731d-111">Порядок сортировки текста обычно выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b731d-111">A typical text sort order is as follows:</span></span>  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set-optioncompare-in-the-visual-studio-ide"></a><span data-ttu-id="b731d-112">Чтобы задать дополнительные в Интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b731d-112">To set /optioncompare in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="b731d-113">Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="b731d-113">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="b731d-114">На **проекта** меню, щелкните **свойства**.</span><span class="sxs-lookup"><span data-stu-id="b731d-114">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="b731d-115">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="b731d-115">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="b731d-116">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="b731d-116">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="b731d-117">Измените значение в **Option Compare** поле.</span><span class="sxs-lookup"><span data-stu-id="b731d-117">Modify the value in the **Option Compare** box.</span></span>  
  
### <a name="to-set-optioncompare-programmatically"></a><span data-ttu-id="b731d-118">Чтобы установить дополнительные программными средствами</span><span class="sxs-lookup"><span data-stu-id="b731d-118">To set /optioncompare programmatically</span></span>  
  
-   <span data-ttu-id="b731d-119">В разделе [Option Compare-оператор](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b731d-119">See [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b731d-120">Пример</span><span class="sxs-lookup"><span data-stu-id="b731d-120">Example</span></span>  
 <span data-ttu-id="b731d-121">Следующий код компилирует P`rojFile.vb` и использует сравнения двоичных строк.</span><span class="sxs-lookup"><span data-stu-id="b731d-121">The following code compiles P`rojFile.vb` and uses binary string comparisons.</span></span>  
  
```  
vbc /optioncompare:binary projFile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b731d-122">См. также</span><span class="sxs-lookup"><span data-stu-id="b731d-122">See Also</span></span>  
 <span data-ttu-id="b731d-123">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="b731d-123">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="b731d-124"> [/ optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span><span class="sxs-lookup"><span data-stu-id="b731d-124"> [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span></span>  
<span data-ttu-id="b731d-125"> [Дополнительные сведения](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span><span class="sxs-lookup"><span data-stu-id="b731d-125"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span></span>  
<span data-ttu-id="b731d-126"> [/ optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span><span class="sxs-lookup"><span data-stu-id="b731d-126"> [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span></span>  
<span data-ttu-id="b731d-127"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="b731d-127"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="b731d-128"> [Оператор Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b731d-128"> [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md) </span></span>  
<span data-ttu-id="b731d-129"> [Страница "Параметры Visual Basic по умолчанию", папка "Проекты", диалоговое окно "Параметры"](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="b731d-129"> [Visual Basic Defaults, Projects, Options Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>
