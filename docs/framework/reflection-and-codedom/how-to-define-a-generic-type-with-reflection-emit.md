---
title: Практическое руководство. Определение универсального типа с порождаемым отражением
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- generics [.NET Framework], reflection emit
- generics [.NET Framework], dynamic types
- reflection emit, generic types
ms.assetid: 07d5f01a-7b5b-40ea-9b15-f21561098fe4
ms.openlocfilehash: b553fd2235c73cf879474dc4f44f958dddcb649c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130156"
---
# <a name="how-to-define-a-generic-type-with-reflection-emit"></a>Практическое руководство. Определение универсального типа с порождаемым отражением
В этом разделе приведено описание способов создания простого универсального типа с двумя параметрами типа, порядка применения ограничений класса, ограничений интерфейса и специальных ограничений параметров типа, создания элементов, использующих параметры типа класса в качестве типов параметров и возвращаемых типов.  
  
> [!IMPORTANT]
> Метод не может являться универсальным только потому, что он принадлежит универсальному типу и использует параметры этого типа. Метод является универсальным только в том случае, если он имеет свой собственный список параметров типа. Большинство методов в универсальных типах не являются универсальными, как в этом примере. Пример выпуска универсального метода см. в разделе [Практическое руководство. Определение универсального метода с порождаемым отражением](how-to-define-a-generic-method-with-reflection-emit.md).  
  
### <a name="to-define-a-generic-type"></a>Определение универсального типа  
  
