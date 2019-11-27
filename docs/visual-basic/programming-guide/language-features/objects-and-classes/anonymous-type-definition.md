---
title: Определение анонимного типа
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
ms.openlocfilehash: f8ac26577a7fbef865605a7ecf643fa733b2c2c0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344920"
---
# <a name="anonymous-type-definition-visual-basic"></a>Определение анонимного типа (Visual Basic)

В ответ на объявление экземпляра анонимного типа компилятор создает новое определение класса, которое содержит указанные свойства для типа.

## <a name="compiler-generated-code"></a>Код, созданный компилятором

Для следующего определения `product`компилятор создает новое определение класса, содержащее свойства `Name`, `Price`и `OnHand`.

[!code-vb[VbVbalrAnonymousTypes#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#25)]

Определение класса содержит определения свойств, аналогичные приведенным ниже. Обратите внимание, что для ключевых свойств отсутствует `Set` метод. Значения ключевых свойств доступны только для чтения.

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

Кроме того, анонимные определения типов содержат конструктор без параметров. Конструкторы, требующие параметров, не разрешены.

Если объявление анонимного типа содержит по крайней мере одно ключевое свойство, определение типа переопределяет три члена, наследуемые от <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>и <xref:System.Object.ToString%2A>. Если ключевые свойства не объявлены, переопределяется только <xref:System.Object.ToString%2A>. Переопределения предоставляют следующие функциональные возможности:

- `Equals` возвращает `True`, если два экземпляра анонимного типа являются одним и тем же экземпляром или если они отвечают следующим условиям:

  - Они имеют одинаковое число свойств.

  - Свойства объявляются в том же порядке с одинаковыми именами и теми же выводимыми типами. При сравнении имен регистр не учитывается.

  - По крайней мере одно из свойств является ключевым свойством, а ключевое слово `Key` применяется к тем же свойствам.

  - Сравнение каждой соответствующей пары ключевых свойств возвращает `True`.

    Например, в следующих примерах `Equals` возвращает `True` только для `employee01` и `employee08`. Комментарий перед каждой строкой указывает причину, по которой новый экземпляр не соответствует `employee01`.

    [!code-vb[VbVbalrAnonymousTypes#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#24)]

- `GetHashcode` предоставляет соответствующим образом уникальный алгоритм GetHashCode. Алгоритм использует только ключевые свойства для вычисления хэш-кода.

- `ToString` возвращает строку сцепленных значений свойств, как показано в следующем примере. Включены ключевые и неключевые свойства.

  [!code-vb[VbVbalrAnonymousTypes#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#29)]

Явно именованные свойства анонимного типа не могут конфликтовать с этими созданными методами. То есть нельзя использовать `.Equals`, `.GetHashCode`или `.ToString` для именования свойства.

Определения анонимных типов, включающие по крайней мере одно ключевое свойство, также реализуют интерфейс <xref:System.IEquatable%601?displayProperty=nameWithType>, где `T` является типом анонимного типа.

> [!NOTE]
> Объявления анонимного типа создают один и тот же анонимный тип только в том случае, если они встречаются в одной сборке, их свойства имеют одинаковые имена и те же выводимые типы, свойства объявляются в том же порядке, а те же свойства помечаются как ключевые свойства.

## <a name="see-also"></a>См. также

- [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
