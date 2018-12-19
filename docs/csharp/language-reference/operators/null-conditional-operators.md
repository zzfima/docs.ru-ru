---
title: Справочник по C#. Операторы проверки на NULL
ms.custom: seodec18
ms.date: 04/03/2015
helpviewer_keywords:
- null-conditional operators [C#]
- ?. operator [C#]
- ?[] operator [C#]
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
ms.openlocfilehash: 4189b07fd280192a4cb39400e4e77cef702c9d08
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239557"
---
# <a name="-and--null-conditional-operators-c-and-visual-basic"></a>?. и ?[]: операторы с условием NULL (C# и Visual Basic)
Проверяет значение левого операнда на наличие значения NULL перед выполнением операции доступа к элементу (`?.`) или индексу (`?[]`). Возвращает `null`, если левый операнд имеет значение `null`. 

Эти операторы позволяют писать меньше кода для проверок значений null, особенно если речь идет о внедрении в структуры данных.  
  
```csharp  
int? length = customers?.Length; // null if customers is null   
Customer first = customers?[0];  // null if customers is null  
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
```  
  
 Операторы с условием NULL предусматривают сокращенную обработку.  Если одна из операций в цепочке условных операций доступа к члену и операций индексирования возвращает значение NULL, то выполнение остальной части цепочки прекращается.  В приведенном ниже примере `E` не выполняется, если `A`, `B` или `C` имеет значение NULL.
  
```csharp
A?.B?.C?.Do(E);
A?.B?.C?[E];
```

 Другим примером использования для доступа к элементам с условием NULL является вызов делегатов в потокобезопасном режиме с существенно меньшим объемом кода.  Для старого способа требуется примерно следующий код:  
  
```csharp  
var handler = this.PropertyChanged;  
if (handler != null)  
    handler(…);
```  
  
  
 Новый способ гораздо проще:  
  
```csharp
PropertyChanged?.Invoke(…)  
```  

 Новый способ является потокобезопасным, так как компилятор создает код для вычисления `PropertyChanged` только один раз, запоминая результат во временной переменной. Необходимо явно вызывать метод `Invoke`, так как отсутствует синтаксис `PropertyChanged?(e)` для вызова делегатов с условием NULL.  
  
## <a name="language-specifications"></a>Спецификации языков  

Дополнительные сведения см. в разделе об [операторах с условием NULL](~/_csharplang/spec/expressions.md#null-conditional-operator) в [Спецификации языка C#](../language-specification/index.md). Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.
  
## <a name="see-also"></a>См. также

- [Оператор ?? (оператор объединения со значением NULL)](null-coalescing-operator.md)  
- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
