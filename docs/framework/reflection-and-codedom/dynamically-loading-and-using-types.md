---
title: Динамическая загрузка и использование типов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- late binding, about late binding
- early binding
- dynamically loading and using types
- implicit late binding
- reflection, dynamically using types
ms.assetid: db985bec-5942-40ec-b13a-771ae98623dc
ms.openlocfilehash: 940f334ec6a42c4d8da461d634051ff979b8f98d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130268"
---
# <a name="dynamically-loading-and-using-types"></a>Динамическая загрузка и использование типов
Отражение предоставляет инфраструктуру, с помощью которой компиляторы различных языков реализуют неявное позднее связывание. Привязка — это процесс поиска объявления (то есть реализации), которое соответствует уникально определенному типу. Если этот процесс происходит во время выполнения, а не во время компиляции, он называется поздним связыванием. Visual Basic позволяет применять неявное позднее связывание в коде. Компилятор Visual Basic вызывает вспомогательный метод, который использует отражение для получения типа объекта. Аргументы, передаваемые вспомогательному методу, приводят к вызову соответствующего метода во время выполнения. Эти аргументы определяют экземпляр (объект), для которого вызывается метод, имя вызываемого метода (строка) и аргументы, передаваемые в вызываемый метод (массив объектов).  
  
 В следующем примере компилятор Visual Basic неявно использует отражение для вызова метода объекта, тип которого неизвестен во время компиляции. Класс **HelloWorld** содержит метод **PrintHello**, который выводит строку "Hello World" с некоторым текстом, который передается в метод **PrintHello**. Метод **PrintHello**, вызываемый в этом примере, на самом деле представляет собой <xref:System.Type.InvokeMember%2A?displayProperty=nameWithType>; код Visual Basic позволяет вызывать метод **PrintHello** так, как если бы тип объекта (helloObj) был известен уже во время компиляции (ранняя привязка), а не только во время выполнения (позднее связывание).  
  
```vb
Module Hello  
    Sub Main()  
        ' Sets up the variable.  
        Dim helloObj As Object  
        ' Creates the object.  
        helloObj = new HelloWorld()  
        ' Invokes the print method as if it was early bound  
        ' even though it is really late bound.  
        helloObj.PrintHello("Visual Basic Late Bound")  
    End Sub  
End Module  
```  
  
