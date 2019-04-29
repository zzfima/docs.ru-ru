---
title: Оператор Erase (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: bf3eb6476dc1485faeddab475f29e508175d3378
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638198"
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="6824a-102">Оператор Erase (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6824a-102">Erase Statement (Visual Basic)</span></span>
<span data-ttu-id="6824a-103">Используется для удаления переменных массива и освободить память, используемая для их элементов.</span><span class="sxs-lookup"><span data-stu-id="6824a-103">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6824a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6824a-104">Syntax</span></span>  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="6824a-105">Части</span><span class="sxs-lookup"><span data-stu-id="6824a-105">Parts</span></span>  
 `arraylist`  
 <span data-ttu-id="6824a-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="6824a-106">Required.</span></span> <span data-ttu-id="6824a-107">Список переменных массива.</span><span class="sxs-lookup"><span data-stu-id="6824a-107">List of array variables to be erased.</span></span> <span data-ttu-id="6824a-108">Переменные разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="6824a-108">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6824a-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="6824a-109">Remarks</span></span>  
 <span data-ttu-id="6824a-110">`Erase` Оператор может присутствовать только на уровне процедуры.</span><span class="sxs-lookup"><span data-stu-id="6824a-110">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="6824a-111">Это означает, что вы можете выпустить массивы внутри процедуры, но не на уровне класса или модуля.</span><span class="sxs-lookup"><span data-stu-id="6824a-111">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="6824a-112">`Erase` Инструкция эквивалентна присваиванию `Nothing` каждой переменной массива.</span><span class="sxs-lookup"><span data-stu-id="6824a-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6824a-113">Пример</span><span class="sxs-lookup"><span data-stu-id="6824a-113">Example</span></span>  
 <span data-ttu-id="6824a-114">В следующем примере используется `Erase` инструкцию, чтобы очистить два массива и освободить память (1000 и 100 элементов, соответственно).</span><span class="sxs-lookup"><span data-stu-id="6824a-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="6824a-115">`ReDim` Оператора затем присваивается новый экземпляр массива трехмерный массив.</span><span class="sxs-lookup"><span data-stu-id="6824a-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="6824a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6824a-116">See also</span></span>

- [<span data-ttu-id="6824a-117">Nothing</span><span class="sxs-lookup"><span data-stu-id="6824a-117">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="6824a-118">Оператор reDim</span><span class="sxs-lookup"><span data-stu-id="6824a-118">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
