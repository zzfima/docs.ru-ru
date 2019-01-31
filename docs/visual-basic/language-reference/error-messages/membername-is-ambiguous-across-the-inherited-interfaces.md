---
title: Член <membername> является неоднозначным в наследуемых интерфейсах <interfacename1> и <interfacename2>
ms.date: 07/20/2015
f1_keywords:
- vbc30685
- bc30685
helpviewer_keywords:
- BC30685
ms.assetid: 756add7a-23d5-4b4f-a48d-8297d6459c73
ms.openlocfilehash: 1548c9894d476cc4b92d6581362d309e7b4d00d4
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55265001"
---
# <a name="membername-is-ambiguous-across-the-inherited-interfaces-interfacename1-and-interfacename2"></a>"\<имя_члена >" является неоднозначным в наследуемых интерфейсах\<имя_интерфейса1 > "и"\<имя_интерфейса2 > "
Этот интерфейс наследует два или несколько членов с таким именем несколько интерфейсов.  
  
 **Идентификатор ошибки:** BC30685  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Приведение значения к базовому интерфейсу, который вы хотите использовать; Например:  
  
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
  
## <a name="see-also"></a>См. также
- [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
