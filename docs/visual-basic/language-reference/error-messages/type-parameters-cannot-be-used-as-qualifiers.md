---
title: Параметры типа нельзя использовать в качестве квалификаторов
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: 8ee0fd5822c22da090aa0abee679e2f68e0fc1d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659719"
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a><span data-ttu-id="b1a94-102">Параметры типа нельзя использовать в качестве квалификаторов</span><span class="sxs-lookup"><span data-stu-id="b1a94-102">Type parameters cannot be used as qualifiers</span></span>
<span data-ttu-id="b1a94-103">Программный элемент квалифицируется с помощью уточняющей строке, которая включает параметр типа.</span><span class="sxs-lookup"><span data-stu-id="b1a94-103">A programming element is qualified with a qualification string that includes a type parameter.</span></span>  
  
 <span data-ttu-id="b1a94-104">Параметр типа представляет требования для типа, который предоставляется при создании универсального типа.</span><span class="sxs-lookup"><span data-stu-id="b1a94-104">A type parameter represents a requirement for a type that is to be supplied when the generic type is constructed.</span></span> <span data-ttu-id="b1a94-105">Он не представляет конкретный определенный тип.</span><span class="sxs-lookup"><span data-stu-id="b1a94-105">It does not represent a specific defined type.</span></span> <span data-ttu-id="b1a94-106">Строка квалификации должна включать только те элементы, которые определены во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="b1a94-106">A qualification string must include only elements that are defined at compile time.</span></span>  
  
 <span data-ttu-id="b1a94-107">Следующие операторы могут привести к этой ошибке.</span><span class="sxs-lookup"><span data-stu-id="b1a94-107">The following statements can generate this error.</span></span>  
  
```  
Public Function checkText(Of c As System.Windows.Forms.Control)(  
    ByVal badText As String) As Boolean  
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.  
End Function  
```  
  
 <span data-ttu-id="b1a94-108">**Идентификатор ошибки:** BC32098</span><span class="sxs-lookup"><span data-stu-id="b1a94-108">**Error ID:** BC32098</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b1a94-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="b1a94-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="b1a94-110">Удалите параметр типа из уточняющей строке или замените его определенного типа.</span><span class="sxs-lookup"><span data-stu-id="b1a94-110">Remove the type parameter from the qualification string, or replace it with a defined type.</span></span>  
  
2.  <span data-ttu-id="b1a94-111">Если вам нужно использовать для поиска элемента программирования имен сконструированный тип, необходимо использовать дополнительную логику программы.</span><span class="sxs-lookup"><span data-stu-id="b1a94-111">If you need to use a constructed type to locate the programming element being qualified, you must use additional program logic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1a94-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b1a94-112">See also</span></span>
- [<span data-ttu-id="b1a94-113">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="b1a94-113">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="b1a94-114">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b1a94-114">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="b1a94-115">Список типов</span><span class="sxs-lookup"><span data-stu-id="b1a94-115">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
