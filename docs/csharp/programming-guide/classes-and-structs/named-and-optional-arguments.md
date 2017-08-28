---
title: "Именованные и необязательные аргументы (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- namedParameter_CSharpKeyword
- cs_namedParameter
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], named
- named arguments [C#]
- arguments [C#], named
- optional arguments [C#]
- arguments [C#], optional
- parameters [C#], optional
- named and optional arguments [C#]
ms.assetid: 839c960c-c2dc-4d05-af4d-ca5428e54008
caps.latest.revision: 43
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c4da026d7ad38976565cbaad930652670aed2854
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="named-and-optional-arguments-c-programming-guide"></a>Именованные и необязательные аргументы (Руководство по программированию на C#)
[!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)] вводит именованные и необязательные аргументы. *Именованные аргументы* позволяют указать аргумент для определенного параметра, связав этот аргумент с именем параметра, а не с его позицией в списке параметров. *Необязательные аргументы* позволяют опускать аргументы для некоторых параметров. Оба варианта можно использовать с методами, индексаторами, конструкторами и делегатами.  
  
 При использовании именованных и необязательных аргументов аргументы оцениваются в том порядке, в котором они отображаются в списке аргументов, а не в списке параметров.  
  
 При совместном использовании именованные и необязательные параметры позволяют задавать аргументы только для некоторых параметров из списка необязательных параметров. Эта возможность значительно упрощает вызов интерфейсов COM, таких как API автоматизации Microsoft Office.  
  
## <a name="named-arguments"></a>Именованные аргументы  
 Именованные аргументы освобождают разработчика от необходимости запоминать или уточнять порядок параметров в списках параметров вызванных методов. Параметр для каждого аргумента можно указать, используя имя параметра. Например, функция, которая вычисляет индекс массы тела (BMI), может вызываться как обычно, путем передачи аргументов для веса и роста по позиции в порядке, определяемом функцией.  
  
 `CalculateBMI(123, 64);`  
  
 Если вы не помните порядок параметров, но знаете их имена, можете передать аргументы в любом порядке, начиная либо с веса, либо с роста.  
  
 `CalculateBMI(weight: 123, height: 64);`  
  
 `CalculateBMI(height: 64, weight: 123);`  
  
 Именованные аргументы также делают код более удобным для чтения, поскольку указывают, чему соответствует каждый аргумент.  
  
 Именованный аргумент может следовать за позиционными аргументами, как показано ниже.  
  
 `CalculateBMI(123, height: 64);`  
  
 При этом за именованным аргументом позиционный аргумент идти не может. Следующий код вызывает ошибку компилятора.  
  
 `//CalculateBMI(weight: 123, 64);`  
  
## <a name="example"></a>Пример  
 Следующий код реализует примеры из этого раздела.  
  
 [!code-cs[csProgGuideNamedAndOptional#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_1.cs)]  
  
## <a name="optional-arguments"></a>Необязательные аргументы  
 Определение метода, конструктора, индексатора или делегата может указывать, являются его параметры обязательными или нет. Любой вызов должен содержать аргументы для всех обязательных параметров; аргументы для необязательных параметров можно опустить.  
  
 Определение каждого необязательного параметра содержит его значение по умолчанию. Если аргумент для параметра не передается, используется значение по умолчанию. Значением по умолчанию должен быть один из следующих типов выражений:  
  
-   константное выражение;  
  
-   выражение в форме `new ValType()`, где `ValType` — это тип значения, например, [enum](../../../csharp/language-reference/keywords/enum.md) или [struct](../../../csharp/programming-guide/classes-and-structs/structs.md);  
  
-   выражение в форме [default(ValType)](../../../csharp/programming-guide/generics/default-keyword-in-generic-code.md), где `ValType` — это тип значения.  
  
 Необязательные параметры определяются в конце списка параметров после всех обязательных параметров. Если вызывающий объект предоставляет аргумент для любого из последующих необязательных параметров, он должен содержать аргументы для всех предыдущих необязательных параметров. Пробелы, разделенные запятыми, в списке аргументов не поддерживаются. Например, в следующем коде метод экземпляра `ExampleMethod` определяется одним обязательным и двумя необязательными параметрами.  
  
 [!code-cs[csProgGuideNamedAndOptional#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_2.cs)]  
  
 Следующий вызов `ExampleMethod` вызывает ошибку компилятора, поскольку аргумент предоставляется для третьего параметра, но не для второго.  
  
 `//anExample.ExampleMethod(3, ,4);`  
  
 Если вы знаете имя третьего параметра, можете использовать для выполнения задачи именованный аргумент.  
  
 `anExample.ExampleMethod(3, optionalint: 4);`  
  
 В IntelliSense необязательные параметры заключаются в квадратные скобки, как показано на следующем рисунке.  
  
 ![Быстрая справка IntelliSense для метода ExampleMethod.](../../../csharp/programming-guide/classes-and-structs/media/optional_parameters.png "Optional_Parameters")  
Необязательные параметры в ExampleMethod  
  
> [!NOTE]
>  Необязательные параметры также можно объявлять с помощью класса .NET <xref:System.Runtime.InteropServices.OptionalAttribute>. Для параметров `OptionalAttribute` значение по умолчанию не требуется.  
  
## <a name="example"></a>Пример  
 В следующем примере конструктор `ExampleClass` имеет один параметр, который является необязательным. У метода экземпляра `ExampleMethod` есть один обязательный параметр, `required`, и два необязательных параметра, `optionalstr` и `optionalint`. Код в `Main` демонстрирует различные способы, которые можно использовать для вызова конструктора и метода.  
  
 [!code-cs[csProgGuideNamedAndOptional#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_3.cs)]  
  
## <a name="com-interfaces"></a>Интерфейсы COM  
 Именованные и необязательные аргументы, а также поддержка динамических объектов и другие усовершенствования значительно улучшают взаимодействие с API COM, такими как API автоматизации Office.  
  
 Например, метод [AutoFormat](http://go.microsoft.com/fwlink/?LinkId=148201) в интерфейсе [диапазона](http://go.microsoft.com/fwlink/?LinkId=148196) Microsoft Office Excel имеет семь параметров и все они необязательные. Эти параметры показаны на следующем рисунке.  
  
 ![Быстрая справка IntelliSense для метода AutoFormat.](../../../csharp/programming-guide/classes-and-structs/media/autoformat_parameters.png "AutoFormat_Parameters")  
Параметры метода AutoFormat  
  
 В C# 3.0 и более ранних версиях аргумент необходимо указывать для каждого параметра, как показано в следующем примере.  
  
 [!code-cs[csProgGuideNamedAndOptional#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_4.cs)]  
  
 При этом вызов `AutoFormat` можно значительно упростить, используя именованные и необязательные аргументы, представленные в C# 4.0. Именованные и необязательные аргументы позволяют опускать аргументы для необязательных параметров, если значение параметра по умолчанию менять не нужно. В следующем вызове значение задается только для одного из семи параметров.  
  
 [!code-cs[csProgGuideNamedAndOptional#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_5.cs)]  
  
 Дополнительные сведения и примеры см. в разделах [Практическое руководство. Использование именованных и необязательных аргументов в программировании Office](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) и [Практическое руководство. Доступ к объектам взаимодействия Office с помощью функций языка Visual C#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).  
  
## <a name="overload-resolution"></a>Overload Resolution  
 Использование именованных и необязательных аргументов влияет на разрешение перегрузки описанным ниже образом.  
  
-   Метод, индексатор или конструктор является кандидатом на выполнение, если каждый из его параметров необязателен либо по имени или позиции соответствует одному и тому же аргументу в операторе вызова, и этот аргумент можно преобразовать в тип параметра.  
  
-   Если найдено более одного кандидата, правила разрешения перегрузки для предпочтительных преобразований применяются к аргументам, указанным явно. Опущенные аргументы для необязательных параметров игнорируются.  
  
-   Если два кандидата определяются как равно подходящие, предпочтение отдается кандидату без необязательных параметров, аргументы которых в вызове были опущены. Это — последовательность определения приоритетов в разрешении перегрузки для кандидатов с меньшим числом параметров.  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Использование именованных и необязательных аргументов в программировании приложений Office](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)   
 [Использование типа dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md)   
 [Использование конструкторов](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)   
 [Использование индексаторов](../../../csharp/programming-guide/indexers/using-indexers.md)

