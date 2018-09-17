---
title: Использование операторов преобразования (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
- implicit conversion operators [C#]
- explicit conversion operators [C#]
ms.assetid: caf36e89-c6c0-4b87-9f9e-85780a45c9a4
ms.openlocfilehash: 17a722f7160ae9cd03caa2dff9c4436fcf0f9d9e
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45593703"
---
# <a name="using-conversion-operators-c-programming-guide"></a>Использование операторов преобразования (Руководство по программированию в C#)
Вы можете использовать более удобные операторы преобразования `implicit` или операторы преобразования `explicit`, которые четко указывают на то, что выполняется преобразование типа. В этом разделе демонстрируется применение обоих типов операторов преобразования.  
  
> [!NOTE]
>  Дополнительные сведения о простых преобразованиях типов см. в разделах [Практическое руководство. Преобразование строки в число](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), [Практическое руководство. Преобразование массива байтов в значение типа int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [Практическое руководство. Преобразование из шестнадцатеричных строк в числовые типы](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md) и <xref:System.Convert>.  
  
## <a name="example"></a>Пример  
 Это пример оператора явного преобразования. Этот оператор преобразует тип <xref:System.Byte> в тип значения с именем `Digit`. Поскольку не все байты можно преобразовать в цифры, это преобразование является явным. Это значит, что необходимо использовать приведение, как показано в методе `Main`.  
  
 [!code-csharp[csProgGuideStatements#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-conversion-operators_1.cs)]  
  
## <a name="example"></a>Пример  
 В этом примере демонстрируется оператор неявного преобразования. Для этого определяется оператор преобразования, который выполняет операцию, обратную показанной в предыдущем примере: преобразование из класса значения `Digit` в целочисленный тип <xref:System.Byte>. Поскольку любую цифру можно преобразовать в <xref:System.Byte>, явное преобразование в этом случае не требуется.  
  
 [!code-csharp[csProgGuideStatements#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-conversion-operators_2.cs)]  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Операторы преобразования](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)  
- [is](../../../csharp/language-reference/keywords/is.md)
