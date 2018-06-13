---
title: Оператор Erase (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 317e2a7dc5facb08388f3a3e635734e4daed5eac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33601797"
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="4dc7d-102">Оператор Erase (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4dc7d-102">Erase Statement (Visual Basic)</span></span>
<span data-ttu-id="4dc7d-103">Используется для выпуска переменных массива и освобождения памяти, используемой для их элементов.</span><span class="sxs-lookup"><span data-stu-id="4dc7d-103">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dc7d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4dc7d-104">Syntax</span></span>  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="4dc7d-105">Части</span><span class="sxs-lookup"><span data-stu-id="4dc7d-105">Parts</span></span>  
 `arraylist`  
 <span data-ttu-id="4dc7d-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="4dc7d-106">Required.</span></span> <span data-ttu-id="4dc7d-107">Список переменных массива для удаления.</span><span class="sxs-lookup"><span data-stu-id="4dc7d-107">List of array variables to be erased.</span></span> <span data-ttu-id="4dc7d-108">Переменные разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="4dc7d-108">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4dc7d-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="4dc7d-109">Remarks</span></span>  
 <span data-ttu-id="4dc7d-110">`Erase` Оператор может присутствовать только на уровне процедуры.</span><span class="sxs-lookup"><span data-stu-id="4dc7d-110">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="4dc7d-111">Это означает, что освобождением массивы внутри процедуры, но не на уровне класса или модуля.</span><span class="sxs-lookup"><span data-stu-id="4dc7d-111">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="4dc7d-112">`Erase` Оператор эквивалентен назначение `Nothing` каждой переменной массива.</span><span class="sxs-lookup"><span data-stu-id="4dc7d-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4dc7d-113">Пример</span><span class="sxs-lookup"><span data-stu-id="4dc7d-113">Example</span></span>  
 <span data-ttu-id="4dc7d-114">В следующем примере используется `Erase` инструкции для удаления двух массивов и высвобождения памяти (1000 и 100 элементов, соответственно).</span><span class="sxs-lookup"><span data-stu-id="4dc7d-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="4dc7d-115">`ReDim` Оператора затем присваивается новый экземпляр массива трехмерного массива.</span><span class="sxs-lookup"><span data-stu-id="4dc7d-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/erase-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4dc7d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4dc7d-116">See Also</span></span>  
 [<span data-ttu-id="4dc7d-117">Nothing</span><span class="sxs-lookup"><span data-stu-id="4dc7d-117">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)  
 [<span data-ttu-id="4dc7d-118">Оператор reDim</span><span class="sxs-lookup"><span data-stu-id="4dc7d-118">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
