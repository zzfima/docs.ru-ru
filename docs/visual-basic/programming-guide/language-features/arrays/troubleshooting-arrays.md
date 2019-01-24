---
title: Устранение неполадок, связанных с массивами (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
ms.openlocfilehash: 81817af230298528a766aa6494899538c35da7bf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54707626"
---
# <a name="troubleshooting-arrays-visual-basic"></a><span data-ttu-id="d97bc-102">Устранение неполадок, связанных с массивами (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d97bc-102">Troubleshooting Arrays (Visual Basic)</span></span>
<span data-ttu-id="d97bc-103">Этой странице перечислены некоторые распространенные проблемы, которые могут возникнуть при работе с массивами.</span><span class="sxs-lookup"><span data-stu-id="d97bc-103">This page lists some common problems that can occur when working with arrays.</span></span>  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a><span data-ttu-id="d97bc-104">Ошибки компиляции, объявления и инициализации массива</span><span class="sxs-lookup"><span data-stu-id="d97bc-104">Compilation Errors Declaring and Initializing an Array</span></span>  
 <span data-ttu-id="d97bc-105">Ошибки компиляции могут возникнуть с неправильным пониманием того, правила для объявления, создания и инициализации массивов.</span><span class="sxs-lookup"><span data-stu-id="d97bc-105">Compilation errors can arise from misunderstanding of the rules for declaring, creating, and initializing arrays.</span></span> <span data-ttu-id="d97bc-106">Ниже перечислены наиболее распространенные причины ошибок.</span><span class="sxs-lookup"><span data-stu-id="d97bc-106">The most common causes of errors are the following:</span></span>  
  
-   <span data-ttu-id="d97bc-107">Предоставление [оператор New](../../../../visual-basic/language-reference/operators/new-operator.md) предложение после указания размерностей в объявлении переменной массива.</span><span class="sxs-lookup"><span data-stu-id="d97bc-107">Supplying a [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) clause after specifying dimension lengths in the array variable declaration.</span></span> <span data-ttu-id="d97bc-108">Следующие строки кода показывают недопустимые объявления этого типа.</span><span class="sxs-lookup"><span data-stu-id="d97bc-108">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
-   <span data-ttu-id="d97bc-109">Указание длины по измерениям дольше, чем массива верхнего уровня массива массивов.</span><span class="sxs-lookup"><span data-stu-id="d97bc-109">Specifying dimension lengths for more than the top-level array of a jagged array.</span></span> <span data-ttu-id="d97bc-110">В следующей строке кода показано недопустимое объявление этого типа.</span><span class="sxs-lookup"><span data-stu-id="d97bc-110">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
-   <span data-ttu-id="d97bc-111">Пропуск `New` ключевое слово, при указании значения элементов.</span><span class="sxs-lookup"><span data-stu-id="d97bc-111">Omitting the `New` keyword when specifying the element values.</span></span> <span data-ttu-id="d97bc-112">В следующей строке кода показано недопустимое объявление этого типа.</span><span class="sxs-lookup"><span data-stu-id="d97bc-112">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
-   <span data-ttu-id="d97bc-113">Предоставление `New` предложение без фигурных скобок (`{}`).</span><span class="sxs-lookup"><span data-stu-id="d97bc-113">Supplying a `New` clause without braces (`{}`).</span></span> <span data-ttu-id="d97bc-114">Следующие строки кода показывают недопустимые объявления этого типа.</span><span class="sxs-lookup"><span data-stu-id="d97bc-114">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a><span data-ttu-id="d97bc-115">Доступ к массиву вне допустимых границ</span><span class="sxs-lookup"><span data-stu-id="d97bc-115">Accessing an Array Out of Bounds</span></span>  
 <span data-ttu-id="d97bc-116">Процесс инициализации массива назначает верхней и нижней границей каждого измерения.</span><span class="sxs-lookup"><span data-stu-id="d97bc-116">The process of initializing an array assigns an upper bound and a lower bound to each dimension.</span></span> <span data-ttu-id="d97bc-117">При каждом обращении к элемент массива необходимо указать допустимый индекс или индекс, для каждого измерения.</span><span class="sxs-lookup"><span data-stu-id="d97bc-117">Every access to an element of the array must specify a valid index, or subscript, for every dimension.</span></span> <span data-ttu-id="d97bc-118">Если любой индекс ниже его нижней границы или выше верхней границы, <xref:System.IndexOutOfRangeException> результаты исключения.</span><span class="sxs-lookup"><span data-stu-id="d97bc-118">If any index is below its lower bound or above its upper bound, an <xref:System.IndexOutOfRangeException> exception results.</span></span> <span data-ttu-id="d97bc-119">Компилятор не обнаруживает такую ошибку, поэтому она возникает во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d97bc-119">The compiler cannot detect such an error, so an error occurs at run time.</span></span>  
  
### <a name="determining-bounds"></a><span data-ttu-id="d97bc-120">Определение границ</span><span class="sxs-lookup"><span data-stu-id="d97bc-120">Determining Bounds</span></span>  
 <span data-ttu-id="d97bc-121">Если другой компонент передает массив в коде, например как аргумент процедуры, вы не знаете размер массива или длина его измерений.</span><span class="sxs-lookup"><span data-stu-id="d97bc-121">If another component passes an array to your code, for example as a procedure argument, you do not know the size of that array or the lengths of its dimensions.</span></span> <span data-ttu-id="d97bc-122">Всегда необходимо определить верхнюю границу для каждого измерения массива, прежде чем пытаться получить доступ к какие-либо элементы.</span><span class="sxs-lookup"><span data-stu-id="d97bc-122">You should always determine the upper bound for every dimension of an array before you attempt to access any elements.</span></span> <span data-ttu-id="d97bc-123">Если массив был создан с помощью некоторых средств, отличных от Visual Basic `New` предложение, нижняя граница может быть что-то отличное от 0, и лучше всего определить, что нижняя граница.</span><span class="sxs-lookup"><span data-stu-id="d97bc-123">If the array has been created by some means other than a Visual Basic `New` clause, the lower bound might be something other than 0, and it is safest to determine that lower bound as well.</span></span>  
  
### <a name="specifying-the-dimension"></a><span data-ttu-id="d97bc-124">Указание измерения</span><span class="sxs-lookup"><span data-stu-id="d97bc-124">Specifying the Dimension</span></span>  
 <span data-ttu-id="d97bc-125">При определении границ многомерного массива, будьте внимательны, как указать измерения.</span><span class="sxs-lookup"><span data-stu-id="d97bc-125">When determining the bounds of a multidimensional array, take care how you specify the dimension.</span></span> <span data-ttu-id="d97bc-126">`dimension` Параметры <xref:System.Array.GetLowerBound%2A> и <xref:System.Array.GetUpperBound%2A> методов начинаются с нуля, при `Rank` параметры Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> и <xref:Microsoft.VisualBasic.Information.UBound%2A> функции начинаются с 1.</span><span class="sxs-lookup"><span data-stu-id="d97bc-126">The `dimension` parameters of the <xref:System.Array.GetLowerBound%2A> and <xref:System.Array.GetUpperBound%2A> methods are 0-based, while the `Rank` parameters of the Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> and <xref:Microsoft.VisualBasic.Information.UBound%2A> functions are 1-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d97bc-127">См. также</span><span class="sxs-lookup"><span data-stu-id="d97bc-127">See also</span></span>
- [<span data-ttu-id="d97bc-128">Массивы</span><span class="sxs-lookup"><span data-stu-id="d97bc-128">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="d97bc-129">Практическое руководство. Инициализация переменной массива в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d97bc-129">How to: Initialize an Array Variable in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
