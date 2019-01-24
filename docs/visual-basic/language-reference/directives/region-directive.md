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
ms.openlocfilehash: db8063cf06ad0735bb4d9290c60548f7ff9af217
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611947"
---
# <a name="region-directive"></a><span data-ttu-id="515f0-102">Директива #Region</span><span class="sxs-lookup"><span data-stu-id="515f0-102">#Region Directive</span></span>
<span data-ttu-id="515f0-103">Сворачивает и скрывает разделы кода в файлах Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="515f0-103">Collapses and hides sections of code in Visual Basic files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="515f0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="515f0-104">Syntax</span></span>  

```vb
#Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a><span data-ttu-id="515f0-105">Части</span><span class="sxs-lookup"><span data-stu-id="515f0-105">Parts</span></span>  
  
|<span data-ttu-id="515f0-106">Термин</span><span class="sxs-lookup"><span data-stu-id="515f0-106">Term</span></span>|<span data-ttu-id="515f0-107">Определение</span><span class="sxs-lookup"><span data-stu-id="515f0-107">Definition</span></span>|  
|---|---|  
|`identifier_string`|<span data-ttu-id="515f0-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="515f0-108">Required.</span></span> <span data-ttu-id="515f0-109">Строка, которая выступает в качестве заголовка области, если он свернут.</span><span class="sxs-lookup"><span data-stu-id="515f0-109">String that acts as the title of a region when it is collapsed.</span></span> <span data-ttu-id="515f0-110">По умолчанию области свернуты.</span><span class="sxs-lookup"><span data-stu-id="515f0-110">Regions are collapsed by default.</span></span>|  
|`#End Region`|<span data-ttu-id="515f0-111">Завершает блок `#Region`.</span><span class="sxs-lookup"><span data-stu-id="515f0-111">Terminates the `#Region` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="515f0-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="515f0-112">Remarks</span></span>  
 <span data-ttu-id="515f0-113">Используйте директиву `#Region`, чтобы указать блок кода, который можно разворачивать и сворачивать с помощью возможности структурирования в редакторе кода Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="515f0-113">Use the `#Region` directive to specify a block of code to expand or collapse when using the outlining feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="515f0-114">Можно установить, или *вкладывать друг в друга*, регионы, в другие области, чтобы сгруппировать похожими областями.</span><span class="sxs-lookup"><span data-stu-id="515f0-114">You can place, or *nest*, regions within other regions to group similar regions together.</span></span>  
  
## <a name="example"></a><span data-ttu-id="515f0-115">Пример</span><span class="sxs-lookup"><span data-stu-id="515f0-115">Example</span></span>  
 <span data-ttu-id="515f0-116">В этом примере используется директива `#Region`.</span><span class="sxs-lookup"><span data-stu-id="515f0-116">This example uses the `#Region` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#4](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="515f0-117">См. также</span><span class="sxs-lookup"><span data-stu-id="515f0-117">See also</span></span>
- [<span data-ttu-id="515f0-118">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="515f0-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="515f0-119">Структура</span><span class="sxs-lookup"><span data-stu-id="515f0-119">Outlining</span></span>](/visualstudio/ide/outlining)
- [<span data-ttu-id="515f0-120">Практическое руководство. Сворачивание и скрытие частей кода</span><span class="sxs-lookup"><span data-stu-id="515f0-120">How to: Collapse and Hide Sections of Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)
