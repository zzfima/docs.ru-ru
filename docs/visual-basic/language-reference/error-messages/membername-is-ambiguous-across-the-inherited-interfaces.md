---
title: Член <membername> является неоднозначным в наследуемых интерфейсах <interfacename1> и <interfacename2>
ms.date: 07/20/2015
f1_keywords:
- vbc30685
- bc30685
helpviewer_keywords:
- BC30685
ms.assetid: 756add7a-23d5-4b4f-a48d-8297d6459c73
ms.openlocfilehash: 4415608bcfca63b43b3d9ebf17ce622ccd418775
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921008"
---
# <a name="membername-is-ambiguous-across-the-inherited-interfaces-interfacename1-and-interfacename2"></a><span data-ttu-id="f107d-102">"\<имя_члена >" является неоднозначным в наследуемых интерфейсах\<имя_интерфейса1 > "и"\<имя_интерфейса2 > "</span><span class="sxs-lookup"><span data-stu-id="f107d-102">'\<membername>' is ambiguous across the inherited interfaces '\<interfacename1>' and '\<interfacename2>'</span></span>
<span data-ttu-id="f107d-103">Этот интерфейс наследует два или несколько членов с таким именем несколько интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="f107d-103">The interface inherits two or more members with the same name from multiple interfaces.</span></span>  
  
 <span data-ttu-id="f107d-104">**Идентификатор ошибки:** BC30685</span><span class="sxs-lookup"><span data-stu-id="f107d-104">**Error ID:** BC30685</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f107d-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="f107d-105">To correct this error</span></span>  
  
- <span data-ttu-id="f107d-106">Приведение значения к базовому интерфейсу, который вы хотите использовать; Например:</span><span class="sxs-lookup"><span data-stu-id="f107d-106">Cast the value to the base interface that you want to use; for example:</span></span>  
  
    ```  
    Interface Left  
        Sub MySub()  
    End Interface  
  
    Interface Right  
        Sub MySub()  
    End Interface  
  
    Interface LeftRight  
        Inherits Left, Right  
    End Interface  
  
    Module test  
        Sub Main()  
            Dim x As LeftRight  
            ' x.MySub()  'x is ambiguous.  
            CType(x, Left).MySub() ' Cast to base type.  
            CType(x, Right).MySub() ' Call the other base type.  
        End Sub  
    End Module  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f107d-107">См. также</span><span class="sxs-lookup"><span data-stu-id="f107d-107">See also</span></span>

- [<span data-ttu-id="f107d-108">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="f107d-108">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
