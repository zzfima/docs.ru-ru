---
title: "Параметры типа нельзя использовать в качестве квалификаторов"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords: BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 58be51e0c05750ee044f0287cde8db037718b4aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a><span data-ttu-id="b395a-102">Параметры типа нельзя использовать в качестве квалификаторов</span><span class="sxs-lookup"><span data-stu-id="b395a-102">Type parameters cannot be used as qualifiers</span></span>
<span data-ttu-id="b395a-103">Программный элемент квалифицировался уточняющей строки, которая содержит параметр типа.</span><span class="sxs-lookup"><span data-stu-id="b395a-103">A programming element is qualified with a qualification string that includes a type parameter.</span></span>  
  
 <span data-ttu-id="b395a-104">Представляет параметр типа является обязательным для типа, которое должно быть предоставлено при создании универсального типа.</span><span class="sxs-lookup"><span data-stu-id="b395a-104">A type parameter represents a requirement for a type that is to be supplied when the generic type is constructed.</span></span> <span data-ttu-id="b395a-105">Он не представляет конкретный определенный тип.</span><span class="sxs-lookup"><span data-stu-id="b395a-105">It does not represent a specific defined type.</span></span> <span data-ttu-id="b395a-106">Уточняющей строки должна включать только те элементы, которые определены во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="b395a-106">A qualification string must include only elements that are defined at compile time.</span></span>  
  
 <span data-ttu-id="b395a-107">Следующие операторы могут привести к этой ошибке.</span><span class="sxs-lookup"><span data-stu-id="b395a-107">The following statements can generate this error.</span></span>  
  
```  
Public Function checkText(Of c As System.Windows.Forms.Control)(  
    ByVal badText As String) As Boolean  
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.  
End Function  
```  
  
 <span data-ttu-id="b395a-108">**Идентификатор ошибки:** BC32098</span><span class="sxs-lookup"><span data-stu-id="b395a-108">**Error ID:** BC32098</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b395a-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="b395a-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="b395a-110">Удалите параметр типа из строки квалификации или замените его определенным типом.</span><span class="sxs-lookup"><span data-stu-id="b395a-110">Remove the type parameter from the qualification string, or replace it with a defined type.</span></span>  
  
2.  <span data-ttu-id="b395a-111">Если необходимо использовать для поиска элемента программирования имен сконструированный тип, необходимо использовать дополнительную логику программы.</span><span class="sxs-lookup"><span data-stu-id="b395a-111">If you need to use a constructed type to locate the programming element being qualified, you must use additional program logic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b395a-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b395a-112">See Also</span></span>  
 [<span data-ttu-id="b395a-113">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="b395a-113">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="b395a-114">Универсальные типы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b395a-114">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="b395a-115">Список типов</span><span class="sxs-lookup"><span data-stu-id="b395a-115">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
