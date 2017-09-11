---
title: "Типы методов для обработки в Visual Basic | Документы Microsoft"
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
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
caps.latest.revision: 12
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
ms.openlocfilehash: 9c63ad0931ae2f3760576a792795b9fe0ab6a409
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="02b58-102">Типы методов для работы со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="02b58-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="02b58-103">Существует несколько способов анализа и работы со строками.</span><span class="sxs-lookup"><span data-stu-id="02b58-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="02b58-104">Некоторые методы являются частью [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] язык и другие принадлежат `String` класса.</span><span class="sxs-lookup"><span data-stu-id="02b58-104">Some of the methods are a part of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="02b58-105">Язык Visual Basic и .NET Framework</span><span class="sxs-lookup"><span data-stu-id="02b58-105">Visual Basic Language and the .NET Framework</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="02b58-106">методы используются как встроенные функции языка.</span><span class="sxs-lookup"><span data-stu-id="02b58-106"> methods are used as inherent functions of the language.</span></span> <span data-ttu-id="02b58-107">Они могут использоваться без уточнения в коде.</span><span class="sxs-lookup"><span data-stu-id="02b58-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="02b58-108">В следующем примере показано типичное использование [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] команды управления строками:</span><span class="sxs-lookup"><span data-stu-id="02b58-108">The following example shows typical use of a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] string-manipulation command:</span></span>  
  
 <span data-ttu-id="02b58-109">[!code-vb[VbVbalrStrings&#44;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="02b58-109">[!code-vb[VbVbalrStrings#44](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]</span></span>  
  
 <span data-ttu-id="02b58-110">В этом примере `Mid` функция выполняет прямую операцию на `aString` и присваивает это значение `bString`.</span><span class="sxs-lookup"><span data-stu-id="02b58-110">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="02b58-111">Список методов обработки для Visual Basic, в разделе [Сводка управления строками](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span><span class="sxs-lookup"><span data-stu-id="02b58-111">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="02b58-112">Общие методы и методы экземпляра</span><span class="sxs-lookup"><span data-stu-id="02b58-112">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="02b58-113">Строками можно управлять с помощью методов `String` класса.</span><span class="sxs-lookup"><span data-stu-id="02b58-113">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="02b58-114">Существует два типа методов в `String`: *общего* методы и *экземпляр* методы.</span><span class="sxs-lookup"><span data-stu-id="02b58-114">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="02b58-115">Общие методы</span><span class="sxs-lookup"><span data-stu-id="02b58-115">Shared Methods</span></span>  
 <span data-ttu-id="02b58-116">Общий метод является методом, порождаемой `String` сам класс и не требует экземпляр этого класса для работы.</span><span class="sxs-lookup"><span data-stu-id="02b58-116">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="02b58-117">Эти методы могут быть уточнено именем класса (`String`), а не с экземпляром `String` класса.</span><span class="sxs-lookup"><span data-stu-id="02b58-117">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="02b58-118">Например:</span><span class="sxs-lookup"><span data-stu-id="02b58-118">For example:</span></span>  
  
 <span data-ttu-id="02b58-119">[!code-vb[VbVbalrStrings&#45;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="02b58-119">[!code-vb[VbVbalrStrings#45](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]</span></span>  
  
 <span data-ttu-id="02b58-120">В предыдущем примере <xref:System.String.Copy%2A?displayProperty=fullName>является статическим методом, выражение, которое функционирует он получает и присваивает полученное значение для `bString`.</xref:System.String.Copy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="02b58-120">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=fullName> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="02b58-121">Методы экземпляра</span><span class="sxs-lookup"><span data-stu-id="02b58-121">Instance Methods</span></span>  
 <span data-ttu-id="02b58-122">Методы экземпляра, напротив, вытекают из конкретного экземпляра `String` и должны уточняться именем экземпляра.</span><span class="sxs-lookup"><span data-stu-id="02b58-122">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="02b58-123">Пример:</span><span class="sxs-lookup"><span data-stu-id="02b58-123">For example:</span></span>  
  
 <span data-ttu-id="02b58-124">[!code-vb[VbVbalrStrings&#46;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="02b58-124">[!code-vb[VbVbalrStrings#46](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]</span></span>  
  
 <span data-ttu-id="02b58-125">В этом примере <xref:System.String.Substring%2A?displayProperty=fullName>является методом экземпляра `String` (то есть, `aString`).</xref:System.String.Substring%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="02b58-125">In this example, the <xref:System.String.Substring%2A?displayProperty=fullName> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="02b58-126">Он выполняет операцию над `aString` и присваивает это значение `bString`.</span><span class="sxs-lookup"><span data-stu-id="02b58-126">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="02b58-127">Дополнительные сведения см. в документации для <xref:System.String>класса.</xref:System.String></span><span class="sxs-lookup"><span data-stu-id="02b58-127">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02b58-128">См. также</span><span class="sxs-lookup"><span data-stu-id="02b58-128">See Also</span></span>  
 [<span data-ttu-id="02b58-129">Знакомство со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="02b58-129">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
