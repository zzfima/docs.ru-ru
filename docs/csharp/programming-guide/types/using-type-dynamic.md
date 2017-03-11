---
title: "Использование типа dynamic (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "dynamic [C#], сведения о типе dynamic"
  - "тип dynamic [C#]"
ms.assetid: 3828989d-c967-4a51-b948-857ebc8fdf26
caps.latest.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# Использование типа dynamic (Руководство по программированию на C#)
В [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp-dev10-long-md.md)] появился новый тип — `dynamic`.  Тип является статическим типом, но объект типа `dynamic` обходит проверку статического типа.  В большинстве случаев он функционирует, как тип `object`.  Во время компиляции предполагается что элементы с типом `dynamic` поддерживают любые операции.  Поэтому разработчику не нужно следить за тем, откуда объект получает свое значение — из интерфейса API COM, из динамического языка, такого как IronPython, из объектной модели DOM HTML, из отражения или из любого другого места программы.  Но если код является недействительным, во время выполнения перехватываются ошибки.  
  
 Например, если у метода `exampleMethod1` экземпляра в следующем коде имеется только один параметр, компилятор определяет, что первый вызов метода \(`ec.exampleMethod1(10, 4)`\) является недопустимым, поскольку он содержит два аргумента.  Такой вызов приводит к ошибке компилятора.  Второй вызов метода `dynamic_ec.exampleMethod1(10, 4)` не проверяется компилятором, поскольку тип `dynamic_ec` является типом `dynamic`.  Поэтому ошибка компилятора не возникает.  Однако ошибка не остается незамеченной и не приводит к неопределенному результату.  Она перехватывается во время выполнения и вызывает исключение времени выполнения.  
  
 [!code-cs[CsProgGuideTypes#50](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-type-dynamic_1.cs)]  
  
 [!code-cs[CsProgGuideTypes#56](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-type-dynamic_2.cs)]  
  
 Роль компилятора в этом примере состоит в том, чтобы объединить информацию о предполагаемых действиях каждой инструкции над объектом или выражением, которые имеют тип `dynamic`.  Во время выполнения хранимая информация проверяется, и все инструкции, которые не являются допустимыми, вызывают исключение времени выполнения.  
  
 Результат большинства динамических операций сам по себе имеет тип `dynamic`.  Например, если в следующем примере кода навести указатель мыши на вызов `testSum`, IntelliSense отобразит тип **\(локальная переменная\) dynamic testSum**.  
  
 [!code-cs[CsProgGuideTypes#51](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-type-dynamic_3.cs)]  
  
 К операциям, результат которых не имеет тип `dynamic`, относятся преобразования из `dynamic` в другой тип и вызовы конструкторов, включающих аргументы типа `dynamic`.  Например, в следующем примере типом `testInstance` будет `ExampleClass`, а не `dynamic`.  
  
 [!code-cs[CsProgGuideTypes#52](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-type-dynamic_4.cs)]  
  
 Примеры преобразований представлены далее в разделе "Преобразования".  
  
## Преобразования  
 Выполнять преобразования между динамическими объектами и другими типами очень просто.  Это позволяет разработчику переключаться между динамическим и нединамическим поведением.  
  
 Любой объект можно преобразовать в динамический неявным образом, как показано в следующих примерах.  
  
 [!code-cs[CsProgGuideTypes#53](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-type-dynamic_5.cs)]  
  
 Аналогично неявное преобразование можно динамически применить к выражению типа `dynamic`.  
  
 [!code-cs[CsProgGuideTypes#54](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-type-dynamic_6.cs)]  
  
## Разрешение перегрузки с аргументами типа dynamic  
 Разрешение перегрузки происходит во время выполнения, а не во время компиляции, если один или более аргументов в вызове метода относятся к типу `dynamic`, или если получатель вызова метода имеет тип `dynamic`.  Если в следующем примере единственный доступный метод `exampleMethod2` должен принимать строковый аргумент, передача в качестве аргумента значения `d1` не приведет к ошибке компилятора, но вызовет исключение времени выполнения.  Разрешение перегрузки во время выполнения приводит к исключению, поскольку во время выполнения `d1` имеет тип `int`, а метод `exampleMethod2` принимает строковый аргумент.  
  
 [!code-cs[CsProgGuideTypes#55](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/using-type-dynamic_7.cs)]  
  
## Среда DLR  
 Среда DLR — это новый интерфейс API в [!INCLUDE[net_v40_short](../../../csharp/programming-guide/types/includes/net-v40-short-md.md)].  Она обеспечивает инфраструктуру, поддерживающую тип `dynamic` в C\#, а также реализацию языков динамического программирования, таких как IronPython и IronRuby.  Дополнительные сведения о среде DLR см. в разделе [Dynamic Language Runtime Overview](../Topic/Dynamic%20Language%20Runtime%20Overview.md).  
  
## COM\-взаимодействие  
 В [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp-dev10-long-md.md)] имеется несколько функций, улучшающих взаимодействие с интерфейсами API COM, такими как API автоматизации Office.  К таким усовершенствованиями относятся тип `dynamic` и [именованные и необязательные аргументы](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md).  
  
 Многие методы COM допускают изменение типов аргументов и возвращаемых типов за счет определение типов в виде `object`.  Ранее это требовало явного приведения значений в соответствии со строго типизированными переменными в C\#.  При компиляции с использованием параметра [\/link \(Link to COM Assembly\)](../../../csharp/language-reference/compiler-options/link-compiler-option.md) появление типа `dynamic` позволяет обрабатывать вхождения `object` в сигнатурах COM, как если бы они имели тип `dynamic`, и, следовательно, избегать большей части операций приведения.  Например, следующие инструкции показывают различия в обращении к ячейке в таблице Microsoft Office Excel с использованием типа `dynamic` и без использования типа `dynamic`.  
  
 [!code-cs[csOfficeWalkthrough#12](../../../csharp/programming-guide/interop/codesnippet/csharp/officewalkthroughcs/thisaddin.cs#12)]  
  
 [!code-cs[csOfficeWalkthrough#13](../../../csharp/programming-guide/interop/codesnippet/csharp/officewalkthroughcs/thisaddin.cs#13)]  
  
## Связанные разделы  
  
|Заголовок|Описание|  
|---------------|--------------|  
|[dynamic](../../../csharp/language-reference/keywords/dynamic.md)|Описание использования ключевого слова `dynamic`.|  
|[Dynamic Language Runtime Overview](../Topic/Dynamic%20Language%20Runtime%20Overview.md)|Обзор среды DLR, которая представляет собой среду выполнения, добавляющую набор служб для динамических языков в среду CLR.|  
|[Пошаговое руководство. Создание и использование динамических объектов](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)|Предоставление пошаговых руководств для создания пользовательских динамических объектов и проекта, который имеет доступ к библиотеке `IronPython`.|  
|[Практическое руководство. Доступ к объектам взаимодействия Office с помощью функций языка Visual C\#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)|Демонстрация процедуры создания проекта, использующего именованные и необязательные аргументы, тип `dynamic` и другие усовершенствованные возможности, которые упрощают обращение к объектам API Office.|