## <a name="custom-binding"></a>Пользовательская привязка  
 Наряду с использованием в компиляторах для позднего связывания отражение можно явно использовать в коде для полного связывания.  
  
 [Общеязыковая среда выполнения](../../standard/clr.md) поддерживает несколько языков программирования, и правила связывания в этих языках различаются. В случае раннего связывания генераторы кода могут полностью управлять этим связыванием. Однако в случае позднего связывания через отражение связыванием необходимо управлять с помощью пользовательского связывания. Класс <xref:System.Reflection.Binder> предоставляет пользовательский элемент управления для выбора и вызова элемента.  
  
 С помощью пользовательского связывания можно загрузить сборку во время выполнения, получить сведения о типах в этой сборке, определить нужный тип, а затем вызывать методы или обращаться к полям или свойствам этого типа. Этот способ полезен, если тип объекта во время компиляции неизвестен, например, если тип объекта зависит от входных данных пользователя.  
  
 Ниже приведен простой пользовательский класс привязки без преобразования типов аргументов. Код `Simple_Type.dll` приведен перед основным примером. Соберите `Simple_Type.dll`, а затем включите в проект ссылку на него во время сборки.  
  
 [!code-cpp[Conceptual.Types.Dynamic#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.dynamic/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Types.Dynamic#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.dynamic/cs/source1.cs#1)]
 [!code-vb[Conceptual.Types.Dynamic#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.dynamic/vb/source1.vb#1)]  
  
### <a name="invokemember-and-createinstance"></a>InvokeMember и CreateInstance  
 Используйте <xref:System.Type.InvokeMember%2A?displayProperty=nameWithType> для вызова члена типа. Методы **CreateInstance** различных классов, таких как <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> и <xref:System.Reflection.Assembly.CreateInstance%2A?displayProperty=nameWithType>, представляют собой специализированные варианты метода **InvokeMember**, которые создают новые экземпляры указанного типа. Класс **Binder** используется для разрешения перегрузки и приведения аргументов в этих методах.  
  
 В следующем примере показаны три возможных сочетания приведения аргументов (преобразования типов) и выбора членов. В первом случае ни приведение аргументов, ни выбор членов не требуются. Во втором случае требуется только выбор членов. В третьем случае требуется только приведение аргументов.  
  
 [!code-cpp[Conceptual.Types.Dynamic#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.dynamic/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Types.Dynamic#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.dynamic/cs/source2.cs#2)]
 [!code-vb[Conceptual.Types.Dynamic#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.dynamic/vb/source2.vb#2)]  
  
 Разрешение перегрузки необходимо, если существует несколько членов с одинаковыми именами. Методы <xref:System.Reflection.Binder.BindToMethod%2A?displayProperty=nameWithType> и <xref:System.Reflection.Binder.BindToField%2A?displayProperty=nameWithType> используются для разрешения привязки к одному члену. Метод **Binder.BindToMethod** также обеспечивает разрешение свойств с помощью методов доступа к свойствам **get** и **set**.  
  
 Метод **BindToMethod** возвращает вызывающему объекту <xref:System.Reflection.MethodBase> или пустую ссылку (в Visual Basic **не возвращает ничего**), если такой вызов невозможен. Возвращаемое значение метода **MethodBase** не обязательно должно содержаться в параметре *match*, хотя обычно это имеет место.  
  
 При наличии аргументов ByRef может потребоваться вернуть их для вызывающего объекта. Таким образом, класс **Binder** позволяет клиенту вернуть массив аргументов в исходную форму, если метод **BindToMethod** изменил массив аргументов. Для этого необходимо гарантировать вызывающему объекту, что порядок аргументов не изменяется. Если аргументы передаются по имени, класс **Binder** изменяет порядок аргументов в массиве, и это видит вызывающий объект. Для получения дополнительной информации см. <xref:System.Reflection.Binder.ReorderArgumentArray%2A?displayProperty=nameWithType>.  
  
 В набор доступных членов входят члены, которые определены в типе или любом базовом типе. Если указан параметр <xref:System.Reflection.BindingFlags>, в наборе будут возвращены члены с любым уровнем доступности. Если параметр **BindingFlags.NonPublic** не указан, модуль привязки должен применить правила доступа. Если указан флаг привязки **Public** или **NonPublic**, необходимо также указать флаг привязки **Instance** или **Static**, в противном случае ни одного члена не будет возвращено.  
  
 Если имеется только один член с заданным именем, обратный вызов не требуется и привязка для этого метода считается выполненной. Этот аспект иллюстрируется в первом примере: доступен только метод **PrintBob**, поэтому обратный вызов не требуется.  
  
 Если в доступном наборе содержится несколько членов, все эти методы передаются методу **BindToMethod**, который выбирает нужный метод и возвращает его. Во втором примере кода есть два метода с именем **PrintValue**. Нужный метод выбирается с помощью вызова метода **BindToMethod**.  
  
 <xref:System.Reflection.Binder.ChangeType%2A> выполняет приведение аргументов (преобразование типов), при котором фактические аргументы преобразуются к типу формальных аргументов выбранного метода. Метод **ChangeType** вызывается для каждого аргумента, даже если типы полностью совпадают.  
  
 В третьем примере фактический аргумент типа **String** со значением "5.5" передается в метод с помощью формального аргумента типа **Double**. Чтобы вызов был успешным строковое значение "5.5" необходимо преобразовать в тип Double. Метод **ChangeType** выполняет это преобразование.  
  
 Метод **ChangeType** выполняет только приведение без потерь, или [расширяющее приведение](../../standard/base-types/type-conversion.md), как показано в следующей таблице.  
  
|Тип исходного значения|Тип результирующего значения|  
|-----------------|-----------------|  
|Любой тип|Его базовый тип|  
|Любой тип|Интерфейс, который он реализует|  
|Char|UInt16, UInt32, Int32, UInt64, Int64, Single, Double|  
|Байт|Char, UInt16, Int16, UInt32, Int32, UInt64, Int64, Single, Double|  
|SByte|Int16, Int32, Int64, Single, Double|  
|UInt16|UInt32, Int32, UInt64, Int64, Single, Double|  
|Int16|Int32, Int64, Single, Double|  
|UInt32|UInt64, Int64, Single, Double|  
|Int32|Int64, Single, Double|  
|UInt64|Single, Double|  
|Int64|Single, Double|  
|Single|Double|  
|Нессылочный тип|Ссылочный тип|  
  
 Класс <xref:System.Type> содержит методы **Get**, которые используют параметры типа **Binder**, чтобы разрешить ссылки на конкретный член. Методы <xref:System.Type.GetConstructor%2A?displayProperty=nameWithType>, <xref:System.Type.GetMethod%2A?displayProperty=nameWithType> и <xref:System.Type.GetProperty%2A?displayProperty=nameWithType> выполняют поиск определенного члена текущего типа по сведениям о подписи для этого члена. Методы <xref:System.Reflection.Binder.SelectMethod%2A?displayProperty=nameWithType> и <xref:System.Reflection.Binder.SelectProperty%2A?displayProperty=nameWithType> используются в качестве методов обратного вызова для выбора заданных сведений о подписи для соответствующих методов.  
  
## <a name="see-also"></a>См. также

- <xref:System.Type.InvokeMember%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>
- [Просмотр сведений о типах](viewing-type-information.md)
- [Преобразование типов в .NET Framework](../../standard/base-types/type-conversion.md)
