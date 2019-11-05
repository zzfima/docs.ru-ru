---
title: Практическое руководство. Определение универсального метода с порождаемым отражением
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- generics [.NET Framework], reflection emit
- reflection emit, generic methods
- generics [.NET Framework], dynamic types
ms.assetid: 93892fa4-90b3-4ec4-b147-4bec9880de2b
ms.openlocfilehash: d16f6728b01583fe3ffb8d892522f3892444c537
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130178"
---
# <a name="how-to-define-a-generic-method-with-reflection-emit"></a>Практическое руководство. Определение универсального метода с порождаемым отражением

В первой процедуре показано, как создать простой универсальный метод с двумя типами параметров и как применить ограничения класса, интерфейса, а также особые ограничения параметров типа.

Во второй процедуре показано, как вывести основную часть метода и как использовать параметры типа в универсальном методе для создания экземпляров универсального типа и вызова соответствующих методов.

В третьей процедуре показано, как вызывать универсальный метод.

> [!IMPORTANT]
> Метод не может являться универсальным только потому, что он принадлежит универсальному типу и использует параметры этого типа. Метод является универсальным только в том случае, если он имеет свой собственный список параметров типа. Универсальный метод может появиться в неуниверсальном типе, как показано в этом примере. Пример использования неуниверсального метода для универсального типа см. в разделе [Практическое руководство. Определение универсального типа с порождаемым отражением](how-to-define-a-generic-type-with-reflection-emit.md).

### <a name="to-define-a-generic-method"></a>Определение универсального метода

