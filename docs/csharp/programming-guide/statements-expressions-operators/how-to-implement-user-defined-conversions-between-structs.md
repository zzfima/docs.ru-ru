---
title: Как выполнить Руководство по программированию на C#. Реализация определенных пользователем преобразований между структурами
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- user-defined conversions [C#]
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
ms.openlocfilehash: 85345203982679c0ab8dc9a6ae899312204c3230
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241578"
---
# <a name="how-to-implement-user-defined-conversions-between-structs-c-programming-guide"></a>Как выполнить Руководство по программированию на C#. Реализация определенных пользователем преобразований между структурами
В этом примере определяются две структуры (`RomanNumeral` и `BinaryNumeral`) и демонстрируются преобразования между ними.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideStatements#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_1.cs)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
  
-   В предыдущем примере инструкция:  
  
     [!code-csharp[csProgGuideStatements#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_2.cs)]  
  
     выполняет преобразование из `RomanNumeral` в `BinaryNumeral`. Поскольку прямого преобразования из `RomanNumeral` в `BinaryNumeral` не существует, используется приведение для преобразования из `RomanNumeral` в `int` и еще одно приведение для преобразования из `int` в `BinaryNumeral`.  
  
-   Кроме того, инструкция  
  
     [!code-csharp[csProgGuideStatements#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_3.cs)]  
  
     выполняет преобразование из `BinaryNumeral` в `RomanNumeral`. Поскольку `RomanNumeral` определяет неявное преобразование из `BinaryNumeral`, приведение не требуется.  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Операторы преобразования](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)
