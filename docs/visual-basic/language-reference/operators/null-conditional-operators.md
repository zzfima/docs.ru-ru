---
title: Условные операторы null
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: 003f579a7128bbe2462b7fbe7057de03e61bfbe6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348283"
---
# <a name="-and--null-conditional-operators-visual-basic"></a>?. перетаскивани? ()-условные операторы null (Visual Basic)

Проверяет значение левого операнда для значения NULL (`Nothing`) перед выполнением операции доступа к члену (`?.`) или индекса (`?()`); Возвращает `Nothing`, если левый операнд принимает значение `Nothing`. Обратите внимание, что в выражениях, которые обычно возвращают типы значений, условный оператор null возвращает <xref:System.Nullable%601>.

Эти операторы помогают писать меньше кода для проверки значений NULL, особенно при сортировке по структурам данных. Пример.

```vb
' Nothing if customers is Nothing
Dim length As Integer? = customers?.Length

' Nothing if customers is Nothing
Dim first As Customer = customers?(0)

' Nothing if customers, the first customer, or Orders is Nothing
Dim count As Integer? = customers?(0)?.Orders?.Count()
```

Для сравнения альтернативный код для первого из этих выражений без условного оператора null имеет значение:

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

Иногда необходимо выполнить действие над объектом, который может иметь значение null, на основе значения логического элемента в этом объекте (например, логическое свойство `IsAllowedFreeShipping` в следующем примере):

```vb
Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.

If customer IsNot Nothing AndAlso customer.IsAllowedFreeShipping Then
  ApplyFreeShippingToOrders(customer)
End If
```

Вы можете сократить код и избежать ручной проверки значения NULL с помощью оператора Conditional, как показано ниже:

```vb
Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.

If customer?.IsAllowedFreeShipping Then ApplyFreeShippingToOrders(customer)
```

Операторы с условием NULL предусматривают сокращенную обработку.  Если одна операция в цепочке условного доступа к члену и операции с индексами возвращает `Nothing`, оставшаяся часть выполнения цепочки останавливается.  В следующем примере `C(E)` не вычисляется, если `A`, `B`или `C` равен `Nothing`.

```vb
A?.B?.C?(E)
```

Другим вариантом использования для доступа к членам с атрибутом null является вызов делегатов потокобезопасным способом с гораздо меньшим объемом кода.  В следующем примере определяются два типа: `NewsBroadcaster` и `NewsReceiver`. Элементы новостей отправляются получателю с помощью делегата `NewsBroadcaster.SendNews`.

```vb
Public Module NewsBroadcaster
   Dim SendNews As Action(Of String)

   Public Sub Main()
      Dim rec As New NewsReceiver()
      Dim rec2 As New NewsReceiver()
      SendNews?.Invoke("Just in: A newsworthy item...")
   End Sub

   Public Sub Register(client As Action(Of String))
      SendNews = SendNews.Combine({SendNews, client})
   End Sub
End Module

Public Class NewsReceiver
   Public Sub New()
      NewsBroadcaster.Register(AddressOf Me.DisplayNews)
   End Sub

   Public Sub DisplayNews(newsItem As String)
      Console.WriteLine(newsItem)
   End Sub
End Class
```

Если в списке вызовов `SendNews` нет элементов, `SendNews` делегат создает <xref:System.NullReferenceException>. Перед пустыми условными операторами, код, подобный приведенному ниже, гарантирует, что список вызовов делегата не `Nothing`:

```vb
SendNews = SendNews.Combine({SendNews, client})
If SendNews IsNot Nothing Then
   SendNews("Just in...")
End If
```

Новый способ гораздо проще:

```vb
SendNews = SendNews.Combine({SendNews, client})
SendNews?.Invoke("Just in...")
```

Новый способ является потокобезопасным, так как компилятор создает код для вычисления `SendNews` только один раз, запоминая результат во временной переменной. Необходимо явно вызывать метод `Invoke`, так как отсутствует синтаксис `SendNews?(String)` для вызова делегатов с условием NULL.

## <a name="see-also"></a>См. также

- [Операторы (Visual Basic)](index.md)
- [Руководство по программированию на Visual Basic](../../../visual-basic/programming-guide/index.md)
- [Справочник по языку Visual Basic](../../../visual-basic/language-reference/index.md)
