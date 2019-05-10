---
title: Советы по производительности .NET
ms.date: 03/30/2017
helpviewer_keywords:
- C# language, performance
- performance [C#]
- Visual Basic, performance
- performance [Visual Basic]
ms.assetid: ae275793-857d-4102-9095-b4c2a02d57f4
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f020e50cfe53c2b6ba134308ed6587876ca21a42
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64616298"
---
# <a name="net-performance-tips"></a>Советы по производительности .NET
Под *производительностью* обычно понимается скорость выполнения программы. В некоторых случаях ее можно увеличить, следуя определенным основным правилам написания исходного кода. В некоторых программах важно тщательно проверить код и с помощью профилировщиков убедиться, что он выполняется максимально быстро. В других случаях такая оптимизация не требуется, поскольку код выполняется достаточно быстро в своем первоначальном виде. В этой статье описываются основные причины снижения производительности и приводятся рекомендации по ее повышению, а также ссылки на разделы с дополнительной информацией. Дополнительные сведения о планировании и измерении производительности см. в разделе [Производительность](../../../docs/framework/performance/index.md)  
  
## <a name="boxing-and-unboxing"></a>Упаковка–преобразование и распаковка–преобразование  
 Не рекомендуется использовать типы значений в тех случаях, где они многократно упаковываются, например в классах неуниверсальных коллекций, таких как <xref:System.Collections.ArrayList?displayProperty=nameWithType>. Чтобы избежать упаковки типов значений, используйте универсальные коллекции, такие как <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>. Операции упаковки и распаковки являются весьма затратными процессами с точки зрения вычислений. При упаковке типа значений создается полностью новый объект. Это может занимать почти в 20 раз больше времени, чем простое присваивание ссылки. Процесс приведения при распаковке также занимает в 4 раза больше времени, чем присваивание. Дополнительные сведения см. в разделе [Упаковка-преобразование и распаковка-преобразование](~/docs/csharp/programming-guide/types/boxing-and-unboxing.md).  
  
## <a name="strings"></a>Строки  
 При сцеплении большого числа строковых переменных, например в непрерывном цикле, используйте <xref:System.Text.StringBuilder?displayProperty=nameWithType> вместо [оператора + (C#)](~/docs/csharp/language-reference/operators/addition-operator.md) или [операторов сцепления (Visual Basic)](~/docs/visual-basic/language-reference/operators/concatenation-operators.md). Дополнительные сведения см. в разделе [Как Объединить несколько строк](../../csharp/how-to/concatenate-multiple-strings.md) и [операторы объединения в Visual Basic](~/docs/visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md).  
  
## <a name="destructors"></a>Деструкторы  
 Пустые деструкторы использовать не следует. Если класс содержит деструктор, то в очереди метода Finalize создается запись. При вызове деструктора вызывается сборщик мусора, выполняющий обработку очереди. Если деструктор пустой, это приводит только к ненужному снижению производительности. Дополнительные сведения см. в разделе [деструкторы](~/docs/csharp/programming-guide/classes-and-structs/destructors.md) и [время жизни объекта: Как создаются и удаляются объекты](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
## <a name="other-resources"></a>Другие ресурсы  
  
- [Повышение производительности управляемого кода: Определение значения объектов](https://go.microsoft.com/fwlink/?LinkId=99294)  
  
- [Написание высокой производительности управляемого приложения: Основные сведения](https://go.microsoft.com/fwlink/?LinkId=99295)  
  
- [Общие сведения о сборке мусора и советы по повышению производительности](https://go.microsoft.com/fwlink/?LinkId=99296)  
  
- [Советы и рекомендации по повышению производительности в приложениях .NET](https://go.microsoft.com/fwlink/?LinkId=99297)  

- [Советы по повышению производительности от Рико Мариани](https://go.microsoft.com/fwlink/?LinkId=115679)  

- [Блоге Вэнса Моррисона](https://blogs.msdn.microsoft.com/vancem/)
  
## <a name="see-also"></a>См. также

- [Производительность](../../../docs/framework/performance/index.md)
- [Руководство по программированию на Visual Basic](../../visual-basic/programming-guide/index.md)
- [Руководство по программированию на C#](../../csharp/programming-guide/index.md)
