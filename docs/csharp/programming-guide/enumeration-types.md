---
title: "Типы перечислений (руководство по программированию на C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- enumerations [C#]
- enums [C#]
- C# Language, enums
- bit flags [C#]
ms.assetid: 64a9b731-9e3c-4336-8a09-018db2aa10b7
caps.latest.revision: 17
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8c23c17967474af0f91c0dda6d071073234736c6
ms.lasthandoff: 03/13/2017

---
# <a name="enumeration-types-c-programming-guide"></a>Типы перечислений (Руководство по программированию в C#)
Тип перечисления (называемый также перечислением) предоставляет эффективный способ определения набора именованных целочисленных констант, который можно назначить переменной. Например, предположим, что нужно определить переменную, значение которого должно представлять день недели. Имеется только семь имеющих смысл значений, которые может принимать переменная. Для определения этих значений можно использовать тип перечисления, который объявлен с помощью ключевого слова [enum](../../csharp/language-reference/keywords/enum.md).  
  
 [!code-cs[csProgGuideEnums#1](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_1.cs)]  
  
 По умолчанию базовым типом каждого элемента перечисления является [int](../../csharp/language-reference/keywords/int.md). Можно задать другой целочисленный тип, используя двоеточие, как показано в предыдущем примере. Полный список возможных типов см. в разделе [enum (справочник по C#)](../../csharp/language-reference/keywords/enum.md).  
  
 Чтобы проверить основные числовые значения путем приведения в базовый тип, как показано в следующем примере.  
  
```csharp  
Days today = Days.Monday;  
int dayNumber =(int)today;  
Console.WriteLine("{0} is day number #{1}.", today, dayNumber);  
  
Months thisMonth = Months.Dec;  
byte monthNumber = (byte)thisMonth;  
Console.WriteLine("{0} is month number #{1}.", thisMonth, monthNumber);  
  
// Output:  
// Monday is day number #1.  
// Dec is month number #11.  
```  
  
 Далее указаны преимущества использования enum вместо числового типа.  
  
-   Для клиентского кода ясно задается, какие значения допустимы для переменной.  
  
-   В [!INCLUDE[vsprvs](../../csharp/includes/vsprvs_md.md)] IntelliSense выводит список определенных значений.  
  
 Если не указать значения этих элементов в списке перечислителя, значения будут автоматически увеличиваться на 1. В предыдущем примере `Days.Sunday` имеет значение 0, `Days.Monday` имеет значение 1 и т. д. Когда создается новый объект `Days`, он будет иметь значение по умолчанию `Days.Sunday` (0), только ему явно не присвоить значение. При создании перечисления выберите наиболее логичное используемое по умолчанию значение и присвойте ему значение нуль. В результате этого все перечисления, если при их создании им явно не задать значение, будут иметь по умолчанию это значение.  
  
 Если переменная `meetingDay` имеет тип `Days`, ей можно (без явного приведения) присвоить только одно из значений, определенных в `Days`. И если день встречи изменяется, можно назначить новое значение из `Days` переменной `meetingDay`:  
  
 [!code-cs[csProgGuideEnums#4](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_2.cs)]  
  
> [!NOTE]
>  Переменной `meetingDay` можно присвоить любое произвольное целое значение. Например, эта строка кода не создает ошибку: `meetingDay = (Days) 42`. Но этого делать нельзя, поскольку неявно ожидается, что переменная перечисления принимает одно из значений, определяемых перечислением. Присвоение переменной типа перечисления произвольного значения связано с большим риском возникновения ошибок.  
  
 Элементам списка перечислителя типа перечисления можно присвоить любые значения, и можно также использовать вычисленные значения:  
  
 [!code-cs[csProgGuideEnums#3](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_3.cs)]  
  
## <a name="enumeration-types-as-bit-flags"></a>Типы перечислений как битовые флаги  
 Тип перечисления можно использовать для определения битовых флагов, благодаря чему экземпляр типа перечисления может хранить любую комбинацию значений, определенных в списке перечислителя. (Конечно, некоторые комбинации могут не иметь смысла или быть недопустимы в коде программы.)  
  
 Перечисление битовых флагов создается путем применения атрибута <xref:System.FlagsAttribute?displayProperty=fullName> и определением соответствующим образом значений так, чтобы с ними могли выполняться битовые операции `AND`, `OR`, `NOT` и `XOR`. В перечисление битовых флагов включите именованную константу с нулевым значением, что означает "флаги не установлены". Не придавайте флагу нулевое значение, если оно не означает "флаги не установлены".  
  
 В следующем примере определена другая версия перечисления `Days`, которая называется `Days2`. У `Days2` имеется атрибут `Flags`, и каждому значению присваивается следующая степень числа 2. Это позволяет создать переменную `Days2` со значением `Days2.Tuesday` и `Days2.Thursday`.  
  
 [!code-cs[csProgGuideEnums#2](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_4.cs)]  
  
 Чтобы установить флаг на перечислении, используйте побитовый оператор `OR`, как показано в следующем примере:  
  
 [!code-cs[csProgGuideEnums#6](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_5.cs)]  
  
 Чтобы определить, установлен ли конкретный флаг, используйте побитовый оператор `AND`, как показано в следующем примере:  
  
 [!code-cs[csProgGuideEnums#7](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_6.cs)]  
  
 Дополнительные сведения о том, что необходимо учитывать при определении типов перечислений при помощи атрибута <xref:System.FlagsAttribute?displayProperty=fullName>, см. в разделе <xref:System.Enum?displayProperty=fullName>.  
  
## <a name="using-the-systemenum-methods-to-discover-and-manipulate-enum-values"></a>Использование методов System.Enum для получения и обработки значений перечисления  
 Все перечисления являются экземплярами типа <xref:System.Enum?displayProperty=fullName>. Нельзя произвести новые классы от класса <xref:System.Enum?displayProperty=fullName>, но можно использовать его методы для получения данных экземпляра перечисления и для обработки этих данных.  
  
 [!code-cs[csProgGuideEnums#5](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_7.cs)]  
  
 Дополнительные сведения см. в разделе <xref:System.Enum?displayProperty=fullName>.  
  
 Можно также создать для перечисления новый метод, используя метод расширения. Дополнительные сведения см. в разделе [Практическое руководство. Создание нового метода для перечисления](../../csharp/programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).  
  
## <a name="featured-book-chapter"></a>Важная глава книги  
 [Дополнительные сведения о переменных](http://go.microsoft.com/fwlink/?LinkId=221230) в публикации [Введение в Visual C# 2010](http://go.microsoft.com/fwlink/?LinkId=221214)  
  
## <a name="see-also"></a>См. также  
 <xref:System.Enum?displayProperty=fullName>   
 [Руководство по программированию на C#](../../csharp/programming-guide/index.md)   
 [enum](../../csharp/language-reference/keywords/enum.md)
