---
title: Практическое руководство. Преобразование объекта к другому типу в Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 053c93e7cf842138f5b9299cd2fcfa56342dd40b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a><span data-ttu-id="4f7cc-102">Практическое руководство. Преобразование объекта к другому типу в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4f7cc-102">How to: Convert an Object to Another Type in Visual Basic</span></span>
<span data-ttu-id="4f7cc-103">Преобразовать `Object` переменных в другой тип данных с помощью ключевого слова преобразования, например [функция CType](../../../../visual-basic/language-reference/functions/ctype-function.md).</span><span class="sxs-lookup"><span data-stu-id="4f7cc-103">You convert an `Object` variable to another data type by using a conversion keyword such as [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f7cc-104">Пример</span><span class="sxs-lookup"><span data-stu-id="4f7cc-104">Example</span></span>  
 <span data-ttu-id="4f7cc-105">В следующем примере выполняется преобразование `Object` переменной `Integer` и `String`.</span><span class="sxs-lookup"><span data-stu-id="4f7cc-105">The following example converts an `Object` variable to an `Integer` and a `String`.</span></span>  
  
```  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 <span data-ttu-id="4f7cc-106">Если известно, что содержимое `Object` переменной определенного типа данных, лучше преобразовать переменную в этот тип данных.</span><span class="sxs-lookup"><span data-stu-id="4f7cc-106">If you know that the contents of an `Object` variable are of a particular data type, it is better to convert the variable to that data type.</span></span> <span data-ttu-id="4f7cc-107">Если вы продолжаете использовать `Object` переменной, то это вызовет либо *упаковка-преобразование* и *распаковки* (для типа значения) или *позднего связывания* (для ссылочного типа).</span><span class="sxs-lookup"><span data-stu-id="4f7cc-107">If you continue to use the `Object` variable, you incur either *boxing* and *unboxing* (for a value type) or *late binding* (for a reference type).</span></span> <span data-ttu-id="4f7cc-108">Эти операции принимают большего времени для выполнения и снижают производительность.</span><span class="sxs-lookup"><span data-stu-id="4f7cc-108">These operations all take extra execution time and make your performance slower.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4f7cc-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="4f7cc-109">Compiling the Code</span></span>  
 <span data-ttu-id="4f7cc-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="4f7cc-110">This example requires:</span></span>  
  
-   <span data-ttu-id="4f7cc-111">ссылка на пространство имен <xref:System?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4f7cc-111">A reference to the <xref:System?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f7cc-112">См. также</span><span class="sxs-lookup"><span data-stu-id="4f7cc-112">See Also</span></span>  
 <xref:System.Object>  
 [<span data-ttu-id="4f7cc-113">Преобразования типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4f7cc-113">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="4f7cc-114">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="4f7cc-114">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="4f7cc-115">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="4f7cc-115">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="4f7cc-116">Преобразования значений между строковыми и другими типами</span><span class="sxs-lookup"><span data-stu-id="4f7cc-116">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [<span data-ttu-id="4f7cc-117">Преобразования массивов</span><span class="sxs-lookup"><span data-stu-id="4f7cc-117">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 [<span data-ttu-id="4f7cc-118">Структуры</span><span class="sxs-lookup"><span data-stu-id="4f7cc-118">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="4f7cc-119">Типы данных</span><span class="sxs-lookup"><span data-stu-id="4f7cc-119">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="4f7cc-120">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="4f7cc-120">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
