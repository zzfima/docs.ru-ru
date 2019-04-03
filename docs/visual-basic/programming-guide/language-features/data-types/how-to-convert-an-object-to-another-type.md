---
title: Практическое руководство. Преобразование объекта к другому типу в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: 1e515c0f4ce8e787754c61a9b53d247fa93c49f2
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814384"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a><span data-ttu-id="a37f3-102">Практическое руководство. Преобразование объекта к другому типу в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a37f3-102">How to: Convert an Object to Another Type in Visual Basic</span></span>
<span data-ttu-id="a37f3-103">Преобразования `Object` переменных в другой тип данных с помощью ключевого слова преобразования, например [функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md).</span><span class="sxs-lookup"><span data-stu-id="a37f3-103">You convert an `Object` variable to another data type by using a conversion keyword such as [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a37f3-104">Пример</span><span class="sxs-lookup"><span data-stu-id="a37f3-104">Example</span></span>  
 <span data-ttu-id="a37f3-105">В следующем примере выполняется преобразование `Object` переменной `Integer` и `String`.</span><span class="sxs-lookup"><span data-stu-id="a37f3-105">The following example converts an `Object` variable to an `Integer` and a `String`.</span></span>  
  
```  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 <span data-ttu-id="a37f3-106">Если вы знаете, что содержимое `Object` переменной типа данных, лучше преобразовать в этот тип данных переменной.</span><span class="sxs-lookup"><span data-stu-id="a37f3-106">If you know that the contents of an `Object` variable are of a particular data type, it is better to convert the variable to that data type.</span></span> <span data-ttu-id="a37f3-107">Если вы продолжите использовать `Object` переменной, то это вызовет либо *упаковки-преобразования* и *распаковки* (для типа значения) или *позднее связывание* (для ссылочного типа).</span><span class="sxs-lookup"><span data-stu-id="a37f3-107">If you continue to use the `Object` variable, you incur either *boxing* and *unboxing* (for a value type) or *late binding* (for a reference type).</span></span> <span data-ttu-id="a37f3-108">Эти операции принимают дополнительное время выполнения и снижают производительность.</span><span class="sxs-lookup"><span data-stu-id="a37f3-108">These operations all take extra execution time and make your performance slower.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a37f3-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="a37f3-109">Compiling the Code</span></span>  
 <span data-ttu-id="a37f3-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="a37f3-110">This example requires:</span></span>  
  
-   <span data-ttu-id="a37f3-111">ссылка на пространство имен <xref:System?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a37f3-111">A reference to the <xref:System?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a37f3-112">См. также</span><span class="sxs-lookup"><span data-stu-id="a37f3-112">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="a37f3-113">Преобразование типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a37f3-113">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="a37f3-114">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="a37f3-114">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="a37f3-115">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="a37f3-115">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="a37f3-116">Преобразования значений между строковыми и другими типами</span><span class="sxs-lookup"><span data-stu-id="a37f3-116">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="a37f3-117">Преобразования массивов</span><span class="sxs-lookup"><span data-stu-id="a37f3-117">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [<span data-ttu-id="a37f3-118">Структуры</span><span class="sxs-lookup"><span data-stu-id="a37f3-118">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="a37f3-119">Типы данных</span><span class="sxs-lookup"><span data-stu-id="a37f3-119">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="a37f3-120">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="a37f3-120">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
