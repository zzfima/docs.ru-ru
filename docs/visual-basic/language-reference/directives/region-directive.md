---
title: '#Region-директива (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.Region
- vb.#Region
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword [Visual Basic]'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
ms.openlocfilehash: 204b53751fce4f9a3e038ae7c44634522d54657c
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "44035194"
---
# <a name="region-directive"></a><span data-ttu-id="da27b-102">Директива #Region</span><span class="sxs-lookup"><span data-stu-id="da27b-102">#Region Directive</span></span>
<span data-ttu-id="da27b-103">Сворачивает и скрывает разделы кода в файлах Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="da27b-103">Collapses and hides sections of code in Visual Basic files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da27b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da27b-104">Syntax</span></span>  

```vb
#Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a><span data-ttu-id="da27b-105">Части</span><span class="sxs-lookup"><span data-stu-id="da27b-105">Parts</span></span>  
  
|<span data-ttu-id="da27b-106">Термин</span><span class="sxs-lookup"><span data-stu-id="da27b-106">Term</span></span>|<span data-ttu-id="da27b-107">Определение</span><span class="sxs-lookup"><span data-stu-id="da27b-107">Definition</span></span>|  
|---|---|  
|`identifier_string`|<span data-ttu-id="da27b-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="da27b-108">Required.</span></span> <span data-ttu-id="da27b-109">Строка, которая выступает в качестве заголовка области, если он свернут.</span><span class="sxs-lookup"><span data-stu-id="da27b-109">String that acts as the title of a region when it is collapsed.</span></span> <span data-ttu-id="da27b-110">По умолчанию области свернуты.</span><span class="sxs-lookup"><span data-stu-id="da27b-110">Regions are collapsed by default.</span></span>|  
|`#End Region`|<span data-ttu-id="da27b-111">Завершает блок `#Region`.</span><span class="sxs-lookup"><span data-stu-id="da27b-111">Terminates the `#Region` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da27b-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="da27b-112">Remarks</span></span>  
 <span data-ttu-id="da27b-113">Используйте директиву `#Region`, чтобы указать блок кода, который можно разворачивать и сворачивать с помощью функции структурирования в редакторе кода Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="da27b-113">Use the `#Region` directive to specify a block of code to expand or collapse when using the outlining feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="da27b-114">Можно установить, или *вкладывать друг в друга*, регионы, в другие области, чтобы сгруппировать похожими областями.</span><span class="sxs-lookup"><span data-stu-id="da27b-114">You can place, or *nest*, regions within other regions to group similar regions together.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da27b-115">Пример</span><span class="sxs-lookup"><span data-stu-id="da27b-115">Example</span></span>  
 <span data-ttu-id="da27b-116">В этом примере используется директива `#Region`.</span><span class="sxs-lookup"><span data-stu-id="da27b-116">This example uses the `#Region` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#4](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="da27b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="da27b-117">See Also</span></span>  
 [<span data-ttu-id="da27b-118">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="da27b-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="da27b-119">Структура</span><span class="sxs-lookup"><span data-stu-id="da27b-119">Outlining</span></span>](/visualstudio/ide/outlining)  
 [<span data-ttu-id="da27b-120">Практическое руководство. Сворачивание и скрытие частей кода</span><span class="sxs-lookup"><span data-stu-id="da27b-120">How to: Collapse and Hide Sections of Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)
