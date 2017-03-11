---
title: "Определение анонимного типа (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "анонимные типы [Visual Basic], определение типа"
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Определение анонимного типа (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

В ответ на объявление экземпляра анонимного типа компилятор создает определение нового класса, содержащее указанные свойства.  
  
## Код, создаваемый компилятором  
 Для следующего определения `product` компилятор создает новое определение класса, содержащее свойства `Name`, `Price` и `OnHand`.  
  
 [!code-vb[VbVbalrAnonymousTypes#25](../../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/anonymous-type-definition_1.vb)]  
  
 Определение класса содержит определения свойств следующего вида.  Обратите внимание, что для ключевых свойств нет метода `Set`.  Значения ключевых свойств доступны только для чтения.  
  
```vb#  
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
  
 Кроме того, определения анонимного типа содержат конструктор по умолчанию.  Конструкторы, требующие параметры, не разрешены.  
  
 Если анонимный тип содержит по крайней мере одно ключевое свойство, определение переопределяет три члена, унаследованные от <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, и <xref:System.Object.ToString%2A>.  Если ключевые свойства не объявлены, переопределяется только <xref:System.Object.ToString%2A>.  Переопределение предоставляет следующие возможности:  
  
-   `Equals` возвращает `True`, если два экземпляра анонимного типа являются одним и тем же экземпляром или если они отвечают следующим условиям:  
  
    -   Они имеют одинаковое число свойств.  
  
    -   Свойства объявляются в том же порядке, имеют те же имена и те же возвращаемые типы.  Сравнение имен не учитывает регистр.  
  
    -   По крайней мере одно из свойств является ключевым свойством и ключевое слово `Key` применяется к тем же свойствам.  
  
    -   Сравнение каждой соответствующей пары ключевых свойств возвращает `True`.  
  
     Например, в следующих примерах `Equals` возвращает `True` только для `employee01` и `employee08`.  Комментарий перед каждой строкой определяет причину, по которой новый экземпляр не соответствует `employee01`.  
  
     [!code-vb[VbVbalrAnonymousTypes#24](../../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/anonymous-type-definition_2.vb)]  
  
-   `GetHashcode` предоставляет соответствующим образом уникальный алгоритм GetHashCode.  Алгоритм использует для вычисления хэш\-кода только ключевые свойства.  
  
-   `ToString` возвращает строку, в которой объединены значения свойств, как показано в следующем примере.  Включены ключевые и неключевые свойства.  
  
     [!code-vb[VbVbalrAnonymousTypes#29](../../../../visual-basic/language-reference/modifiers/codesnippet/visualbasic/anonymous-type-definition_3.vb)]  
  
 Явно именованные свойства анонимного типа не могут конфликтовать с этими созданными методами.  А именно, нельзя использовать `.Equals`, `.GetHashCode` или `.ToString` для имени свойства.  
  
 Определения анонимных типов, которые включают по крайней мере одно ключевое свойство, также реализуют интерфейс <xref:System.IEquatable%601?displayProperty=fullName>, где `T` — тип анонимного типа.  
  
> [!NOTE]
>  Объявления анонимного типа создают тот же анонимный тип, только если они встречаются в той же сборке, их свойства имеют те же имена и те же выводимые типы, свойства объявлены в том же порядке, и те же свойства маркированы как ключевые свойства.  
  
## См. также  
 [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)