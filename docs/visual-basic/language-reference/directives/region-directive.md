---
title: "#Указание области | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Region
- vb.#Region
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
caps.latest.revision: 14
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
ms.openlocfilehash: 86b8e9ce99a8c12e290f5efdc5a5c4da57f350d9
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="region-directive"></a>#<span data-ttu-id="28ae8-102">Указание области</span><span class="sxs-lookup"><span data-stu-id="28ae8-102">Region Directive</span></span>
<span data-ttu-id="28ae8-103">Сворачивает и скрывает разделы кода в файлах Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="28ae8-103">Collapses and hides sections of code in Visual Basic files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28ae8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="28ae8-104">Syntax</span></span>  
  
```  
  
      #Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a><span data-ttu-id="28ae8-105">Части</span><span class="sxs-lookup"><span data-stu-id="28ae8-105">Parts</span></span>  
  
|<span data-ttu-id="28ae8-106">Термин</span><span class="sxs-lookup"><span data-stu-id="28ae8-106">Term</span></span>|<span data-ttu-id="28ae8-107">Определение</span><span class="sxs-lookup"><span data-stu-id="28ae8-107">Definition</span></span>|  
|---|---|  
|`identifier_string`|<span data-ttu-id="28ae8-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="28ae8-108">Required.</span></span> <span data-ttu-id="28ae8-109">Строка, которая выступает в качестве заголовка области, если он свернут.</span><span class="sxs-lookup"><span data-stu-id="28ae8-109">String that acts as the title of a region when it is collapsed.</span></span> <span data-ttu-id="28ae8-110">По умолчанию области свернуты.</span><span class="sxs-lookup"><span data-stu-id="28ae8-110">Regions are collapsed by default.</span></span>|  
|`#End Region`|<span data-ttu-id="28ae8-111">Завершает блок `#Region`.</span><span class="sxs-lookup"><span data-stu-id="28ae8-111">Terminates the `#Region` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28ae8-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="28ae8-112">Remarks</span></span>  
 <span data-ttu-id="28ae8-113">Используйте директиву `#Region`, чтобы указать блок кода, который можно разворачивать и сворачивать с помощью функции структурирования в редакторе кода Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="28ae8-113">Use the `#Region` directive to specify a block of code to expand or collapse when using the outlining feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="28ae8-114">Можно поместить или *вложить*, регионов для группировки с аналогичными областями вместе с другими областями.</span><span class="sxs-lookup"><span data-stu-id="28ae8-114">You can place, or *nest*, regions within other regions to group similar regions together.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28ae8-115">Пример</span><span class="sxs-lookup"><span data-stu-id="28ae8-115">Example</span></span>  
 <span data-ttu-id="28ae8-116">В этом примере используется директива `#Region`.</span><span class="sxs-lookup"><span data-stu-id="28ae8-116">This example uses the `#Region` directive.</span></span>  
  
 <span data-ttu-id="28ae8-117">[!code-vb[VbVbalrConditionalComp&#4;](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="28ae8-117">[!code-vb[VbVbalrConditionalComp#4](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28ae8-118">См. также</span><span class="sxs-lookup"><span data-stu-id="28ae8-118">See Also</span></span>  
 <span data-ttu-id="28ae8-119">[#If... Then... #Else директивы](../../../visual-basic/language-reference/directives/if-then-else-directives.md) </span><span class="sxs-lookup"><span data-stu-id="28ae8-119">[#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) </span></span>  
<span data-ttu-id="28ae8-120"> [Структурирование](https://docs.microsoft.com/visualstudio/ide/outlining) </span><span class="sxs-lookup"><span data-stu-id="28ae8-120"> [Outlining](https://docs.microsoft.com/visualstudio/ide/outlining) </span></span>  
<span data-ttu-id="28ae8-121"> [Практическое руководство. Сворачивание и скрытие частей кода](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)</span><span class="sxs-lookup"><span data-stu-id="28ae8-121"> [How to: Collapse and Hide Sections of Code](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)</span></span>
