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
# <a name="using-conversion-operators-c-programming-guide"></a><span data-ttu-id="dda22-102">Использование операторов преобразования (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="dda22-102">Using Conversion Operators (C# Programming Guide)</span></span>
<span data-ttu-id="dda22-103">Вы можете использовать более удобные операторы преобразования `implicit` или операторы преобразования `explicit`, которые четко указывают на то, что выполняется преобразование типа.</span><span class="sxs-lookup"><span data-stu-id="dda22-103">You can use `implicit` conversion operators, which are easier to use, or `explicit` conversion operators, which clearly indicate to anyone reading the code that you're converting a type.</span></span> <span data-ttu-id="dda22-104">В этом разделе демонстрируется применение обоих типов операторов преобразования.</span><span class="sxs-lookup"><span data-stu-id="dda22-104">This topic demonstrates both types of conversion operator.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dda22-105">Дополнительные сведения о простых преобразованиях типов см. в разделах [Практическое руководство. Преобразование строки в число](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), [Практическое руководство. Преобразование массива байтов в значение типа int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [Практическое руководство. Преобразование из шестнадцатеричных строк в числовые типы](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md) и <xref:System.Convert>.</span><span class="sxs-lookup"><span data-stu-id="dda22-105">For information about simple type conversions, see [How to: Convert a String to a Number](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), [How to: Convert a byte Array to an int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [How to: Convert Between Hexadecimal Strings and Numeric Types](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md), or <xref:System.Convert>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dda22-106">Пример</span><span class="sxs-lookup"><span data-stu-id="dda22-106">Example</span></span>  
 <span data-ttu-id="dda22-107">Это пример оператора явного преобразования.</span><span class="sxs-lookup"><span data-stu-id="dda22-107">This is an example of an explicit conversion operator.</span></span> <span data-ttu-id="dda22-108">Этот оператор преобразует тип <xref:System.Byte> в тип значения с именем `Digit`.</span><span class="sxs-lookup"><span data-stu-id="dda22-108">This operator converts from the type <xref:System.Byte> to a value type called `Digit`.</span></span> <span data-ttu-id="dda22-109">Поскольку не все байты можно преобразовать в цифры, это преобразование является явным. Это значит, что необходимо использовать приведение, как показано в методе `Main`.</span><span class="sxs-lookup"><span data-stu-id="dda22-109">Because not all bytes can be converted to a digit, the conversion is explicit, meaning that a cast must be used, as shown in the `Main` method.</span></span>  
  
 [!code-csharp[csProgGuideStatements#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-conversion-operators_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="dda22-110">Пример</span><span class="sxs-lookup"><span data-stu-id="dda22-110">Example</span></span>  
 <span data-ttu-id="dda22-111">В этом примере демонстрируется оператор неявного преобразования. Для этого определяется оператор преобразования, который выполняет операцию, обратную показанной в предыдущем примере: преобразование из класса значения `Digit` в целочисленный тип <xref:System.Byte>.</span><span class="sxs-lookup"><span data-stu-id="dda22-111">This example demonstrates an implicit conversion operator by defining a conversion operator that undoes what the previous example did: it converts from a value class called `Digit` to the integral <xref:System.Byte> type.</span></span> <span data-ttu-id="dda22-112">Поскольку любую цифру можно преобразовать в <xref:System.Byte>, явное преобразование в этом случае не требуется.</span><span class="sxs-lookup"><span data-stu-id="dda22-112">Because any digit can be converted to a <xref:System.Byte>, there's no need to force users to be explicit about the conversion.</span></span>  
  
 [!code-csharp[csProgGuideStatements#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-conversion-operators_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="dda22-113">См. также</span><span class="sxs-lookup"><span data-stu-id="dda22-113">See Also</span></span>

- [<span data-ttu-id="dda22-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="dda22-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="dda22-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="dda22-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="dda22-116">Операторы преобразования</span><span class="sxs-lookup"><span data-stu-id="dda22-116">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)  
- [<span data-ttu-id="dda22-117">is</span><span class="sxs-lookup"><span data-stu-id="dda22-117">is</span></span>](../../../csharp/language-reference/keywords/is.md)
