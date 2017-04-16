---
title: "Dynamically Loading and Using Types | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "late binding, about late binding"
  - "early binding"
  - "dynamically loading and using types"
  - "implicit late binding"
  - "reflection, dynamically using types"
ms.assetid: db985bec-5942-40ec-b13a-771ae98623dc
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Dynamically Loading and Using Types
Механизм отражения создает инфраструктуру, используемую такими языковыми компиляторами, как [!INCLUDE[vbprvbext](../../../includes/vbprvbext-md.md)] и Jscript, для реализации неявной поздней привязки.  Привязка — это процесс поиска объявления \(т. е. реализации\), соответствующего однозначно заданному типу.  Когда данный процесс имеет место во время выполнения, а не во время компиляции, это называется поздним связыванием.  В [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] можно неявно использовать в коде позднее связывание; компилятор Visual Basic вызывает вспомогательный метод, который использует отражение для получения типа объектов.  Аргументы, переданные вспомогательному методу, обеспечивают вызов надлежащего метода во время выполнения.  Эти аргументы определяют экземпляр \(объект\), для которого вызывается метод, имя вызываемого метода \(строковый параметр\) и передаваемые этому методу аргументы \(массив объектов\).  
  
 В следующем примере компилятор Visual Basic неявно использует отражение для вызова метода объекта, тип которого во время компиляции неизвестен.  В классе **HelloWorld** содержится метод **PrintHello**, который выдает на печать строку "Hello World" вместе с текстом, переданным в метод **PrintHello**.  Вызываемый в этом примере метод **PrintHello** фактически является методом <xref:System.Type.InvokeMember%2A?displayProperty=fullName>; код Visual Basic позволяет вызвать метод **PrintHello** таким образом, словно тип объекта \(helloObj\) известен во время компиляции \(ранняя привязка\), а не во время выполнения \(поздняя привязка\).  
  
