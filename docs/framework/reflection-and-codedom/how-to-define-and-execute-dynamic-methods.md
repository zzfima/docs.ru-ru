---
title: "How to: Define and Execute Dynamic Methods | Microsoft Docs"
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
  - "reflection emit, dynamic methods"
  - "dynamic methods"
ms.assetid: 07d08a99-62c5-4254-bce2-2a75e55a18ab
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# How to: Define and Execute Dynamic Methods
В следующих процедурах показаны способы определения и выполнения простого динамического метода и динамического метода, привязанного к экземпляру класса.  Дополнительные сведения о динамических методах см. в описании класса <xref:System.Reflection.Emit.DynamicMethod> и в разделе [Reflection Emit Dynamic Method Scenarios](http://msdn.microsoft.com/ru-ru/7c27ea3d-0f24-4bf3-8ceb-f49d33faca5e).  
  
### Чтобы определить и выполнить динамический метод  
  
1.  Объявите тип делегата для выполнения метода.  Рассмотрите возможность использования универсального делегата для уменьшения числа типов делегата, которые необходимо будет объявлять.  В следующем коде объявляются два типа делегата, которые могут быть использованы для метода `SquareIt`. Один из этих типов является универсальным.  
  
     [!code-cpp[DynamicMethodHowTo#2](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#2)]
     [!code-csharp[DynamicMethodHowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#2)]
     [!code-vb[DynamicMethodHowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#2)]  
  
2.  Создайте массив, в котором будут указаны типы параметров динамического метода.  В этом примере единственным параметром является `int` \(`Integer` в Visual Basic\), так что массив содержит только один элемент.  
  
     [!code-cpp[DynamicMethodHowTo#3](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#3)]
     [!code-csharp[DynamicMethodHowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#3)]
     [!code-vb[DynamicMethodHowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#3)]  
  
3.  Создайте <xref:System.Reflection.Emit.DynamicMethod>.  В этом примере метод называется `SquareIt`.  
  
    > [!NOTE]
    >  Нет необходимости предоставлять имена динамических методов, они не могут быть вызваны по именам.  Несколько динамических методов могут иметь одинаковое имя.  Однако это имя отображается в стеках вызовов и может оказаться полезным при отладке.  
  
     Тип возвращаемого значения указан как `long`.  Этот метод связан с модулем, содержащим класс `Example`, в котором расположен код примера.  Может быть указан любой загруженный модуль.  Динамический метод выполняется как метод `static` уровня модуля \(`Shared` в Visual Basic\).  
  
     [!code-cpp[DynamicMethodHowTo#4](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#4)]
     [!code-csharp[DynamicMethodHowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#4)]
     [!code-vb[DynamicMethodHowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#4)]  
  
4.  Выпустите основную часть метода.  В этом примере объект <xref:System.Reflection.Emit.ILGenerator> используется для выпуска MSIL.  В качестве альтернативы объект <xref:System.Reflection.Emit.DynamicILInfo> может быть использован вместе с генераторами неуправляемого кода для выпуска основной части метода для <xref:System.Reflection.Emit.DynamicMethod>.  
  
     MSIL в этом примере загружает аргумент, который является `int`, в стек, преобразует его в `long`, дублирует `long` и умножает два значения.  Эти действия приводят к появлению в стеке возведенного в квадрат значения, поэтому методу остается только вернуться.  
  
     [!code-cpp[DynamicMethodHowTo#5](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#5)]
     [!code-csharp[DynamicMethodHowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#5)]
     [!code-vb[DynamicMethodHowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#5)]  
  
5.  Создайте экземпляр делегата \(объявлен на этапе 1\), который представляет динамический метод посредством вызова метода <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A>.  Создание делегата завершает этот метод, любые дальнейшие попытки изменить этот метод, например добавить MSIL, будут игнорироваться.  В следующем коде создается и вызывается делегат с помощью универсального делегата.  
  
     [!code-cpp[DynamicMethodHowTo#6](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#6)]
     [!code-csharp[DynamicMethodHowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#6)]
     [!code-vb[DynamicMethodHowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#6)]  
  
### Чтобы определить и выполнить динамический метод, привязанный к объекту  
  
1.  Объявите тип делегата для выполнения метода.  Рассмотрите возможность использования универсального делегата для уменьшения числа типов делегата, которые необходимо будет объявлять.  В следующем примере кода объявляется делегат универсального типа, который может быть использован для выполнения любого метода с одним параметром и возвращаемым значением или метода с двумя параметрами и возвращаемым значением, если делегат привязан к объекту.  
  
     [!code-cpp[DynamicMethodHowTo#12](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#12)]
     [!code-csharp[DynamicMethodHowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#12)]
     [!code-vb[DynamicMethodHowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#12)]  
  
2.  Создайте массив, в котором будут указаны типы параметров динамического метода.  Если делегат, представляющий метод, должен быть привязан к объекту, первый параметр должен соответствовать типу, к которому привязывается делегат.  В этом примере используются два параметра: один типа `Example`, а другой типа `int` \(`Integer` в Visual Basic\).  
  
     [!code-cpp[DynamicMethodHowTo#13](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#13)]
     [!code-csharp[DynamicMethodHowTo#13](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#13)]
     [!code-vb[DynamicMethodHowTo#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#13)]  
  
3.  Создайте <xref:System.Reflection.Emit.DynamicMethod>.  В этом примере не задано имя для данного метода.  Тип возвращаемого значения указан как `int` \(`Integer` в Visual Basic\).  Этот метод имеет доступ к закрытым и защищенным элементам класса `Example`.  
  
     [!code-cpp[DynamicMethodHowTo#14](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#14)]
     [!code-csharp[DynamicMethodHowTo#14](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#14)]
     [!code-vb[DynamicMethodHowTo#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#14)]  
  
4.  Выпустите основную часть метода.  В этом примере объект <xref:System.Reflection.Emit.ILGenerator> используется для выпуска MSIL.  В качестве альтернативы объект <xref:System.Reflection.Emit.DynamicILInfo> может быть использован вместе с генераторами неуправляемого кода для выпуска основной части метода для <xref:System.Reflection.Emit.DynamicMethod>.  
  
     В этом примере MSIL загружает первый аргумент, которым является экземпляр класса `Example`, и использует его для загрузки значения закрытого поля экземпляра типа `int`.  Загружается второй аргумент, после чего два числа перемножаются.  Если результат превышает значение `int`, то результат усекается и отбрасываются старшие разряды.  Метод возвращается с возвращаемым значением, содержащимся в стеке.  
  
     [!code-cpp[DynamicMethodHowTo#15](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#15)]
     [!code-csharp[DynamicMethodHowTo#15](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#15)]
     [!code-vb[DynamicMethodHowTo#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#15)]  
  
5.  Создайте экземпляр делегата \(объявленного на этапе 1\), который представляет динамический метод посредством вызова перегрузки метода <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%28System.Type%2CSystem.Object%29>.  Создание делегата завершает этот метод, любые дальнейшие попытки изменить этот метод, например добавить MSIL, будут игнорироваться.  
  
    > [!NOTE]
    >  Можно вызвать метод <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A> несколько раз для создания делегатов, привязанных к другим экземплярам целевого типа.  
  
     В следующем примере кода показано, как выполнить привязку метода к новому экземпляру класса `Example`, закрытое свойство проверки которого равняется 42.  Т. е. при каждом вызове делегата экземпляр `Example` передается первому параметру метода.  
  
     Делегат `OneParameter` используется, так как первый параметр метода всегда получает экземпляр `Example`.  При вызове делегата требуется только второй параметр.  
  
     [!code-cpp[DynamicMethodHowTo#16](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#16)]
     [!code-csharp[DynamicMethodHowTo#16](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#16)]
     [!code-vb[DynamicMethodHowTo#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#16)]  
  
## Пример  
 В следующем примере кода показано выполнение простого динамического метода и динамического метода, привязанного к экземпляру класса.  
  
 Простой динамический метод принимает один аргумент, 32\-разрядное целое число, и возвращает 64\-разрядное значение квадрата этого целого числа.  Для вызова этого метода используется универсальный делегат.  
  
 Во втором динамическом метода содержится два параметра типа `Example` и `int` \(`Integer` в Visual Basic\).  При создании динамического метода он привязывается к экземпляру `Example` с помощью универсального делегата, который имеет только один аргумент типа `int`.  Делегат не имеет аргумента типа `Example`, потому что первый параметр метода всегда получает привязанный экземпляр `Example`.  При вызове делегата предоставляется только аргумент `int`.  Этот динамический метод получает доступ к закрытому полю класса `Example` и возвращает продукт закрытого поля и аргумента `int`.  
  
 В этом примере кода определяются делегаты, которые могут быть использованы для выполнения методов.  
  
 [!code-cpp[DynamicMethodHowTo#1](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#1)]
 [!code-csharp[DynamicMethodHowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#1)]
 [!code-vb[DynamicMethodHowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#1)]  
  
## Компиляция кода  
  
-   Код содержит операторы C\# `using` \(`Imports` в Visual Basic\), необходимые для компиляции.  
  
-   Дополнительные ссылки на сборки не требуются.  
  
-   Откомпилируйте код из командной строки, используя команды csc.exe, vbc.exe или cl.exe.  Чтобы откомпилировать код в Visual Studio, поместите его в шаблон проекта консольного приложения.  
  
## См. также  
 <xref:System.Reflection.Emit.DynamicMethod>   
 [Using Reflection Emit](http://msdn.microsoft.com/ru-ru/ccc6540d-0e2c-4d89-b456-eb7353f9e9ac)   
 [Reflection Emit Dynamic Method Scenarios](http://msdn.microsoft.com/ru-ru/7c27ea3d-0f24-4bf3-8ceb-f49d33faca5e)