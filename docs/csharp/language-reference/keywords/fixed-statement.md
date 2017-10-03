---
title: "Оператор fixed (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- fixed_CSharpKeyword
- fixed
dev_langs:
- CSharp
helpviewer_keywords:
- fixed keyword [C#]
ms.assetid: 7ea6db08-ad49-4a7a-b934-d8c4acad1c3a
caps.latest.revision: 24
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
ms.openlocfilehash: 4e1f810f6e6cfaef3a65c7391f074b414ef18b5a
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="fixed-statement-c-reference"></a>Оператор fixed (Справочник по C#)
Оператор `fixed` не позволяет сборщику мусора переносить перемещаемую переменную. Оператор `fixed` допускается только в [небезопасном](../../../csharp/language-reference/keywords/unsafe.md) контексте. `Fixed` также можно использовать для создания [буферов фиксированного размера](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).  
  
 Оператор `fixed` задает указатель на управляемую переменную и "закрепляет" эту переменную во время выполнения оператора. Без `fixed` указатели на перемещаемые управляемые переменные были бы мало полезны, так как при сборке мусора переменные переносились бы непредсказуемым образом. Компилятор C# позволяет присвоить указатель только управляемой переменной в операторе `fixed`.  
  
 [!code-cs[csrefKeywordsFixedLock#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_1.cs)]  
  
 Вы можете инициализировать указатель, используя массив, строку, буфер фиксированного размера или адрес переменной. В приведенном ниже примере демонстрируется использование переменных адресов, массивов и строк. Дополнительные сведения о буферах фиксированного размера см. в разделе [Буферы фиксированного размера](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).  
  
 [!code-cs[csrefKeywordsFixedLock#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_2.cs)]  
  
 Можно инициализировать несколько указателей одного типа.  
  
```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}  
```
  
 Чтобы инициализировать указатели разных типов, просто вложите операторы `fixed`, как показано в приведенном ниже примере.  
  
 [!code-cs[csrefKeywordsFixedLock#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_3.cs)]  
  
 После выполнения кода в операторе закрепление всех переменных отменяется, и они могут пройти сборку мусора. Таким образом, не следует использовать указатели на эти переменные за пределами оператора `fixed`.  
  
> [!NOTE]
>  Указатели, инициализированные в фиксированных операторах, изменять нельзя.  
  
 В небезопасном режиме вы можете выделить память в стеке, где сборка мусора не производится и, соответственно, закрепление не требуется. Дополнительные сведения см. в разделе [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md).  
  
## <a name="example"></a>Пример  
 [!code-cs[csrefKeywordsFixedLock#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_4.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)   
 [Буферы фиксированного размера](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)

