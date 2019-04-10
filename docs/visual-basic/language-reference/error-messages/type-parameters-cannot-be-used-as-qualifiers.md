---
title: Параметры типа нельзя использовать в качестве квалификаторов
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: ba7348ae50965ffcf2719b20934451916c8fa95a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59296359"
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a><span data-ttu-id="20287-102">Параметры типа нельзя использовать в качестве квалификаторов</span><span class="sxs-lookup"><span data-stu-id="20287-102">Type parameters cannot be used as qualifiers</span></span>
<span data-ttu-id="20287-103">Программный элемент квалифицируется с помощью уточняющей строке, которая включает параметр типа.</span><span class="sxs-lookup"><span data-stu-id="20287-103">A programming element is qualified with a qualification string that includes a type parameter.</span></span>  
  
 <span data-ttu-id="20287-104">Параметр типа представляет требования для типа, который предоставляется при создании универсального типа.</span><span class="sxs-lookup"><span data-stu-id="20287-104">A type parameter represents a requirement for a type that is to be supplied when the generic type is constructed.</span></span> <span data-ttu-id="20287-105">Он не представляет конкретный определенный тип.</span><span class="sxs-lookup"><span data-stu-id="20287-105">It does not represent a specific defined type.</span></span> <span data-ttu-id="20287-106">Строка квалификации должна включать только те элементы, которые определены во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="20287-106">A qualification string must include only elements that are defined at compile time.</span></span>  
  
 <span data-ttu-id="20287-107">Следующие операторы могут привести к этой ошибке.</span><span class="sxs-lookup"><span data-stu-id="20287-107">The following statements can generate this error.</span></span>  
  
```  
Public Function checkText(Of c As System.Windows.Forms.Control)(  
    ByVal badText As String) As Boolean  
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.  
End Function  
```  
  
 <span data-ttu-id="20287-108">**Идентификатор ошибки:** BC32098</span><span class="sxs-lookup"><span data-stu-id="20287-108">**Error ID:** BC32098</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="20287-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="20287-109">To correct this error</span></span>  
  
1. <span data-ttu-id="20287-110">Удалите параметр типа из уточняющей строке или замените его определенного типа.</span><span class="sxs-lookup"><span data-stu-id="20287-110">Remove the type parameter from the qualification string, or replace it with a defined type.</span></span>  
  
2. <span data-ttu-id="20287-111">Если вам нужно использовать для поиска элемента программирования имен сконструированный тип, необходимо использовать дополнительную логику программы.</span><span class="sxs-lookup"><span data-stu-id="20287-111">If you need to use a constructed type to locate the programming element being qualified, you must use additional program logic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20287-112">См. также</span><span class="sxs-lookup"><span data-stu-id="20287-112">See also</span></span>

- [<span data-ttu-id="20287-113">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="20287-113">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="20287-114">Универсальные типы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="20287-114">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="20287-115">Type List</span><span class="sxs-lookup"><span data-stu-id="20287-115">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
