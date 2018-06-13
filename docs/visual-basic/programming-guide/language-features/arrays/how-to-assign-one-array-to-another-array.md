---
title: Практическое руководство. Присвоение одного массива другому (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
ms.openlocfilehash: 63c7d187152fcb5ea84378c677aa687f334f63de
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647934"
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a><span data-ttu-id="6a5fc-102">Практическое руководство. Присвоение одного массива другому (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a5fc-102">How to: Assign One Array to Another Array (Visual Basic)</span></span>
<span data-ttu-id="6a5fc-103">Поскольку массивы — это объекты, их можно использовать в инструкциях присваивания, как и другие типы объектов.</span><span class="sxs-lookup"><span data-stu-id="6a5fc-103">Because arrays are objects, you can use them in assignment statements like other object types.</span></span> <span data-ttu-id="6a5fc-104">Переменная массива содержит указатель на данные, составляющие элементы массива и сведения о ранге и длине и назначения копирует только этот указатель.</span><span class="sxs-lookup"><span data-stu-id="6a5fc-104">An array variable holds a pointer to the data constituting the array elements and the rank and length information, and an assignment copies only this pointer.</span></span>  
  
### <a name="to-assign-one-array-to-another-array"></a><span data-ttu-id="6a5fc-105">Чтобы назначить один массив другого массива</span><span class="sxs-lookup"><span data-stu-id="6a5fc-105">To assign one array to another array</span></span>  
  
1.  <span data-ttu-id="6a5fc-106">Убедитесь, что два массива имеют одинаковый ранг (число измерений) и совместимый тип данных элементов.</span><span class="sxs-lookup"><span data-stu-id="6a5fc-106">Ensure that the two arrays have the same rank (number of dimensions) and compatible element data types.</span></span>  
  
2.  <span data-ttu-id="6a5fc-107">Используйте стандартный оператор присваивания для присваивания исходного массива в массив назначения.</span><span class="sxs-lookup"><span data-stu-id="6a5fc-107">Use a standard assignment statement to assign the source array to the destination array.</span></span> <span data-ttu-id="6a5fc-108">Не выполняйте либо имя массива в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="6a5fc-108">Do not follow either array name with parentheses.</span></span>  
  
    ```  
    Dim formArray() As System.Windows.Forms.Form  
    Dim controlArray() As System.Windows.Forms.Control  
    controlArray = formArray  
    ```  
  
 <span data-ttu-id="6a5fc-109">При назначении одного массива в другой, применяются следующие правила:</span><span class="sxs-lookup"><span data-stu-id="6a5fc-109">When you assign one array to another, the following rules apply:</span></span>  
  
-   <span data-ttu-id="6a5fc-110">**Равенство ранга.**</span><span class="sxs-lookup"><span data-stu-id="6a5fc-110">**Equal Ranks.**</span></span> <span data-ttu-id="6a5fc-111">Ранг (число измерений) массива назначения должен быть таким же, как и для исходного массива.</span><span class="sxs-lookup"><span data-stu-id="6a5fc-111">The rank (number of dimensions) of the destination array must be the same as that of the source array.</span></span>  
  
     <span data-ttu-id="6a5fc-112">Предоставляемые равны ранги двух массивов, размеры не обязательно должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="6a5fc-112">Provided the ranks of the two arrays are equal, the dimensions do not need to be equal.</span></span> <span data-ttu-id="6a5fc-113">Количество элементов в определенном измерении может изменяться во время назначения.</span><span class="sxs-lookup"><span data-stu-id="6a5fc-113">The number of elements in a given dimension can change during assignment.</span></span>  
  
-   <span data-ttu-id="6a5fc-114">**Типы элементов.**</span><span class="sxs-lookup"><span data-stu-id="6a5fc-114">**Element Types.**</span></span> <span data-ttu-id="6a5fc-115">Либо оба массива должны состоять *ссылочному типу* элементы или оба массива должны иметь *тип значения* элементов.</span><span class="sxs-lookup"><span data-stu-id="6a5fc-115">Either both arrays must have *reference type* elements or both arrays must have *value type* elements.</span></span> <span data-ttu-id="6a5fc-116">Дополнительные сведения см. в разделе [типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="6a5fc-116">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
    -   <span data-ttu-id="6a5fc-117">Если оба массива состоят из значений, их типы должны полностью совпадать.</span><span class="sxs-lookup"><span data-stu-id="6a5fc-117">If both arrays have value type elements, the element data types must be exactly the same.</span></span> <span data-ttu-id="6a5fc-118">Единственным исключением является, которые можно назначить массив `Enum` элементы в массив, базовый тип `Enum`.</span><span class="sxs-lookup"><span data-stu-id="6a5fc-118">The only exception to this is that you can assign an array of `Enum` elements to an array of the base type of that `Enum`.</span></span>  
  
    -   <span data-ttu-id="6a5fc-119">Если оба массива содержат элементы ссылочного типа, исходный тип элементов должен быть производным от типа конечного элемента.</span><span class="sxs-lookup"><span data-stu-id="6a5fc-119">If both arrays have reference type elements, the source element type must derive from the destination element type.</span></span> <span data-ttu-id="6a5fc-120">В случае два массива имеют такое же отношение наследования, что и их элементы.</span><span class="sxs-lookup"><span data-stu-id="6a5fc-120">When this is the case, the two arrays have the same inheritance relationship as their elements.</span></span> <span data-ttu-id="6a5fc-121">Это называется *Ковариация массивов*.</span><span class="sxs-lookup"><span data-stu-id="6a5fc-121">This is called *array covariance*.</span></span>  
  
 <span data-ttu-id="6a5fc-122">Компилятор выдает ошибку, если приведенные выше правила нарушены, например если типы данных несовместимы или ранги не равны.</span><span class="sxs-lookup"><span data-stu-id="6a5fc-122">The compiler reports an error if the above rules are violated, for example if the data types are not compatible or the ranks are unequal.</span></span> <span data-ttu-id="6a5fc-123">Можно добавить в код, чтобы убедиться в том, что массивы совместимы перед выполнением назначения обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="6a5fc-123">You can add error handling to your code to make sure that the arrays are compatible before attempting an assignment.</span></span> <span data-ttu-id="6a5fc-124">Можно также использовать [оператор TryCast](../../../../visual-basic/language-reference/operators/trycast-operator.md) ключевое слово, если вы хотите избежать создания исключения.</span><span class="sxs-lookup"><span data-stu-id="6a5fc-124">You can also use the [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md) keyword if you want to avoid throwing an exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a5fc-125">См. также</span><span class="sxs-lookup"><span data-stu-id="6a5fc-125">See Also</span></span>  
 [<span data-ttu-id="6a5fc-126">Массивы</span><span class="sxs-lookup"><span data-stu-id="6a5fc-126">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="6a5fc-127">Устранение неполадок, связанных с массивами</span><span class="sxs-lookup"><span data-stu-id="6a5fc-127">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)  
 [<span data-ttu-id="6a5fc-128">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="6a5fc-128">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [<span data-ttu-id="6a5fc-129">Преобразования массивов</span><span class="sxs-lookup"><span data-stu-id="6a5fc-129">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