```  
Imports System  
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
  
## Настраиваемая привязка  
 Отражение может использоваться для обеспечения поздней привязки как неявно компиляторами, так и явным образом в коде.  
  
 [Среда CLR](../../../docs/standard/clr.md) поддерживает несколько языков программирования, и правила привязки в этих языках различаются.  В случае ранней привязки генераторы кода могут полностью контролировать этот процесс.  Однако поздняя привязка, осуществляемая с помощью отражения, должна контролироваться путем настройки привязки.  Класс <xref:System.Reflection.Binder> предоставляет настраиваемый элемент управления для выбора и вызова членов.  
  
 С помощью настраиваемой привязки можно загрузить сборку во время выполнения, получить сведения о типах, включенных в эту сборку, определить нужный тип, а затем вызвать методы или обратиться к полям или свойствам этого типа.  Такой способ применяется в том случае, если тип объекта во время компиляции неизвестен, например зависит от данных, введенных пользователем.  
  
 В следующем примере показан простой пользовательский связыватель, в котором не производится преобразование типов аргументов.  Основному примеру предшествует код `Simple_Type.dll`.  Необходимо выполнить построение библиотеки `Simple_Type.dll`, а затем включить в проект ссылку на нее во время построения.  
  
 [!code-cpp[Conceptual.Types.Dynamic#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.dynamic/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Types.Dynamic#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.dynamic/cs/source1.cs#1)]
 [!code-vb[Conceptual.Types.Dynamic#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.dynamic/vb/source1.vb#1)]  
  
### InvokeMember и CreateInstance  
 Класс <xref:System.Type.InvokeMember%2A?displayProperty=fullName> служит для обращения к члену или типу.  Методы **CreateInstance** различных классов, таких как [System.Activator](frlrfSystemActivatorClassCreateInstanceTopic) и [System.Reflection.Assembly](frlrfSystemReflectionAssemblyClassCreateInstanceTopic), являются специальными формами метода **InvokeMember**, которые создают новые экземпляры заданного типа.  Для разрешения перегруженных версий и приведения аргументов в этих методах используется класс **Binder**.  
  
 В следующем примере показаны три возможных сочетания приведения аргументов \(преобразования типов\) и выбора членов.  В первом случае \(Case 1\) не требуется выполнять ни приведение аргументов, ни выбор членов.  Во втором случае \(Case 2\) необходим только выбор членов.  В третьем случае \(Case 3\) необходимо только приведение аргументов.  
  
 [!code-cpp[Conceptual.Types.Dynamic#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.dynamic/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Types.Dynamic#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.dynamic/cs/source2.cs#2)]
 [!code-vb[Conceptual.Types.Dynamic#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.dynamic/vb/source2.vb#2)]  
  
 Разрешение перегруженных версий необходимо при наличии нескольких членов с одним именем.  Для разрешения привязки к отдельному члену используются методы <xref:System.Reflection.Binder.BindToMethod%2A?displayProperty=fullName> и <xref:System.Reflection.Binder.BindToField%2A?displayProperty=fullName>.  Метод **Binder.BindToMethod** также обеспечивает разрешение свойств при помощи методов обращения к свойствам **get** и **set**.  
  
 Если подобный вызов невозможен, метод **BindToMethod** возвращает вызываемый объект <xref:System.Reflection.MethodBase> или пустую ссылку \(**Nothing** в Visual Basic\).  Возвращаемое значение метода **MethodBase** не обязано относиться к значениям, содержащимся в параметре *match*, хотя это обычно имеет место.  
  
 Если часть аргументов передается по ссылке, возможно, их потребуется возвратить в вызывающий код.  Таким образом, объект **Binder** клиенту сопоставить массив аргументов обратно его исходной форме, если массив аргументов был изменен методом **BindToMethod**.  Для этого необходимо гарантировать, что порядок аргументов, возвращаемых в вызывающий код, не изменится.  Если аргументы передаются по имени, объект **Binder** изменяет порядок массива аргументов и в таком виде массив передается в вызывающий код.  Для получения дополнительной информации см. <xref:System.Reflection.Binder.ReorderArgumentArray%2A?displayProperty=fullName>.  
  
 Набор доступных членов состоит из членов, определенных в этом типе или в каком\-либо базовом типе.  Если установлен флаг [BindingFlags.NonPublic](frlrfSystemReflectionBindingFlagsClassTopic), в наборе будут возвращены члены с любым уровнем доступности.  Если флаг **BindingFlags.NonPublic** не установлен, связыватель должен проследить за соблюдением правил доступности.  При определении флага привязки **Public** или **NonPublic** необходимо также установить флаг привязки **Instance** или **Static**. В обратном случае члены не будут возвращены.  
  
 Если существует только один член с данным именем, обратный вызов не требуется и привязка для этого метода считается выполненной.  Этому варианту соответствует первый вариант \(Case 1\) в приведенном выше примере: доступен только один метод **PrintBob** и поэтому обратный вызов не требуется.  
  
 Если в доступном наборе содержится несколько членов, все они передаются в метод **BindToMethod**, который выбирает нужный метод и возвращает его.  Во втором случае \(Case 2\) в рассматриваемом примере кода существуют два метода с именем **PrintValue**.  Нужный метод выбирается при помощи вызова метода **BindToMethod**.  
  
 Метод <xref:System.Reflection.Binder.ChangeType%2A> выполняет приведение аргументов \(приведение типов\), при котором фактические аргументы преобразуются в тип формальных аргументов выбранного метода.  Метод **ChangeType** вызывается для каждого аргумента, даже если типы полностью совпадают.  
  
 В третьем случае \(Case 3\) рассматриваемого примера фактический аргумент типа **String** , имеющий значение "5.5", передается в метод с помощью формального аргумента типа **Double**.  Чтобы вызов был успешным, строковое значение "5.5" должно быть преобразовано в тип "double".  Это преобразование выполняет метод **ChangeType**.  
  
 Метод **ChangeType** выполняет только приведение без потерь, иначе называемое [расширяющее приведение](../../../docs/standard/base-types/type-conversion.md), что показано в следующей ниже таблице.  
  
|Исходный тип|Целевой тип|  
|------------------|-----------------|  
|Любой тип|Соответствующий базовый тип|  
|Любой тип|Реализуемый интерфейс|  
|Char|UInt16, UInt32, Int32, UInt64, Int64, Single, Double|  
|Byte|Char, UInt16, Int16, UInt32, Int32, UInt64, Int64, Single, Double|  
|SByte|Int16, Int32, Int64, Single, Double|  
|UInt16|UInt32, Int32, UInt64, Int64, Single, Double|  
|Int16|Int32, Int64, Single, Double|  
|UInt32|UInt64, Int64, Single, Double|  
|Int32|Int64, Single, Double|  
|UInt64|Single, Double|  
|Int64|Single, Double|  
|Single|Double|  
|Нессылочный тип|Ссылочный тип|  
  
 В классе <xref:System.Type> содержатся методы **Get**, которые используют параметры с типом **Binder** для разрешения ссылок на конкретный член.  Поиск <xref:System.Type.GetConstructor%2A?displayProperty=fullName>, <xref:System.Type.GetMethod%2A?displayProperty=fullName> и <xref:System.Type.GetProperty%2A?displayProperty=fullName> определенного члена текущего типа путем предоставления сведений о сигнатуре этого члена.  Методы <xref:System.Reflection.Binder.SelectMethod%2A?displayProperty=fullName> и <xref:System.Reflection.Binder.SelectProperty%2A?displayProperty=fullName> вызываются обратно, чтобы выбрать сведения о заданной сигнатуре соответствующих методов.  
  
## См. также  
 <xref:System.Type.InvokeMember%2A?displayProperty=fullName>   
 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>   
 [Viewing Type Information](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)   
 [Преобразование типов в .NET Framework](../../../docs/standard/base-types/type-conversion.md)