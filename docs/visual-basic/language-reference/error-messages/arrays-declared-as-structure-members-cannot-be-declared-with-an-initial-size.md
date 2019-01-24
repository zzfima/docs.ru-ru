---
title: Массивы, объявленные как члены структуры, не могут быть объявлены с указанием начального размера
ms.date: 07/20/2015
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
ms.openlocfilehash: 06e5e36f3e0522e0449c0ef9698f3a1b01b9cb5f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549071"
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="ff21a-102">Массивы, объявленные как члены структуры, не могут быть объявлены с указанием начального размера</span><span class="sxs-lookup"><span data-stu-id="ff21a-102">Arrays declared as structure members cannot be declared with an initial size</span></span>
<span data-ttu-id="ff21a-103">Массив в структуре объявлена с начальным размером.</span><span class="sxs-lookup"><span data-stu-id="ff21a-103">An array in a structure is declared with an initial size.</span></span> <span data-ttu-id="ff21a-104">Не удается инициализировать любой элемент структуры и объявить размер массива является одним из инициализации.</span><span class="sxs-lookup"><span data-stu-id="ff21a-104">You cannot initialize any structure element, and declaring an array size is one form of initialization.</span></span>  
  
 <span data-ttu-id="ff21a-105">**Идентификатор ошибки:** BC31043</span><span class="sxs-lookup"><span data-stu-id="ff21a-105">**Error ID:** BC31043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ff21a-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="ff21a-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="ff21a-107">Определите массив в структуре как динамический (без указания начального размера).</span><span class="sxs-lookup"><span data-stu-id="ff21a-107">Define the array in your structure as dynamic (no initial size).</span></span>  
  
2.  <span data-ttu-id="ff21a-108">Если вам требуется определенного размера массива, можно изменить размер динамического массива с [оператор ReDim](../../../visual-basic/language-reference/statements/redim-statement.md) когда ваш код выполняется.</span><span class="sxs-lookup"><span data-stu-id="ff21a-108">If you require a certain size of array, you can redimension a dynamic array with a [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md) when your code is running.</span></span> <span data-ttu-id="ff21a-109">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ff21a-109">The following example illustrates this.</span></span>  
  
    ```  
    Structure demoStruct  
        Public demoArray() As Integer  
    End Structure  
    Sub useStruct()  
        Dim struct As demoStruct  
        ReDim struct.demoArray(9)  
        Struct.demoArray(2) = 777  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ff21a-110">См. также</span><span class="sxs-lookup"><span data-stu-id="ff21a-110">See also</span></span>
- [<span data-ttu-id="ff21a-111">Массивы</span><span class="sxs-lookup"><span data-stu-id="ff21a-111">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="ff21a-112">Практическое руководство. Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="ff21a-112">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
