---
title: Операторы с условием NULL (Visual Basic)
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: b83435b8448b53eca63aac0519e9eed2f7dfa9f3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62028695"
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
