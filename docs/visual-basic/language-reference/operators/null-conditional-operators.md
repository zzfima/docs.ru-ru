---
title: Операторы с условием NULL (Visual Basic)
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: d30d452a7c140a0c56529386b14ef3a3512df490
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722157"
---
# <a name="-and--null-conditional-operators-visual-basic"></a>?. и? операторы с условием null () (Visual Basic)

Проверяет значение левого операнда со значением NULL (`Nothing`) перед выполнением доступа к членам (`?.`) или индекса (`?()`) операции; возвращает `Nothing` Если левый операнд, результатом которого является `Nothing`. Обратите внимание, что, в выражениях, которые обычно возвращает типы значений, условием null оператор возвращает <xref:System.Nullable%601>.

Эти операторы позволяют писать меньше кода для проверок значений null, особенно в том случае, при внедрении в структуры данных. Пример:

```vb
Dim length As Integer? = customers?.Length  ' Nothing if customers is Nothing  
Dim first As Customer = customers?(0)  ' Nothing if customers is Nothing  
Dim count As Integer? = customers?(0)?.Orders?.Count()  ' Nothing if customers, the first customer, or Orders is Nothing  
```

Для сравнения является альтернативный код для первого из этих выражений без условного оператора:

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

Операторы с условием NULL предусматривают сокращенную обработку.  Если одна операция в цепочке операций доступа и индекс условный член возвращает значение Nothing, остальной части цепочки останавливается.  В следующем примере, если не вычисляется C(E) `A`, `B`, или `C` бесполезным.

```vb
A?.B?.C?(E);
```

Другой член с условием null доступ используется для вызова делегатов в потокобезопасным способом, с гораздо меньшим объемом кода.  Для старого способа требуется примерно следующий код:  

```vb  
Dim handler = AddressOf(Me.PropertyChanged)  
If handler IsNot Nothing  
    Call handler(…)  
```

Новый способ гораздо проще:  

```vb
PropertyChanged?.Invoke(…)
```

Новый способ является потокобезопасным, так как компилятор создает код для вычисления `PropertyChanged` только один раз, запоминая результат во временной переменной. Необходимо явно вызывать метод `Invoke`, так как отсутствует синтаксис `PropertyChanged?(e)` для вызова делегатов с условием NULL.  

## <a name="see-also"></a>См. также

- [Операторы (Visual Basic)](index.md)
- [Руководство по программированию на Visual Basic](../../../visual-basic/programming-guide/index.md)
- [Справочник по языку Visual Basic](../../../visual-basic/language-reference/index.md)
