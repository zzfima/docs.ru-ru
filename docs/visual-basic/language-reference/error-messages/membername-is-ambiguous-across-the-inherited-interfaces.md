---
title: '&#39;&lt;имя пользователя&gt; &#39; является неоднозначным к наследуемому интерфейсу &#39; &lt;имя_интерфейса1&gt; &#39; и &#39; &lt;имя_интерфейса2&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30685
- bc30685
helpviewer_keywords:
- BC30685
ms.assetid: 756add7a-23d5-4b4f-a48d-8297d6459c73
ms.openlocfilehash: 23d1a11bcee2a4faae40f2683d109d5820ee5f9c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="39ltmembernamegt39-is-ambiguous-across-the-inherited-interfaces-39ltinterfacename1gt39-and-39ltinterfacename2gt39"></a>&#39;&lt;имя пользователя&gt; &#39; является неоднозначным к наследуемому интерфейсу &#39; &lt;имя_интерфейса1&gt; &#39; и &#39; &lt;имя_интерфейса2&gt;&#39;
Этот интерфейс наследует нескольких интерфейсов два или более членов с тем же именем.  
  
 **Идентификатор ошибки:** BC30685  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Привести значение к базовому интерфейсу, который вы хотите использовать; Например:  
  
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
 [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
