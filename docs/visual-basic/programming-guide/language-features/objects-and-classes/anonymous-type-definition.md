---
title: Определение анонимного типа (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
ms.openlocfilehash: 179fb9773fde2631666498d54894037b2bbfd087
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649624"
---
# <a name="anonymous-type-definition-visual-basic"></a>Определение анонимного типа (Visual Basic)
В ответ на объявление экземпляра анонимного типа компилятор создает определение нового класса, который содержит указанные свойства для типа.  
  
## <a name="compiler-generated-code"></a>Созданный компилятором код  
 Следующие определения `product`, компилятор создает определение нового класса, который содержит свойства `Name`, `Price`, и `OnHand`.  
  
 [!code-vb[VbVbalrAnonymousTypes#25](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_1.vb)]  
  
 Определение класса содержит определения свойств следующего вида. Обратите внимание, что имеется не `Set` метод для ключевых свойств. Значения ключевых свойств доступны только для чтения.  
  
```vb  
Public Class $Anonymous1  
    Private _name As String  
    Private _price As Double  
    Private _onHand As Integer  
     Public ReadOnly Property Name() As String  
        Get  
            Return _name  
        End Get  
    End Property  
  
    Public ReadOnly Property Price() As Double  
        Get  
            Return _price  
        End Get  
    End Property  
  
    Public Property OnHand() As Integer  
        Get  
            Return _onHand  
        End Get  
        Set(ByVal Value As Integer)  
            _onHand = Value  
        End Set  
    End Property  
  
End Class  
```  
  
 Кроме того определения анонимного типа содержат конструктор по умолчанию. Конструкторы, требующие параметры не допускаются.  
  
 Если в объявлении анонимного типа содержит по крайней мере одно ключевое свойство, определение переопределяет три члена, унаследованные от <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, и <xref:System.Object.ToString%2A>. Если ключевые свойства не объявлены, только <xref:System.Object.ToString%2A> переопределяется. Переопределение предоставляет следующие функциональные возможности:  
  
-   `Equals` Возвращает `True` , если два экземпляра анонимного типа являются одним экземпляром или при соблюдении следующих условий:  
  
    -   Они имеют одинаковое число свойств.  
  
    -   Свойства объявляются в том же порядке, с теми же именами и те же возвращаемые типы. Имя сравнения регистр не учитывается.  
  
    -   По крайней мере одно из свойств является ключевым свойством и `Key` те же свойства применяется ключевое слово.  
  
    -   Сравнение каждой соответствующей пары ключевых свойств возвращает `True`.  
  
     Например, в следующих примерах `Equals` возвращает `True` только для `employee01` и `employee08`. Комментарий перед каждой строки определяет причины, почему нового экземпляра не соответствует `employee01`.  
  
     [!code-vb[VbVbalrAnonymousTypes#24](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_2.vb)]  
  
-   `GetHashcode` предоставляет соответствующим образом уникальный алгоритм GetHashCode. Алгоритм использует только ключевые свойства для вычисления хэш-код.  
  
-   `ToString` Возвращает строку объединены значения свойств, как показано в следующем примере. Включены ключ и неключевые свойства.  
  
     [!code-vb[VbVbalrAnonymousTypes#29](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_3.vb)]  
  
 Явно именованные свойства анонимного типа не могут конфликтовать с этими созданными методами. Другими словами, нельзя использовать `.Equals`, `.GetHashCode`, или `.ToString` для имени свойства.  
  
 Определения анонимных типов, включающих по крайней мере одно ключевое свойство, также реализуют <xref:System.IEquatable%601?displayProperty=nameWithType> интерфейса, где `T` тип анонимного типа.  
  
> [!NOTE]
>  Объявления анонимного типа создают одного анонимного типа только в том случае, если они встречаются в той же сборке, их свойства имеют те же имена и те же выводимые типы, свойства объявлены в том же порядке и те же свойства помечены как ключевые свойства.  
  
## <a name="see-also"></a>См. также  
 [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
