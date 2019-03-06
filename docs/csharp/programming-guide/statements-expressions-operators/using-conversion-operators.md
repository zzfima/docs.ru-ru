---
title: Руководство по программированию в C#. Использование операторов преобразования
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
- implicit conversion operators [C#]
- explicit conversion operators [C#]
ms.assetid: caf36e89-c6c0-4b87-9f9e-85780a45c9a4
ms.openlocfilehash: 888339661ba1cb2e0b702f284d9f27b3217e74c1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973162"
---
# <a name="using-conversion-operators-c-programming-guide"></a>Использование операторов преобразования (Руководство по программированию в C#)
Вы можете использовать более удобные операторы преобразования `implicit` или операторы преобразования `explicit`, которые четко указывают на то, что выполняется преобразование типа. В этом разделе демонстрируется применение обоих типов операторов преобразования.  
  
> [!NOTE]
>  Дополнительные сведения о преобразованиях примитивных типов см. в практических руководствах по [ преобразованию строки в число](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), [ преобразованию массива байтов в значение типа int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [ преобразованию из шестнадцатеричных строк в числовые типы](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md) или <xref:System.Convert>.  
  
## <a name="example"></a>Пример  
 Это пример оператора явного преобразования. Этот оператор преобразует тип <xref:System.Byte> в тип значения с именем `Digit`. Поскольку не все байты можно преобразовать в цифры, это преобразование является явным. Это значит, что необходимо использовать приведение, как показано в методе `Main`.  
  
 [!code-csharp[csProgGuideStatements#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#11)]  
  
## <a name="example"></a>Пример  
 В этом примере демонстрируется оператор неявного преобразования. Для этого определяется оператор преобразования, который выполняет операцию, обратную показанной в предыдущем примере: преобразование из класса значения `Digit` в целочисленный тип <xref:System.Byte>. Поскольку любую цифру можно преобразовать в <xref:System.Byte>, явное преобразование в этом случае не требуется.  
  
 [!code-csharp[csProgGuideStatements#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#12)]  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Операторы преобразования](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)
- [is](../../../csharp/language-reference/keywords/is.md)
