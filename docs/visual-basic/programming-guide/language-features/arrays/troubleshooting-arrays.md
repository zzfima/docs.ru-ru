---
title: "Устранение неполадок с массивами (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 571731ae7066ba7ec52d4a2413b4d948f3f35bfe
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="troubleshooting-arrays-visual-basic"></a><span data-ttu-id="57dfa-102">Устранение неполадок, связанных с массивами (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57dfa-102">Troubleshooting Arrays (Visual Basic)</span></span>
<span data-ttu-id="57dfa-103">На этой странице перечислены некоторые общие проблемы, которые могут возникнуть при работе с массивами.</span><span class="sxs-lookup"><span data-stu-id="57dfa-103">This page lists some common problems that can occur when working with arrays.</span></span>  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a><span data-ttu-id="57dfa-104">Ошибки компиляции, объявления и инициализации массива</span><span class="sxs-lookup"><span data-stu-id="57dfa-104">Compilation Errors Declaring and Initializing an Array</span></span>  
 <span data-ttu-id="57dfa-105">Ошибки компиляции могут возникать из недопонимания правил для объявления, создания и инициализации массивов.</span><span class="sxs-lookup"><span data-stu-id="57dfa-105">Compilation errors can arise from misunderstanding of the rules for declaring, creating, and initializing arrays.</span></span> <span data-ttu-id="57dfa-106">Далее перечислены наиболее распространенные причины ошибки:</span><span class="sxs-lookup"><span data-stu-id="57dfa-106">The most common causes of errors are the following:</span></span>  
  
-   <span data-ttu-id="57dfa-107">Предоставление [оператор New](../../../../visual-basic/language-reference/operators/new-operator.md) предложение после указания размерностей при объявлении переменной массива.</span><span class="sxs-lookup"><span data-stu-id="57dfa-107">Supplying a [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) clause after specifying dimension lengths in the array variable declaration.</span></span> <span data-ttu-id="57dfa-108">Следующие строки кода показывают недопустимые объявления этого типа.</span><span class="sxs-lookup"><span data-stu-id="57dfa-108">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
-   <span data-ttu-id="57dfa-109">Указание размерностей для более чем массива верхнего уровня массива массивов.</span><span class="sxs-lookup"><span data-stu-id="57dfa-109">Specifying dimension lengths for more than the top-level array of a jagged array.</span></span> <span data-ttu-id="57dfa-110">Следующая строка кода показывает недопустимое объявление этого типа.</span><span class="sxs-lookup"><span data-stu-id="57dfa-110">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
-   <span data-ttu-id="57dfa-111">Пропуск `New` ключевое слово, при указании значения элементов.</span><span class="sxs-lookup"><span data-stu-id="57dfa-111">Omitting the `New` keyword when specifying the element values.</span></span> <span data-ttu-id="57dfa-112">Следующая строка кода показывает недопустимое объявление этого типа.</span><span class="sxs-lookup"><span data-stu-id="57dfa-112">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
-   <span data-ttu-id="57dfa-113">Предоставление `New` предложение без фигурных скобок (`{}`).</span><span class="sxs-lookup"><span data-stu-id="57dfa-113">Supplying a `New` clause without braces (`{}`).</span></span> <span data-ttu-id="57dfa-114">Следующие строки кода показывают недопустимые объявления этого типа.</span><span class="sxs-lookup"><span data-stu-id="57dfa-114">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a><span data-ttu-id="57dfa-115">Доступ к массиву за пределы допустимого диапазона</span><span class="sxs-lookup"><span data-stu-id="57dfa-115">Accessing an Array Out of Bounds</span></span>  
 <span data-ttu-id="57dfa-116">Процесс инициализации массива назначает верхнюю и нижнюю границу для каждого измерения.</span><span class="sxs-lookup"><span data-stu-id="57dfa-116">The process of initializing an array assigns an upper bound and a lower bound to each dimension.</span></span> <span data-ttu-id="57dfa-117">У каждого доступа к элементу массива необходимо указать допустимый индекс или индекс для любой размерности.</span><span class="sxs-lookup"><span data-stu-id="57dfa-117">Every access to an element of the array must specify a valid index, or subscript, for every dimension.</span></span> <span data-ttu-id="57dfa-118">Если индекс является ниже его нижней границы или выше верхней границы, <xref:System.IndexOutOfRangeException>Результаты исключения.</xref:System.IndexOutOfRangeException></span><span class="sxs-lookup"><span data-stu-id="57dfa-118">If any index is below its lower bound or above its upper bound, an <xref:System.IndexOutOfRangeException> exception results.</span></span> <span data-ttu-id="57dfa-119">Компилятор не обнаруживает такую ошибку, поэтому она возникает во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="57dfa-119">The compiler cannot detect such an error, so an error occurs at run time.</span></span>  
  
### <a name="determining-bounds"></a><span data-ttu-id="57dfa-120">Определение границ</span><span class="sxs-lookup"><span data-stu-id="57dfa-120">Determining Bounds</span></span>  
 <span data-ttu-id="57dfa-121">Если другой компонент передает массив в код, например в качестве аргумента процедуры неизвестно размер массива или длина его измерений.</span><span class="sxs-lookup"><span data-stu-id="57dfa-121">If another component passes an array to your code, for example as a procedure argument, you do not know the size of that array or the lengths of its dimensions.</span></span> <span data-ttu-id="57dfa-122">Следует всегда определять верхнюю границу для каждого измерения массива до попытки получить доступ все элементы.</span><span class="sxs-lookup"><span data-stu-id="57dfa-122">You should always determine the upper bound for every dimension of an array before you attempt to access any elements.</span></span> <span data-ttu-id="57dfa-123">Если массив был создан с помощью некоторых средств не [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `New` предложение, нижняя граница может быть отлична от 0, и лучше всего определить, что нижняя граница.</span><span class="sxs-lookup"><span data-stu-id="57dfa-123">If the array has been created by some means other than a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `New` clause, the lower bound might be something other than 0, and it is safest to determine that lower bound as well.</span></span>  
  
### <a name="specifying-the-dimension"></a><span data-ttu-id="57dfa-124">Указание измерения</span><span class="sxs-lookup"><span data-stu-id="57dfa-124">Specifying the Dimension</span></span>  
 <span data-ttu-id="57dfa-125">При определении границ многомерного массива, будьте внимательны, как указать измерения.</span><span class="sxs-lookup"><span data-stu-id="57dfa-125">When determining the bounds of a multidimensional array, take care how you specify the dimension.</span></span> <span data-ttu-id="57dfa-126">`dimension` Параметры <xref:System.Array.GetLowerBound%2A>и <xref:System.Array.GetUpperBound%2A>методов ведется от нуля, при `Rank` параметры [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Information.LBound%2A>и <xref:Microsoft.VisualBasic.Information.UBound%2A>функции основаны на 1.</xref:Microsoft.VisualBasic.Information.UBound%2A> </xref:Microsoft.VisualBasic.Information.LBound%2A> </xref:System.Array.GetUpperBound%2A> </xref:System.Array.GetLowerBound%2A></span><span class="sxs-lookup"><span data-stu-id="57dfa-126">The `dimension` parameters of the <xref:System.Array.GetLowerBound%2A> and <xref:System.Array.GetUpperBound%2A> methods are 0-based, while the `Rank` parameters of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Information.LBound%2A> and <xref:Microsoft.VisualBasic.Information.UBound%2A> functions are 1-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57dfa-127">См. также</span><span class="sxs-lookup"><span data-stu-id="57dfa-127">See Also</span></span>  
 <span data-ttu-id="57dfa-128">[Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="57dfa-128">[Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md) </span></span>  
<span data-ttu-id="57dfa-129"> [Практическое руководство: инициализация переменной массива в Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)</span><span class="sxs-lookup"><span data-stu-id="57dfa-129"> [How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)</span></span>
