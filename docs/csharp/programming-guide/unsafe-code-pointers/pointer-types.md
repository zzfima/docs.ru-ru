---
title: "Типы указателей (Руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.assetid: 3319faf9-336d-4148-9af2-1da2579cdd1e
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fe7b926bdf9f662d25f2fe960b51fc8254b7aa3a
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2018
---
# <a name="pointer-types-c-programming-guide"></a>Типы указателей (Руководство по программированию на C#)
В небезопасном контексте тип может быть типом указателя, типом значения или ссылочным типом. Объявления типа указателя выполняется одним из следующих способов:  
  
```  
type* identifier;  
void* identifier; //allowed but not recommended  
```  
  
 Любой из указанных ниже типов может быть типом указателя:  
  
-   [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [char](../../../csharp/language-reference/keywords/char.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), [decimal](../../../csharp/language-reference/keywords/decimal.md) или [bool](../../../csharp/language-reference/keywords/bool.md).  
  
-   Любой тип [enum](../../../csharp/language-reference/keywords/enum.md).  
  
-   Любой тип указателя.  
  
-   Любой пользовательский тип структуры, содержащий поля только неуправляемых типов.  
  
 Типы указателей не наследуются от [объекта](../../../csharp/language-reference/keywords/object.md), а типы указателей не преобразуются в `object`. Кроме того, упаковка-преобразование и распаковка-преобразование не поддерживают указатели. Однако можно выполнять преобразования между различными типами указателей, а также между типами указателей и целочисленными типами.  
  
 При объявлении нескольких указателей в одном объявлении знак * указывается только с базовым типом; он не используется в качестве префикса для каждого имени указателя. Пример:  
  
```  
int* p1, p2, p3;   // Ok  
int *p1, *p2, *p3;   // Invalid in C#  
```  
  
 Указатель не может указывать на ссылку или на [структуру](../../../csharp/language-reference/keywords/struct.md), содержащую ссылки, поскольку ссылка на объект может быть подвергнута сбору мусора, даже если на нее указывает указатель. Сборщик мусора не отслеживает наличие указателей любых типов, указывающих на объекты.  
  
 Значением переменной-указателя типа `myType*` является адрес переменной типа `myType`. Ниже приведены примеры объявлений типов указателей.  
  
|Пример|Описание:|  
|-------------|-----------------|  
|`int* p`|`p` — указатель на целое число.|  
|`int** p`|`p` — указатель на указатель на целое число.|  
|`int*[] p`|`p` — одномерный массив указателей на целые числа.|  
|`char* p`|`p` — указатель на тип char.|  
|`void* p`|`p` — указатель на неизвестный тип.|  
  
 Оператор косвенного обращения указателя * можно использовать для доступа к содержимому, на которое указывает переменная-указатель. В качестве примера рассмотрим следующее объявление:  
  
```  
int* myVariable;  
```  
  
 Выражение `*myVariable` обозначает переменную `int`, находящуюся по адресу, содержащемуся в `myVariable`.  
  
 Разделы [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md) и [Преобразования указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-conversions.md) содержат несколько примеров.  В следующем примере показана необходимость наличия ключевого слова `unsafe` и оператора `fixed`, а также продемонстрирован способ инкрементирования внутреннего указателя.  Этот код можно вставить в функцию Main консольного приложения для его запуска. (Не забудьте включить небезопасный код в **Конструктор проектов**. Для этого в строке меню выберите **Проект**, **Свойства**, а затем на вкладке **Сборка** — **Разрешить небезопасный код**.)  
  
```  
// Normal pointer to an object.  
int[] a = new int[5] {10, 20, 30, 40, 50};  
// Must be in unsafe code to use interior pointers.  
unsafe  
{  
    // Must pin object on heap so that it doesn't move while using interior pointers.  
    fixed (int* p = &a[0])  
    {  
        // p is pinned as well as object, so create another pointer to show incrementing it.  
        int* p2 = p;  
        Console.WriteLine(*p2);  
        // Incrementing p2 bumps the pointer by four bytes due to its type ...  
        p2 += 1;  
        Console.WriteLine(*p2);  
        p2 += 1;  
        Console.WriteLine(*p2);  
        Console.WriteLine("--------");  
        Console.WriteLine(*p);  
        // Deferencing p and incrementing changes the value of a[0] ...  
        *p += 1;  
        Console.WriteLine(*p);  
        *p += 1;  
        Console.WriteLine(*p);  
    }  
}  
  
Console.WriteLine("--------");  
Console.WriteLine(a[0]);  
Console.ReadLine();  
  
// Output:  
//10  
//20  
//30  
//--------  
//10  
//11  
//12  
//--------  
//12  
```  
  
 Для указателя типа `void*` использовать оператор косвенного обращения нельзя. Однако можно использовать приведение для преобразования указателя типа void в любой другой тип и наоборот.  
  
 Указатель может иметь значение `null`. При применении оператора косвенного обращения к указателю со значением null результат зависит от конкретной реализации.  
  
 Обратите внимание, что при передаче указателей между методами может возникнуть неопределенное поведение. Рекомендуется использовать метод, возвращающий указатель в локальную переменную посредством параметра `in`, `out` или `ref` либо в виде результата функции. Если указатель был задан в фиксированном блоке, переменная, на которую он указывает, больше не может быть фиксированной.  
  
 В следующей таблице перечислены операторы, которые можно использовать для указателей в небезопасном контексте.  
  
|Оператор|Использовать|  
|-------------------------|---------|  
|*|Косвенное обращение к указателю.|  
|->|Доступ к члену структуры через указатель.|  
|[]|Индексирование указателя.|  
|`&`|Получение адреса переменной.|  
|++ и --|Увеличение и уменьшение указателей.|  
|+ и -|Арифметические действия с указателем.|  
|==, !=, \<, >, \<= и >=|Сравнение указателей.|  
|`stackalloc`|Выделение памяти в стеке.|  
|Оператор `fixed`|Временная фиксация переменной, чтобы можно было найти ее адрес.|  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [Преобразования указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-conversions.md)  
 [Выражения указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [Типы](../../../csharp/language-reference/keywords/types.md)  
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
 [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)  
 [Упаковка-преобразование и распаковка-преобразование](../../../csharp/programming-guide/types/boxing-and-unboxing.md)
