---
title: Практическое руководство. Изучение универсальных типов и создание их экземпляров при помощи отражения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reflection, generic types
- generics [.NET Framework], reflection
ms.assetid: f93b03b0-1778-43fc-bc6d-35983d210e74
ms.openlocfilehash: 62e4e066740d0422f8f7045b043a5725278c209c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130135"
---
# <a name="how-to-examine-and-instantiate-generic-types-with-reflection"></a>Практическое руководство. Изучение универсальных типов и создание их экземпляров при помощи отражения
Сведения об универсальных типах получаются аналогично сведениям о других типах: путем изучения объекта <xref:System.Type>, который представляет универсальный тип. Принципиальная разница заключается в том, что универсальный тип имеет список объектов <xref:System.Type>, представляющих его параметры универсального типа. В первой процедуре данного раздела изучаются универсальные типы.  
  
 Можно создать объект <xref:System.Type>, представляющий сконструированный тип, путем привязки аргументов типа к параметрам типа определения универсального типа. Это демонстрируется во второй процедуре.  
  
### <a name="to-examine-a-generic-type-and-its-type-parameters"></a>Изучение универсального типа и его параметров типа  
  
1. Получите экземпляр класса <xref:System.Type>, который представляет этот универсальный тип. В следующем коде этот тип получается с помощью оператора C# `typeof` (`GetType` в Visual Basic, `typeid` в Visual C++). Другие способы получения объекта <xref:System.Type> см. в теме, посвященной объекту <xref:System.Type>. Обратите внимание, что в оставшейся части этой процедуры этот тип содержится в параметре метода с именем `t`.  
  
     [!code-cpp[HowToGeneric#2](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#2)]
     [!code-csharp[HowToGeneric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#2)]
     [!code-vb[HowToGeneric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#2)]  
  
2. Для определения того, является ли тип универсальным, используется свойство <xref:System.Type.IsGenericType%2A>, а для определения того, является ли тип определением универсального типа, свойство <xref:System.Type.IsGenericTypeDefinition%2A>.  
  
     [!code-cpp[HowToGeneric#3](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#3)]
     [!code-csharp[HowToGeneric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#3)]
     [!code-vb[HowToGeneric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#3)]  
  
3. Получите массив, содержащий аргументы универсального типа, с использованием метода <xref:System.Type.GetGenericArguments%2A>.  
  
     [!code-cpp[HowToGeneric#4](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#4)]
     [!code-csharp[HowToGeneric#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#4)]
     [!code-vb[HowToGeneric#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#4)]  
  
4. Для каждого аргумента типа следует определить, является ли он параметром типа (например, в определении универсального типа) или типом, который был задан для параметра типа (например, в сконструированном типе) с использованием свойства <xref:System.Type.IsGenericParameter%2A>.  
  
     [!code-cpp[HowToGeneric#5](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#5)]
     [!code-csharp[HowToGeneric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#5)]
     [!code-vb[HowToGeneric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#5)]  
  
5. В системе типов параметр универсального типа представлен экземпляром класса <xref:System.Type>, как обычные типы. В следующем примере показано имя и расположение параметра для объекта <xref:System.Type>, который представляет параметр универсального типа. В этом примере определить положение параметра не представляет труда; эти сведения более важны при изучении параметра типа, который используется в качестве аргумента типа для другого универсального типа.  
  
     [!code-cpp[HowToGeneric#6](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#6)]
     [!code-csharp[HowToGeneric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#6)]
     [!code-vb[HowToGeneric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#6)]  
  
6. Определите ограничение базового типа и ограничения интерфейса параметра универсального типа с использованием метода <xref:System.Type.GetGenericParameterConstraints%2A>, чтобы получить все ограничения в одном массиве. Расположение ограничений в конкретном порядке не гарантируется.  
  
     [!code-cpp[HowToGeneric#7](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#7)]
     [!code-csharp[HowToGeneric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#7)]
     [!code-vb[HowToGeneric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#7)]  
  
7. При помощи свойства <xref:System.Type.GenericParameterAttributes%2A> выявите особые ограничения для параметра типа, например требования, чтобы он являлся ссылочным типом. Это свойство содержит значения, представляющие расхождение, которое можно замаскировать, как показано в следующем коде.  
  
     [!code-cpp[HowToGeneric#8](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#8)]
     [!code-csharp[HowToGeneric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#8)]
     [!code-vb[HowToGeneric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#8)]  
  
8. Атрибуты особого ограничения являются флагами, флаг (<xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>), который не представляет особые ограничения, также не представляет ковариацию или контрвариацию. Таким образом, для проверки любого из этих условий необходимо использовать подходящую маску. В этом случае следует использовать свойство <xref:System.Reflection.GenericParameterAttributes.SpecialConstraintMask?displayProperty=nameWithType> для изоляции флагов особых ограничений.  
  
     [!code-cpp[HowToGeneric#9](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#9)]
     [!code-csharp[HowToGeneric#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#9)]
     [!code-vb[HowToGeneric#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#9)]  
  
## <a name="constructing-an-instance-of-a-generic-type"></a>Конструирование экземпляра универсального типа  
 Универсальный тип напоминает шаблон. Нельзя создать его экземпляры, если не указаны фактические типы для его параметров универсального типа. Чтобы сделать это во время выполнения с использованием отражения, необходимо использовать метод <xref:System.Type.MakeGenericType%2A>.  
  
#### <a name="to-construct-an-instance-of-a-generic-type"></a>Конструирование экземпляра универсального типа  
  
1. Получите объект <xref:System.Type>, который представляет универсальный тип. В следующем примере получается универсальный тип <xref:System.Collections.Generic.Dictionary%602> двумя разными способами: с использованием перегруженной версии метода <xref:System.Type.GetType%28System.String%29?displayProperty=nameWithType> со строкой, описывающей этот тип, а также путем вызова метода <xref:System.Type.GetGenericTypeDefinition%2A> для сконструированного типа `Dictionary\<String, Example>` (`Dictionary(Of String, Example)` в Visual Basic). Для метода <xref:System.Type.MakeGenericType%2A> требуется определение универсального типа.  
  
     [!code-cpp[HowToGeneric#10](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#10)]
     [!code-csharp[HowToGeneric#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#10)]
     [!code-vb[HowToGeneric#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#10)]  
  
2. Создайте массив аргументов типа, на который будут заменены параметры типа. Этот массив должен содержать правильное количество объектов <xref:System.Type> в том же порядке, в котором они отображаются в списке параметров типа. В этом случае ключ (первый параметр типа) имеет тип <xref:System.String>, а значения в словаре являются экземплярами класса с именем `Example`.  
  
     [!code-cpp[HowToGeneric#11](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#11)]
     [!code-csharp[HowToGeneric#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#11)]
     [!code-vb[HowToGeneric#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#11)]  
  
3. Вызовите метод <xref:System.Type.MakeGenericType%2A>, чтобы привязать аргументы типа к параметрам типа и сконструировать тип.  
  
     [!code-cpp[HowToGeneric#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#12)]
     [!code-csharp[HowToGeneric#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#12)]
     [!code-vb[HowToGeneric#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#12)]  
  
4. Для создания объекта сконструированного типа используется перегруженная версия метода <xref:System.Activator.CreateInstance%28System.Type%29>. В следующем примере кода два экземпляра класса `Example` сохраняются в итоговом объекте `Dictionary<String, Example>`.  
  
     [!code-cpp[HowToGeneric#13](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#13)]
     [!code-csharp[HowToGeneric#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#13)]
     [!code-vb[HowToGeneric#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#13)]  
  
## <a name="example"></a>Пример  
 В следующем примере кода определяется метод `DisplayGenericType` для изучения определений универсальных типов и сконструированных типов, используемых в коде, и вывода сведений о них. Метод `DisplayGenericType` показывает, как использовать свойства <xref:System.Type.IsGenericType%2A>, <xref:System.Type.IsGenericParameter%2A> и <xref:System.Type.GenericParameterPosition%2A>, а также метод <xref:System.Type.GetGenericArguments%2A>.  
  
 В этом примере также определяется метод `DisplayGenericParameter` для изучения параметра универсального типа и вывода его ограничений.  
  
 В этом примере кода определяется набор тестовых типов, включая универсальный тип, который иллюстрирует ограничения параметра типа, и демонстрируется, как вывести сведения об этих типах.  
  
 В примере создается тип на основе класса <xref:System.Collections.Generic.Dictionary%602> путем создания массива аргументов типа и вызова метода <xref:System.Type.MakeGenericType%2A>. Программа сравнивает объект <xref:System.Type>, сконструированный с использованием метода <xref:System.Type.MakeGenericType%2A>, с объектом <xref:System.Type>, полученным с использованием оператора `typeof` (`GetType` в Visual Basic), показывая, что эти объекты одинаковы. Аналогичным образом программа получает определение универсального типа для сконструированного типа при помощи метода <xref:System.Type.GetGenericTypeDefinition%2A> и сравнивает его с объектом <xref:System.Type>, представляющим класс <xref:System.Collections.Generic.Dictionary%602>.  
  
 [!code-cpp[HowToGeneric#1](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#1)]
 [!code-csharp[HowToGeneric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#1)]
 [!code-vb[HowToGeneric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#1)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Type>
- <xref:System.Reflection.MethodInfo>
- [Отражение и универсальные типы](reflection-and-generic-types.md)
- [Просмотр сведений о типах](viewing-type-information.md)
- [Универсальные шаблоны](../../standard/generics/index.md)