1. Определите динамическую сборку с именем `GenericEmitExample1`. В этом примере сборка выполняется и сохраняется на диске, так что указан флаг <xref:System.Reflection.Emit.AssemblyBuilderAccess.RunAndSave?displayProperty=nameWithType>.  
  
     [!code-cpp[EmitGenericType#2](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#2)]
     [!code-csharp[EmitGenericType#2](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#2)]
     [!code-vb[EmitGenericType#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#2)]  
  
2. Определите динамический модуль. Сборка состоит из выполняемых модулей. Для сборки с одним модулем именем модуля является имя сборки, а именем файла — имя сборки с расширением.  
  
     [!code-cpp[EmitGenericType#3](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#3)]
     [!code-csharp[EmitGenericType#3](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#3)]
     [!code-vb[EmitGenericType#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#3)]  
  
3. Определите класс. В этом примере класс называется `Sample`.  
  
     [!code-cpp[EmitGenericType#4](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#4)]
     [!code-csharp[EmitGenericType#4](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#4)]
     [!code-vb[EmitGenericType#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#4)]  
  
4. Определите параметры универсального типа метода `Sample` посредством передачи массива строк, содержащего имена параметров, в метод <xref:System.Reflection.Emit.TypeBuilder.DefineGenericParameters%2A?displayProperty=nameWithType>. Этот класс станет универсального типа. Возвращаемое значение — это массив объектов <xref:System.Reflection.Emit.GenericTypeParameterBuilder>, представляющих параметры типа, который может использоваться в выпущенном коде.  
  
     В следующем коде `Sample` становится универсальным типом с параметрами типа `TFirst` и `TSecond`. Чтобы сделать код более удобными для чтения, каждый объект <xref:System.Reflection.Emit.GenericTypeParameterBuilder> помещается в переменную с тем же именем, что параметр типа.  
  
     [!code-cpp[EmitGenericType#5](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#5)]
     [!code-csharp[EmitGenericType#5](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#5)]
     [!code-vb[EmitGenericType#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#5)]  
  
5. Добавьте специальные ограничения параметров типа. В этом примере параметр типа `TFirst` ограничен типами, имеющими конструкторы без параметров, а также ссылочными типами.  
  
     [!code-cpp[EmitGenericType#6](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#6)]
     [!code-csharp[EmitGenericType#6](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#6)]
     [!code-vb[EmitGenericType#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#6)]  
  
6. Дополнительно добавьте ограничения класса и интерфейса в параметры типа. В этом примере параметр типа `TFirst` ограничен типами, которые являются производными из базового класса, представленного объектом <xref:System.Type>, содержащимся в переменной `baseType`, а также которые реализуют интерфейсы, содержащие типы в переменных `interfaceA` и `interfaceB`. Объявление и назначение этих переменных см. в примере кода.  
  
     [!code-cpp[EmitGenericType#7](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#7)]
     [!code-csharp[EmitGenericType#7](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#7)]
     [!code-vb[EmitGenericType#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#7)]  
  
7. Определите поле. В этом примере тип поля задается параметром типа `TFirst`. <xref:System.Reflection.Emit.GenericTypeParameterBuilder> является производным от <xref:System.Type>, поэтому параметры универсального типа можно использовать везде, где можно использовать тип.  
  
     [!code-cpp[EmitGenericType#21](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#21)]
     [!code-csharp[EmitGenericType#21](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#21)]
     [!code-vb[EmitGenericType#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#21)]  
  
8. Определите метод, который использует параметры типа, относящиеся к универсальному типу. Обратите внимание, что такие методы не являются универсальными, если только они не имеют собственный список параметров типа. В следующем примере кода определяется метод `static` (`Shared` в Visual Basic), который принимает массив `TFirst` и возвращает `List<TFirst>` (`List(Of TFirst)` в Visual Basic), содержащий все элементы массива. Чтобы определить этот метод, необходимо создать тип `List<TFirst>` путем вызова метода <xref:System.Type.MakeGenericType%2A> в определении универсального типа `List<T>`. (`T` пропускается при использовании оператора `typeof` (`GetType` в Visual Basic) для получения определения универсального типа.) Тип параметра создается с помощью метода <xref:System.Type.MakeArrayType%2A>.  
  
     [!code-cpp[EmitGenericType#22](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#22)]
     [!code-csharp[EmitGenericType#22](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#22)]
     [!code-vb[EmitGenericType#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#22)]  
  
9. Выпустите основную часть метода. Основная часть метода состоит из трех кодов операции, которые загружает входной массив в стек, вызывают конструктор `List<TFirst>`, который принимает `IEnumerable<TFirst>` (выполняет всю работу по помещению входных элементов в список), и возвращается (оставляя новый объект <xref:System.Collections.Generic.List%601> в стеке). Трудной частью выпуска этого кода является получение конструктора.  
  
     Метод <xref:System.Type.GetConstructor%2A> не поддерживается для <xref:System.Reflection.Emit.GenericTypeParameterBuilder>, так что невозможно напрямую получить конструктор `List<TFirst>`. Сначала необходимо получить конструктор определения универсального типа `List<T>`, а затем вызвать метод, который преобразует его в соответствующий конструктор `List<TFirst>`.  
  
     Конструктор, используемый для этого примера кода принимает `IEnumerable<T>`. Но обратите внимание, что это не определение универсального типа универсального интерфейса <xref:System.Collections.Generic.IEnumerable%601>; вместо этого параметр типа `T` из `List<T>` должен быть замещен для параметра типа `T` объекта `IEnumerable<T>`. (Это кажется запутанным только потому, что оба типа имеют параметры типа с именем `T`. Именно поэтому в этом примере кода используются имена `TFirst` и `TSecond`.) Чтобы получить тип аргумента конструктора, начните с определения универсального типа `IEnumerable<T>` и вызовите <xref:System.Type.MakeGenericType%2A> с первым параметром универсального типа `List<T>`. В этом случае список аргументов конструктора должен быть передан в качестве массива только с одним аргументом.  
  
    > [!NOTE]
    > Определение общего типа выражается как `IEnumerable<>` при использовании оператора `typeof` в C# или `IEnumerable(Of )` при использовании оператора `GetType` в Visual Basic.  
  
     Теперь возможно получить конструктор `List<T>` путем вызова метода <xref:System.Type.GetConstructor%2A> в определении универсального типа. Чтобы преобразовать этот конструктор в соответствующий конструктор `List<TFirst>`, передайте `List<TFirst>` и конструктор из `List<T>` в статический метод <xref:System.Reflection.Emit.TypeBuilder.GetConstructor%28System.Type%2CSystem.Reflection.ConstructorInfo%29?displayProperty=nameWithType>.  
  
     [!code-cpp[EmitGenericType#23](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#23)]
     [!code-csharp[EmitGenericType#23](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#23)]
     [!code-vb[EmitGenericType#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#23)]  
  
10. Создайте тип и сохраните файл.  
  
     [!code-cpp[EmitGenericType#8](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#8)]
     [!code-csharp[EmitGenericType#8](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#8)]
     [!code-vb[EmitGenericType#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#8)]  
  
11. Вызовите метод. `ExampleMethod` не является универсальным, но тип, которому он принадлежит, является универсальным. Поэтому для получения объекта <xref:System.Reflection.MethodInfo>, который может быть вызван, необходимо создать сконструированный тип из определения типа для `Sample`. Сконструированный тип использует класс `Example`, который согласуется с ограничениями `TFirst`, так как он является ссылочным типом и имеет конструктор без параметров по умолчанию, а также класс `ExampleDerived`, который соответствует ограничениям `TSecond`. (Код для `ExampleDerived` можно найти в разделе «пример кода».) Эти два типа передаются <xref:System.Type.MakeGenericType%2A> для создания сконструированного типа. Затем получается объект <xref:System.Reflection.MethodInfo> с помощью метода <xref:System.Type.GetMethod%2A>.  
  
     [!code-cpp[EmitGenericType#9](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#9)]
     [!code-csharp[EmitGenericType#9](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#9)]
     [!code-vb[EmitGenericType#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#9)]  
  
12. В следующем коде создается массив объектов `Example`, затем этот массив размещается в массиве типа <xref:System.Object>, представленном аргументами вызываемого метода, после чего они передаются в метод <xref:System.Reflection.MethodBase.Invoke%28System.Object%2CSystem.Object%5B%5D%29>. Первый аргумент метода <xref:System.Reflection.MethodBase.Invoke%2A> — это пустая ссылка, так как метод является `static`.  
  
     [!code-cpp[EmitGenericType#10](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#10)]
     [!code-csharp[EmitGenericType#10](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#10)]
     [!code-vb[EmitGenericType#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#10)]  
  
## <a name="example"></a>Пример  
 В следующем примере кода определяется класс с именем `Sample` наряду с базовым классом и двумя интерфейсами. Программа определяет два параметра универсального типа для `Sample`, преобразуя его в универсальный тип. Параметры типа — это единственный фактор, делающий тип универсальным. Программа отображает это посредством сообщения проверки до и после определения параметров типа.  
  
 Параметр типа `TSecond` используется для демонстрации ограничений класса и интерфейса с помощью базовых классов и интерфейсов, а параметр типа `TFirst` применяется для демонстрации специальных ограничений.  
  
 В примере кода определяется поле и метод с использованием параметров типа класса для типа поля и параметра, а также возвращаемый тип метода.  
  
 После создания класса `Sample` вызывается этот метод.  
  
 Программа содержит метод, который отображает сведения об универсальном типе, и метод, который отображает список специальных ограничений для параметра типа. Эти методы используются для отображения сведений о завершенном классе `Sample`.  
  
 Программа сохраняет завершенный модуль на диске как `GenericEmitExample1.dll`, чтобы его можно было открыть с помощью [Ildasm.exe (дизассемблер IL)](../tools/ildasm-exe-il-disassembler.md) и изучить MSIL для класса `Sample`.  
  
 [!code-cpp[EmitGenericType#1](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#1)]
 [!code-csharp[EmitGenericType#1](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#1)]
 [!code-vb[EmitGenericType#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#1)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Reflection.Emit.GenericTypeParameterBuilder>
- [Использование порождаемого отражения](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y322t50(v=vs.100))
- [Сценарии динамических сборок порождаемого отражения](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/tt9483fk(v=vs.100))
