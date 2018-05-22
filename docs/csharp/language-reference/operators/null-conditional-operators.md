---
title: Операторы с условием NULL (C# и Visual Basic)
ms.date: 04/03/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- null-conditional operators [C#]
- null-conditional operators [Visual Basic]
- ?. operator [C#]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
ms.openlocfilehash: da771fa4a2a89dca308508ea81ef8e0060efa7f0
ms.sourcegitcommit: e5bb395ec86f536e114314184288f40a8c745e2e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2018
---
# <a name="-and--null-conditional-operators-c-and-visual-basic"></a>?. и ?[]: операторы с условием NULL (C# и Visual Basic)
Проверяет значение левого операнда на наличие значения NULL перед выполнением операции доступа к элементу (`?.`) или индексу (`?[]`). Возвращает `null`, если левый операнд имеет значение `null`. 

Эти операторы позволяют писать меньше кода для проверок значений null, особенно если речь идет о внедрении в структуры данных.  
  
```csharp  
int? length = customers?.Length; // null if customers is null   
Customer first = customers?[0];  // null if customers is null  
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
```  
  
```vb  
Dim length = customers?.Length  ' null if customers is null  
Dim first as Customer = customers?(0)  ' null if customers is null  
Dim count as Integer? = customers?(0)?.Orders?.Count()  ' null if customers, the first customer, or Orders is null  
```  
  
 Операторы с условием NULL предусматривают сокращенную обработку.  Если одна операция в цепочке условных операций доступа к элементу и операций индексирования возвращает значение NULL, то выполнение остальной части цепочки останавливается.  В приведенном ниже примере `E` не выполняется, если `A`, `B` или `C` имеет значение NULL.
  
```csharp
A?.B?.C?.Do(E);
A?.B?.C?[E];
```

```vb
A?.B?.C?.Do(E);
A?.B?.C?(E);
```  
  
 Другим примером использования для доступа к элементам с условием NULL является вызов делегатов в потокобезопасном режиме с существенно меньшим объемом кода.  Для старого способа требуется примерно следующий код:  
  
```csharp  
var handler = this.PropertyChanged;  
if (handler != null)  
    handler(…);
```  
  
```vb  
Dim handler = AddressOf(Me.PropertyChanged)  
If handler IsNot Nothing  
    Call handler(…)  
```  
  
 Новый способ гораздо проще:  
  
```csharp
PropertyChanged?.Invoke(…)  
```  

```vb
PropertyChanged?.Invoke(…)
```  
  
 Новый способ является потокобезопасным, так как компилятор создает код для вычисления `PropertyChanged` только один раз, запоминая результат во временной переменной. Необходимо явно вызывать метод `Invoke`, так как отсутствует синтаксис `PropertyChanged?(e)` для вызова делегатов с условием NULL.  
  
## <a name="language-specifications"></a>Спецификации языков  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
 Дополнительные сведения см. в разделе [Справочник по языку Visual Basic](../../../visual-basic/language-reference/index.md).  
  
## <a name="see-also"></a>См. также  
 [Оператор ?? (оператор объединения со значением NULL)](null-conditional-operator.md)  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Руководство по программированию на Visual Basic](../../../visual-basic/programming-guide/index.md)
