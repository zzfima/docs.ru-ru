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
# <a name="using-conversion-operators-c-programming-guide"></a><span data-ttu-id="880ef-102">Использование операторов преобразования (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="880ef-102">Using Conversion Operators (C# Programming Guide)</span></span>
<span data-ttu-id="880ef-103">Вы можете использовать более удобные операторы преобразования `implicit` или операторы преобразования `explicit`, которые четко указывают на то, что выполняется преобразование типа.</span><span class="sxs-lookup"><span data-stu-id="880ef-103">You can use `implicit` conversion operators, which are easier to use, or `explicit` conversion operators, which clearly indicate to anyone reading the code that you're converting a type.</span></span> <span data-ttu-id="880ef-104">В этом разделе демонстрируется применение обоих типов операторов преобразования.</span><span class="sxs-lookup"><span data-stu-id="880ef-104">This topic demonstrates both types of conversion operator.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="880ef-105">Дополнительные сведения о преобразованиях примитивных типов см. в практических руководствах по [ преобразованию строки в число](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), [ преобразованию массива байтов в значение типа int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [ преобразованию из шестнадцатеричных строк в числовые типы](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md) или <xref:System.Convert>.</span><span class="sxs-lookup"><span data-stu-id="880ef-105">For information about simple type conversions, see [How to: Convert a String to a Number](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), [How to: Convert a byte Array to an int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [How to: Convert Between Hexadecimal Strings and Numeric Types](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md), or <xref:System.Convert>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="880ef-106">Пример</span><span class="sxs-lookup"><span data-stu-id="880ef-106">Example</span></span>  
 <span data-ttu-id="880ef-107">Это пример оператора явного преобразования.</span><span class="sxs-lookup"><span data-stu-id="880ef-107">This is an example of an explicit conversion operator.</span></span> <span data-ttu-id="880ef-108">Этот оператор преобразует тип <xref:System.Byte> в тип значения с именем `Digit`.</span><span class="sxs-lookup"><span data-stu-id="880ef-108">This operator converts from the type <xref:System.Byte> to a value type called `Digit`.</span></span> <span data-ttu-id="880ef-109">Поскольку не все байты можно преобразовать в цифры, это преобразование является явным. Это значит, что необходимо использовать приведение, как показано в методе `Main`.</span><span class="sxs-lookup"><span data-stu-id="880ef-109">Because not all bytes can be converted to a digit, the conversion is explicit, meaning that a cast must be used, as shown in the `Main` method.</span></span>  
  
 [!code-csharp[csProgGuideStatements#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#11)]  
  
## <a name="example"></a><span data-ttu-id="880ef-110">Пример</span><span class="sxs-lookup"><span data-stu-id="880ef-110">Example</span></span>  
 <span data-ttu-id="880ef-111">В этом примере демонстрируется оператор неявного преобразования. Для этого определяется оператор преобразования, который выполняет операцию, обратную показанной в предыдущем примере: преобразование из класса значения `Digit` в целочисленный тип <xref:System.Byte>.</span><span class="sxs-lookup"><span data-stu-id="880ef-111">This example demonstrates an implicit conversion operator by defining a conversion operator that undoes what the previous example did: it converts from a value class called `Digit` to the integral <xref:System.Byte> type.</span></span> <span data-ttu-id="880ef-112">Поскольку любую цифру можно преобразовать в <xref:System.Byte>, явное преобразование в этом случае не требуется.</span><span class="sxs-lookup"><span data-stu-id="880ef-112">Because any digit can be converted to a <xref:System.Byte>, there's no need to force users to be explicit about the conversion.</span></span>  
  
 [!code-csharp[csProgGuideStatements#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#12)]  
  
## <a name="see-also"></a><span data-ttu-id="880ef-113">См. также</span><span class="sxs-lookup"><span data-stu-id="880ef-113">See also</span></span>

- [<span data-ttu-id="880ef-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="880ef-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="880ef-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="880ef-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="880ef-116">Операторы преобразования</span><span class="sxs-lookup"><span data-stu-id="880ef-116">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)
- [<span data-ttu-id="880ef-117">is</span><span class="sxs-lookup"><span data-stu-id="880ef-117">is</span></span>](../../../csharp/language-reference/keywords/is.md)
