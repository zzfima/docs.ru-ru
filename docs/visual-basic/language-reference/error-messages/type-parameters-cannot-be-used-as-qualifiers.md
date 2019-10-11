---
title: Параметры типа нельзя использовать в качестве квалификаторов
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: 3ff4b189539bf119351a94dabadd596c336ac723
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250327"
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a><span data-ttu-id="2f2b3-102">Параметры типа нельзя использовать в качестве квалификаторов</span><span class="sxs-lookup"><span data-stu-id="2f2b3-102">Type parameters cannot be used as qualifiers</span></span>

<span data-ttu-id="2f2b3-103">Элемент программирования дополняется уточняющей строкой, включающей параметр типа.</span><span class="sxs-lookup"><span data-stu-id="2f2b3-103">A programming element is qualified with a qualification string that includes a type parameter.</span></span>

<span data-ttu-id="2f2b3-104">Параметр типа представляет требование для типа, который должен предоставляться при создании универсального типа.</span><span class="sxs-lookup"><span data-stu-id="2f2b3-104">A type parameter represents a requirement for a type that is to be supplied when the generic type is constructed.</span></span> <span data-ttu-id="2f2b3-105">Он не представляет определенный определенный тип.</span><span class="sxs-lookup"><span data-stu-id="2f2b3-105">It does not represent a specific defined type.</span></span> <span data-ttu-id="2f2b3-106">Уточняющая строка должна включать только те элементы, которые определены во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="2f2b3-106">A qualification string must include only elements that are defined at compile time.</span></span>

<span data-ttu-id="2f2b3-107">Следующий код может вызвать эту ошибку:</span><span class="sxs-lookup"><span data-stu-id="2f2b3-107">The following code can generate this error:</span></span>

```vb  
Public Function CheckText(Of c As System.Windows.Forms.Control)(
    badText As String) As Boolean
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.
End Function  
```  
  
 <span data-ttu-id="2f2b3-108">**Идентификатор ошибки:** BC32098</span><span class="sxs-lookup"><span data-stu-id="2f2b3-108">**Error ID:** BC32098</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2f2b3-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="2f2b3-109">To correct this error</span></span>  
  
1. <span data-ttu-id="2f2b3-110">Удалите параметр типа из строки квалификации или замените его определенным типом.</span><span class="sxs-lookup"><span data-stu-id="2f2b3-110">Remove the type parameter from the qualification string, or replace it with a defined type.</span></span>  
  
2. <span data-ttu-id="2f2b3-111">Если необходимо использовать сконструированный тип для нахождение квалифицированного программного элемента, необходимо использовать дополнительную логику программы.</span><span class="sxs-lookup"><span data-stu-id="2f2b3-111">If you need to use a constructed type to locate the programming element being qualified, you must use additional program logic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f2b3-112">См. также</span><span class="sxs-lookup"><span data-stu-id="2f2b3-112">See also</span></span>

- [<span data-ttu-id="2f2b3-113">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="2f2b3-113">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="2f2b3-114">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2f2b3-114">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="2f2b3-115">Список типов</span><span class="sxs-lookup"><span data-stu-id="2f2b3-115">Type List</span></span>](../statements/type-list.md)