1. Прежде чем приступить к работе, стоит рассмотреть, как универсальный метод выглядит при его создании на высокоуровневом языке. Следующий код включен в код примера из этого раздела вместе с кодом вызова универсального метода. Этот метод содержит параметры двух типов — `TInput` и `TOutput`. Последний должен быть ссылочным типом (`class`), должен иметь конструктор без параметров (`new`) и должен реализовывать `ICollection(Of TInput)` (`ICollection<TInput>` в C#). Это ограничение интерфейса обеспечивает использование метода <xref:System.Collections.Generic.ICollection%601.Add%2A?displayProperty=nameWithType> для добавления элементов в коллекцию `TOutput`, созданную этим методом. Этот метод имеет один формальный параметр `input`, который является массивом `TInput`. Этот метод создает коллекцию типа `TOutput` и копирует в нее элементы `input`.

    [!code-csharp[GenericMethodHowTo#20](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#20)]
    [!code-vb[GenericMethodHowTo#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#20)]

2. Определите динамическую сборку и динамический модуль, содержащие тип, которому принадлежит универсальный метод. В этом случае сборка имеет только один модуль, который называется `DemoMethodBuilder1`. Имя модуля является идентичным имени сборки с добавленным расширением. В этом примере сборка сохраняется на диск и также выполняется, поэтому указывается <xref:System.Reflection.Emit.AssemblyBuilderAccess.RunAndSave?displayProperty=nameWithType>. Можно использовать [Ildasm.exe (дизассемблер IL)](../tools/ildasm-exe-il-disassembler.md) для проверки DemoMethodBuilder1.dll и сравнения этой библиотеки с языком MSIL для метода, показанного на этапе 1.

    [!code-csharp[GenericMethodHowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#2)]
    [!code-vb[GenericMethodHowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#2)]

3. Определите тип, которому принадлежит универсальный метод. Тип не обязательно должен быть универсальным. Универсальный метод может принадлежать универсальному или неуниверсальному типу. В этом примере тип представляет собой класс, не является универсальным и называется `DemoType`.

    [!code-csharp[GenericMethodHowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#3)]
    [!code-vb[GenericMethodHowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#3)]

4. Определите универсальный метод. Если типы формальных параметров универсального метода указаны с помощью параметров универсального типа универсального метода, используйте перегрузку метода <xref:System.Reflection.Emit.TypeBuilder.DefineMethod%28System.String%2CSystem.Reflection.MethodAttributes%29> для определения метода. Параметры универсального типа этого метода еще не определены, поэтому невозможно указать типы формальных параметров метода в вызове перегрузки <xref:System.Reflection.Emit.TypeBuilder.DefineMethod%2A>. В этом примере метод называется `Factory`. Метод является открытым и `static` (`Shared` в Visual Basic).

    [!code-csharp[GenericMethodHowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#4)]
    [!code-vb[GenericMethodHowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#4)]

5. Определите параметры универсального типа метода `DemoMethod` посредством передачи массива строк, содержащего имена параметров, в метод <xref:System.Reflection.Emit.MethodBuilder.DefineGenericParameters%2A?displayProperty=nameWithType>. Таким образом, этот метод станет универсальным. В следующем коде создается универсальный метод `Factory` с параметрами типа `TInput` и `TOutput`. Чтобы сделать код более удобным для чтения, создаются переменные с этими именами для хранения объектов <xref:System.Reflection.Emit.GenericTypeParameterBuilder>, представляющих два типа параметров.

    [!code-csharp[GenericMethodHowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#5)]
    [!code-vb[GenericMethodHowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#5)]

6. Дополнительно добавьте особые ограничения параметров типа. Особые объекты добавляются с помощью метода <xref:System.Reflection.Emit.GenericTypeParameterBuilder.SetGenericParameterAttributes%2A>. В этом примере `TOutput` ограничивается ссылочным типом и конструктором без параметров.

    [!code-csharp[GenericMethodHowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#6)]
    [!code-vb[GenericMethodHowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#6)]

7. Дополнительно добавьте ограничения класса и интерфейса в параметры типа. В этом примере параметр типа `TOutput` ограничен типами, которые реализуют интерфейс `ICollection(Of TInput)` (`ICollection<TInput>` в C#). Это гарантирует, что метод <xref:System.Collections.Generic.ICollection%601.Add%2A> можно использовать для добавления элементов.

    [!code-csharp[GenericMethodHowTo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#7)]
    [!code-vb[GenericMethodHowTo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#7)]

8. Определите формальные параметры метода, используя метод <xref:System.Reflection.Emit.MethodBuilder.SetParameters%2A>. В этом примере метод `Factory` имеет один параметр — массив `TInput`. Этот тип создается путем вызова метода <xref:System.Type.MakeArrayType%2A> для <xref:System.Reflection.Emit.GenericTypeParameterBuilder>, который представляет `TInput`. Аргументом метода <xref:System.Reflection.Emit.MethodBuilder.SetParameters%2A> является массив объектов <xref:System.Type>.

    [!code-csharp[GenericMethodHowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#8)]
    [!code-vb[GenericMethodHowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#8)]

9. Определить тип возвращаемого значения для этого метода с помощью метода <xref:System.Reflection.Emit.MethodBuilder.SetReturnType%2A>. В этом примере возвращается экземпляр `TOutput`.

    [!code-csharp[GenericMethodHowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#9)]
    [!code-vb[GenericMethodHowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#9)]

10. Выпустите основную часть метода с помощью <xref:System.Reflection.Emit.ILGenerator>. Дополнительные сведения см. в сопутствующей процедуре для создания тела метода.

    > [!IMPORTANT]
    > При выпуске вызовов методов универсального типа, если аргументы типа для этих типов являются параметрами типа универсального метода, необходимо использовать перегрузки метода `static` <xref:System.Reflection.Emit.TypeBuilder.GetConstructor%28System.Type%2CSystem.Reflection.ConstructorInfo%29>, <xref:System.Reflection.Emit.TypeBuilder.GetMethod%28System.Type%2CSystem.Reflection.MethodInfo%29> и <xref:System.Reflection.Emit.TypeBuilder.GetField%28System.Type%2CSystem.Reflection.FieldInfo%29> класса <xref:System.Reflection.Emit.TypeBuilder> для получения созданных форм этих методов. Это показано в сопутствующей процедуре выпуска основной части метода.

11. Завершите тип, который содержит метод, и сохраните сборку. В сопутствующей процедуре вызова универсального метода показаны два способа вызова завершенного метода.

    [!code-csharp[GenericMethodHowTo#14](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#14)]
    [!code-vb[GenericMethodHowTo#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#14)]

<a name="procedureSection1"></a>

### <a name="to-emit-the-method-body"></a>Выпуск основной части метода

1. Получите генератор кода и объявите локальные переменные и метки. Для объявления локальных переменных используется метод <xref:System.Reflection.Emit.ILGenerator.DeclareLocal%2A>. Метод `Factory` содержит четыре локальных переменных: `retVal` для хранения нового объекта `TOutput`, возвращенного методом, `ic` для хранения объекта `TOutput` при приведении его к `ICollection(Of TInput)` (`ICollection<TInput>` в C#), `input` для хранения входного массива объектов `TInput` и `index` для итерации в массиве. Этот метод также содержит две метки: одна для входа в цикл (`enterLoop`) и одна для вершины цикла (`loopAgain`), определенные с помощью метода <xref:System.Reflection.Emit.ILGenerator.DefineLabel%2A>.

    Первым действием этого метода является загрузка аргумента с помощью кода операции <xref:System.Reflection.Emit.OpCodes.Ldarg_0> и для хранения этого аргумента в локальной переменной `input` с помощью кода операции <xref:System.Reflection.Emit.OpCodes.Stloc_S>.

    [!code-csharp[GenericMethodHowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#10)]
    [!code-vb[GenericMethodHowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#10)]

2. Выпустите код для создания экземпляра `TOutput` с помощью перегрузки универсального метода <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>. При использовании этой перегрузки требуется наличие конструктора без параметров для указанного типа, что является причиной добавления ограничения к `TOutput`. Создайте универсальный метод, передав `TOutput` в метод <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A>. После выпуска кода для вызова метода выпустите код для хранения его в локальной переменной `retVal` с помощью параметра <xref:System.Reflection.Emit.OpCodes.Stloc_S>.

    [!code-csharp[GenericMethodHowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#11)]
    [!code-vb[GenericMethodHowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#11)]

3. Выпустите код для приведения нового объекта `TOutput` к `ICollection(Of TInput)` и сохранения его в локальной переменной `ic`.

    [!code-csharp[GenericMethodHowTo#31](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#31)]
    [!code-vb[GenericMethodHowTo#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#31)]

4. Получите объект <xref:System.Reflection.MethodInfo>, представляющий метод <xref:System.Collections.Generic.ICollection%601.Add%2A?displayProperty=nameWithType>. Этот метод работает с `ICollection(Of TInput)` (`ICollection<TInput>` в C#), поэтому необходимо получить метод `Add`, относящийся к этому сконструированному типу. Невозможно использовать метод <xref:System.Type.GetMethod%2A>, чтобы получить этот объект <xref:System.Reflection.MethodInfo> напрямую из `icollOfTInput`, так как <xref:System.Type.GetMethod%2A> не поддерживается для типа, который был сконструирован с <xref:System.Reflection.Emit.GenericTypeParameterBuilder>. Вместо этого вызовите <xref:System.Type.GetMethod%2A> для `icoll`, который содержит определение универсального типа для универсального интерфейса <xref:System.Collections.Generic.ICollection%601>. Затем с помощью метода <xref:System.Reflection.Emit.TypeBuilder.GetMethod%28System.Type%2CSystem.Reflection.MethodInfo%29>`static` создайте <xref:System.Reflection.MethodInfo> для сконструированного типа. Это демонстрируется в следующем коде.

    [!code-csharp[GenericMethodHowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#12)]
    [!code-vb[GenericMethodHowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#12)]

5. Выпустите код для инициализации переменной `index` путем загрузки 32-разрядного целого числа 0 и хранения его в переменной. Выпустите код перехода на метку `enterLoop`. Эта метка еще не была отмечена, так как она находится внутри цикла. Код для цикла выпускается на следующем этапе.

    [!code-csharp[GenericMethodHowTo#32](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#32)]
    [!code-vb[GenericMethodHowTo#32](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#32)]

6. Выпустите код для цикла. Первым действием является маркировка вершины цикла посредством вызова метода <xref:System.Reflection.Emit.ILGenerator.MarkLabel%2A> с меткой `loopAgain`. Операторы перехода, которые используют метку, теперь будут переходить на эту точку в коде. Следующим действием является передача объекта `TOutput`, приведенного к `ICollection(Of TInput)`, в стек. Это не является необходимым в данный момент, но должно быть подготовлено для вызова метода `Add`. Затем входной массив передается в стек, после чего в массив передается переменная `index`, содержащая текущий индекс. Код операции <xref:System.Reflection.Emit.OpCodes.Ldelem> принимает индекс и массив из стека и передает индексированный элемент массива в стек. Теперь стек готов для вызова метода <xref:System.Collections.Generic.ICollection%601.Add%2A?displayProperty=nameWithType>, который принимает коллекцию и новый элемент из стека и добавляет элемент в коллекцию.

    В оставшейся части кода цикла увеличивается индекс и проверяется, завершился ли цикл. Индекс и 32-разрядное целое число 1 передается в стек и суммируется, после чего сумма остается в стеке; сумма сохраняется в `index`. Метод <xref:System.Reflection.Emit.ILGenerator.MarkLabel%2A> вызывается для задания этой точки в качестве точки входа цикла. Снова загружается индекс. Входной массив передается в стек, и выпускается <xref:System.Reflection.Emit.OpCodes.Ldlen> для получения его длины. Теперь в стеке находятся индекс и длина, выпускается <xref:System.Reflection.Emit.OpCodes.Clt> для их сравнения. Если индекс меньше длины, <xref:System.Reflection.Emit.OpCodes.Brtrue_S> переходит обратно к началу цикла.

    [!code-csharp[GenericMethodHowTo#13](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#13)]
    [!code-vb[GenericMethodHowTo#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#13)]

7. Выпустите код для передачи объекта `TOutput` в стек и возврата из метода. Локальные переменные `retVal` и `ic` содержат ссылки на новый объект `TOutput`; `ic` используется только для доступа к методу <xref:System.Collections.Generic.ICollection%601.Add%2A?displayProperty=nameWithType>.

    [!code-csharp[GenericMethodHowTo#33](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#33)]
    [!code-vb[GenericMethodHowTo#33](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#33)]

<a name="procedureSection2"></a>

### <a name="to-invoke-the-generic-method"></a>Вызов универсального метода

1. `Factory` — это определение универсального метода. Чтобы вызывать его, необходимо назначить типы для его параметров универсального типа. Для этого используется метод <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A>. В следующем коде создается сконструированный универсальный метод, указывая <xref:System.String> для `TInput` и `List(Of String)` (`List<string>` в C#) для `TOutput`, а также отображает строковое представление метода.

    [!code-csharp[GenericMethodHowTo#21](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#21)]
    [!code-vb[GenericMethodHowTo#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#21)]

2. Чтобы вызвать позднюю привязку метода, используйте метод <xref:System.Reflection.MethodBase.Invoke%2A>. В следующем коде создается массив объектов <xref:System.Object>, в качестве единственного элемента содержащий массив строк, и передает его в качестве списка аргументов для универсального метода. Первый параметр <xref:System.Reflection.MethodBase.Invoke%2A> — это пустая ссылка, так как метод является `static`. Возвращаемое значение приводится к `List(Of String)`, затем отображается первый элемент.

    [!code-csharp[GenericMethodHowTo#22](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#22)]
    [!code-vb[GenericMethodHowTo#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#22)]

3. Чтобы вызвать метод с помощью делегата, необходимо иметь делегат, который соответствует сигнатуре сконструированного универсального метода. Простым способом выполнения этой задачи является создание универсального делегата. В следующем коде создается экземпляр универсального делегата `D`, определенного в примере кода, с помощью перегрузки метода <xref:System.Delegate.CreateDelegate%28System.Type%2CSystem.Reflection.MethodInfo%29?displayProperty=nameWithType>, а затем вызывается делегат. По своим возможностям делегаты превосходят вызовы с поздней привязкой.

    [!code-csharp[GenericMethodHowTo#23](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#23)]
    [!code-vb[GenericMethodHowTo#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#23)]

4. Выпущенный метод также может быть вызван из программы, которая ссылается на сохраненную сборку.

## <a name="example"></a>Пример

В следующем примере кода создается неуниверсальный тип `DemoType` с универсальным методом `Factory`. Этот метод имеет два параметра универсального типа: `TInput` для указания входного типа и `TOutput` для указания выходного типа. Параметр типа `TOutput` ограничен для реализации `ICollection<TInput>` (`ICollection(Of TInput)` в Visual Basic) в качестве ссылочного типа и для содержания конструктора без параметров.

Этот метод имеет один формальный параметр, который является массивом `TInput`. Метод возвращает экземпляр класса `TOutput`, содержащий все элементы входного массива. Экземпляр класса `TOutput` может быть любым универсальным типом коллекции, реализующим универсальный интерфейс <xref:System.Collections.Generic.ICollection%601>.

При выполнении этого кода динамическая сборка сохраняется как DemoGenericMethod1.dll и может быть проанализирована с помощью [Ildasm.exe (дизассемблера IL)](../tools/ildasm-exe-il-disassembler.md).

> [!NOTE]
> Хорошим способом изучения способов выпуска кода является написание программы на языке Visual Basic, C# или Visual C++, которая будет выполнять программу и использовать дизассемблер для изучения MSIL, созданного компилятором.

В примере кода содержится исходный код, который эквивалентен выпущенному методу. Выпущенный метод вызывается с поздней привязкой, а также с помощью универсального делегата, объявленного в примере кода.

[!code-csharp[GenericMethodHowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#1)]
[!code-vb[GenericMethodHowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#1)]

## <a name="see-also"></a>См. также

- <xref:System.Reflection.Emit.MethodBuilder>
- [Практическое руководство. Определение универсального типа с порождаемым отражением](how-to-define-a-generic-type-with-reflection-emit.md)
