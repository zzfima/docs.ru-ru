---
title: Операторы с условием NULL (Visual Basic)
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: 4815fe7ad337634cfb56127fbd24a47a37fdd74b
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2019
ms.locfileid: "65062942"
---
# <a name="-and--null-conditional-operators-visual-basic"></a>?. и? операторы с условием null () (Visual Basic)

Проверяет значение левого операнда со значением NULL (`Nothing`) перед выполнением доступа к членам (`?.`) или индекса (`?()`) операции; возвращает `Nothing` Если левый операнд, результатом которого является `Nothing`. Обратите внимание, что в выражениях, которые обычно возвращают типы значений, условием null оператор возвращает <xref:System.Nullable%601>.

Эти операторы позволяют писать меньше кода для проверок значений null, особенно в том случае, при внедрении в структуры данных. Пример:

```vb
' Nothing if customers is Nothing  
Dim length As Integer? = customers?.Length  

' Nothing if customers is Nothing
Dim first As Customer = customers?(0)

' Nothing if customers, the first customer, or Orders is Nothing
Dim count As Integer? = customers?(0)?.Orders?.Count()   
```

Для сравнения является альтернативный код для первого из этих выражений без условного оператора:

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

Иногда требуется выполнить действие на объекте, который может иметь значение null, на основе значения член типа Boolean для этого объекта (значение логического свойства, такие как `IsAllowedFreeShipping` в следующем примере):

```vb
  Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.
  
  If customer IsNot Nothing AndAlso customer.IsAllowedFreeShipping Then
   ApplyFreeShippingToOrders(customer)
  End If
```

Можно сократить код и избежать вручную проверки значений NULL с помощью условного оператора, следующим образом:

```vb
 Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.
 
 If customer?.IsAllowedFreeShipping Then ApplyFreeShippingToOrders(customer)
```

Операторы с условием NULL предусматривают сокращенную обработку.  Если одна операция в цепочке операций доступа и индекс условный член возвращает `Nothing`, остальной части цепочки выполнение останавливается.  В следующем примере `C(E)` не вычисляется, если `A`, `B`, или `C` принимает значение `Nothing`.

```vb
A?.B?.C?(E);
```

Другой член с условием null доступ используется для вызова делегатов в потокобезопасным способом, с гораздо меньшим объемом кода.  В следующем примере определяется два типа `NewsBroadcaster` и `NewsReceiver`. Новости отправляются получателю по `NewsBroadcaster.SendNews` делегировать.

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

Если ни один элемент в `SendNews` список вызова, `SendNews` делегат создает исключение <xref:System.NullReferenceException>. Перед условные операторы null, код, как следующие гарантируется, что список вызовов делегата не `Nothing`:

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
