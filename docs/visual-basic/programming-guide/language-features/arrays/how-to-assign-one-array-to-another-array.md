---
title: Практическое руководство. Присвоение одного массива другому (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
ms.openlocfilehash: a39888f19e5033a5c6622313fb7451d6463b2f7c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64858881"
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a><span data-ttu-id="a6e00-102">Практическое руководство. Присвоение одного массива другому (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6e00-102">How to: Assign One Array to Another Array (Visual Basic)</span></span>

<span data-ttu-id="a6e00-103">Поскольку массивы являются объектами, их можно использовать в инструкциях присваивания, как и другие типы объектов.</span><span class="sxs-lookup"><span data-stu-id="a6e00-103">Because arrays are objects, you can use them in assignment statements like other object types.</span></span> <span data-ttu-id="a6e00-104">Переменную массива содержит указатель на данные, содержащие элементы массива и ранг и длина информацию и присваивания копирует только этот указатель.</span><span class="sxs-lookup"><span data-stu-id="a6e00-104">An array variable holds a pointer to the data constituting the array elements and the rank and length information, and an assignment copies only this pointer.</span></span>

### <a name="to-assign-one-array-to-another-array"></a><span data-ttu-id="a6e00-105">Чтобы присвоение одного массива другому</span><span class="sxs-lookup"><span data-stu-id="a6e00-105">To assign one array to another array</span></span>

1. <span data-ttu-id="a6e00-106">Убедитесь, что два массива имеют одинаковый ранг (число измерений) и совместимый тип данных элементов.</span><span class="sxs-lookup"><span data-stu-id="a6e00-106">Ensure that the two arrays have the same rank (number of dimensions) and compatible element data types.</span></span>

2. <span data-ttu-id="a6e00-107">Используйте стандартный оператор присваивания для назначения исходного массива в массив назначения.</span><span class="sxs-lookup"><span data-stu-id="a6e00-107">Use a standard assignment statement to assign the source array to the destination array.</span></span> <span data-ttu-id="a6e00-108">Не выполняйте либо имя массива в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="a6e00-108">Do not follow either array name with parentheses.</span></span>

    ```vb
    Dim formArray() As System.Windows.Forms.Form
    Dim controlArray() As System.Windows.Forms.Control
    controlArray = formArray
    ```

<span data-ttu-id="a6e00-109">Когда вы назначаете один массив в другой, применяются следующие правила:</span><span class="sxs-lookup"><span data-stu-id="a6e00-109">When you assign one array to another, the following rules apply:</span></span>

- <span data-ttu-id="a6e00-110">**Равенство ранга.**</span><span class="sxs-lookup"><span data-stu-id="a6e00-110">**Equal Ranks.**</span></span> <span data-ttu-id="a6e00-111">Ранг (число измерений) массива назначения должен быть таким же, как и для исходного массива.</span><span class="sxs-lookup"><span data-stu-id="a6e00-111">The rank (number of dimensions) of the destination array must be the same as that of the source array.</span></span>

  <span data-ttu-id="a6e00-112">Предоставляемые ранги два массива равны, размеры не обязательно должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="a6e00-112">Provided the ranks of the two arrays are equal, the dimensions do not need to be equal.</span></span> <span data-ttu-id="a6e00-113">Число элементов в определенном измерении можно изменить во время назначения.</span><span class="sxs-lookup"><span data-stu-id="a6e00-113">The number of elements in a given dimension can change during assignment.</span></span>

- <span data-ttu-id="a6e00-114">**Типы элементов.**</span><span class="sxs-lookup"><span data-stu-id="a6e00-114">**Element Types.**</span></span> <span data-ttu-id="a6e00-115">Либо обоих массивов должны быть *ссылочный тип* элементов или оба массива должны иметь *тип значения* элементов.</span><span class="sxs-lookup"><span data-stu-id="a6e00-115">Either both arrays must have *reference type* elements or both arrays must have *value type* elements.</span></span> <span data-ttu-id="a6e00-116">Для получения дополнительной информации см. [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="a6e00-116">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>

  - <span data-ttu-id="a6e00-117">Если оба массива состоят из значений, их типы должны полностью совпадать.</span><span class="sxs-lookup"><span data-stu-id="a6e00-117">If both arrays have value type elements, the element data types must be exactly the same.</span></span> <span data-ttu-id="a6e00-118">Единственным исключением из этого является, можно назначить массив `Enum` элементы в массив, базовый тип `Enum`.</span><span class="sxs-lookup"><span data-stu-id="a6e00-118">The only exception to this is that you can assign an array of `Enum` elements to an array of the base type of that `Enum`.</span></span>

  - <span data-ttu-id="a6e00-119">Если оба массива имеют ссылочный тип элементов, тип элемента источника должен быть производным от типа элемента назначения.</span><span class="sxs-lookup"><span data-stu-id="a6e00-119">If both arrays have reference type elements, the source element type must derive from the destination element type.</span></span> <span data-ttu-id="a6e00-120">Это делается с помощью двух массивов после той же связи наследования, как их элементов.</span><span class="sxs-lookup"><span data-stu-id="a6e00-120">When this is the case, the two arrays have the same inheritance relationship as their elements.</span></span> <span data-ttu-id="a6e00-121">Это называется *ковариацией*.</span><span class="sxs-lookup"><span data-stu-id="a6e00-121">This is called *array covariance*.</span></span>

<span data-ttu-id="a6e00-122">Компилятор выдает ошибку, если приведенные выше правила нарушены, например если типы данных несовместимы или ранги не равны.</span><span class="sxs-lookup"><span data-stu-id="a6e00-122">The compiler reports an error if the above rules are violated, for example if the data types are not compatible or the ranks are unequal.</span></span> <span data-ttu-id="a6e00-123">Вы можете добавить в код, чтобы убедиться в том, что массивы совместимы, прежде чем назначение обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="a6e00-123">You can add error handling to your code to make sure that the arrays are compatible before attempting an assignment.</span></span> <span data-ttu-id="a6e00-124">Можно также использовать [оператор TryCast](../../../../visual-basic/language-reference/operators/trycast-operator.md) ключевое слово, если вы хотите избежать возникновения исключения.</span><span class="sxs-lookup"><span data-stu-id="a6e00-124">You can also use the [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md) keyword if you want to avoid throwing an exception.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6e00-125">См. также</span><span class="sxs-lookup"><span data-stu-id="a6e00-125">See also</span></span>

- [<span data-ttu-id="a6e00-126">Массивы</span><span class="sxs-lookup"><span data-stu-id="a6e00-126">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="a6e00-127">Устранение неполадок, связанных с массивами</span><span class="sxs-lookup"><span data-stu-id="a6e00-127">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
- [<span data-ttu-id="a6e00-128">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="a6e00-128">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="a6e00-129">Преобразования массивов</span><span class="sxs-lookup"><span data-stu-id="a6e00-129">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
