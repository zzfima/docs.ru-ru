---
title: Операторы проверки на NULL (Справочник по C#)
ms.date: 04/03/2015
helpviewer_keywords:
- null-conditional operators [C#]
- ?. operator [C#]
- ?[] operator [C#]
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
ms.openlocfilehash: 823b9dc886bf2448ca9da4ac640bfe56f90d3ff3
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50194856"
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
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также

- [Оператор ?? (оператор объединения со значением NULL)](null-coalescing-operator.md)  
- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
