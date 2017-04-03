---
title: "sizeof (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
dev_langs:
- CSharp
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
caps.latest.revision: 20
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
ms.openlocfilehash: 7a1944caceaba3ffb8d83a8f67e5ef2975bf9644
ms.lasthandoff: 03/13/2017

---
# <a name="sizeof-c-reference"></a>sizeof (Справочник по C#)
Позволяет получить размер в байтах для неуправляемого типа. К неуправляемым типам относятся встроенные типы, перечисленные в представленной ниже таблице, а также следующие типы:  
  
-   типы перечисления;  
  
-   типы указателей;  
  
-   определяемые пользователем структуры, не содержащие полей или свойств, принадлежащих ссылочным типам.  
  
 В приведенном ниже примере показано, как извлекать размер переменной типа `int`.  
  
```csharp  
// Constant value 4:  
int intSize = sizeof(int);   
```  
  
## <a name="remarks"></a>Примечания  
 Начиная с версии 2.0 языка C# при применении оператора `sizeof` к встроенным типам больше не требуется использовать [небезопасный](../../../csharp/language-reference/keywords/unsafe.md) режим.  
  
 Оператор `sizeof` перегрузить нельзя. Возвращаемые оператором `sizeof` значения принадлежат типу `int`. В приведенной ниже таблице показаны константы, которые заменяются выражениями `sizeof`, содержащими некоторые операнды встроенных типов.  
  
|Выражение|Константа|  
|----------------|--------------------|  
|`sizeof(sbyte)`|1|  
|`sizeof(byte)`|1|  
|`sizeof(short)`|2|  
|`sizeof(ushort)`|2|  
|`sizeof(int)`|4|  
|`sizeof(uint)`|4|  
|`sizeof(long)`|8|  
|`sizeof(ulong)`|8|  
|`sizeof(char)`|2 (Юникод)|  
|`sizeof(float)`|4|  
|`sizeof(double)`|8|  
|`sizeof(decimal)`|16|  
|`sizeof(bool)`|1|  
  
 Для всех остальных типов, в том числе для структур, оператор `sizeof` можно использовать только в блоках небезопасного кода. Можно также использовать метод <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName>, однако возвращаемое им значение не всегда совпадает со значением метода `sizeof`. Метод <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName> возвращает размер после маршалинга типа, тогда как оператор `sizeof` возвращает размер сразу после выделения памяти средой CLR, включая заполнения.  
  
## <a name="example"></a>Пример  
 [!code-cs[csrefKeywordsOperator#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/sizeof_1.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Ключевые слова операторов](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [enum](../../../csharp/language-reference/keywords/enum.md)   
 [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [Структуры](../../../csharp/programming-guide/classes-and-structs/structs.md)   
 [Константы](../../../csharp/programming-guide/classes-and-structs/constants.md)
