---
title: "Типы методов для работы со строками в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b437be4a6f4a0cc9d5a4d21291a80c9cb8fffcd3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="41ee3-102">Типы методов для работы со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="41ee3-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="41ee3-103">Существует несколько способов для анализа и работы со строками.</span><span class="sxs-lookup"><span data-stu-id="41ee3-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="41ee3-104">Некоторые методы являются частью [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] язык и другие принадлежат `String` класса.</span><span class="sxs-lookup"><span data-stu-id="41ee3-104">Some of the methods are a part of the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="41ee3-105">Язык Visual Basic и .NET Framework</span><span class="sxs-lookup"><span data-stu-id="41ee3-105">Visual Basic Language and the .NET Framework</span></span>  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="41ee3-106">методы используются как встроенные функции языка.</span><span class="sxs-lookup"><span data-stu-id="41ee3-106"> methods are used as inherent functions of the language.</span></span> <span data-ttu-id="41ee3-107">Они могут использоваться без уточнения в коде.</span><span class="sxs-lookup"><span data-stu-id="41ee3-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="41ee3-108">В следующем примере показано типичное использование [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] команды управления строками:</span><span class="sxs-lookup"><span data-stu-id="41ee3-108">The following example shows typical use of a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] string-manipulation command:</span></span>  
  
 [!code-vb[VbVbalrStrings#44](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]  
  
 <span data-ttu-id="41ee3-109">В этом примере `Mid` функция выполняет операцию прямой на `aString` и присваивает это значение `bString`.</span><span class="sxs-lookup"><span data-stu-id="41ee3-109">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="41ee3-110">Список методов Visual Basic для обработки см. в разделе [Сводка управления строками](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span><span class="sxs-lookup"><span data-stu-id="41ee3-110">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="41ee3-111">Общие методы и методы экземпляра</span><span class="sxs-lookup"><span data-stu-id="41ee3-111">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="41ee3-112">Строки также можно работать с методами `String` класса.</span><span class="sxs-lookup"><span data-stu-id="41ee3-112">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="41ee3-113">Существует два типа методов в `String`: *общего* методы и *экземпляр* методы.</span><span class="sxs-lookup"><span data-stu-id="41ee3-113">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="41ee3-114">Общие методы</span><span class="sxs-lookup"><span data-stu-id="41ee3-114">Shared Methods</span></span>  
 <span data-ttu-id="41ee3-115">Общий метод является методом, основанная на `String` сам класс и не требует экземпляр этого класса для работы.</span><span class="sxs-lookup"><span data-stu-id="41ee3-115">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="41ee3-116">Эти методы могут быть дополнены имя класса (`String`), а не с помощью экземпляра `String` класса.</span><span class="sxs-lookup"><span data-stu-id="41ee3-116">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="41ee3-117">Пример:</span><span class="sxs-lookup"><span data-stu-id="41ee3-117">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#45](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]  
  
 <span data-ttu-id="41ee3-118">В приведенном выше примере <xref:System.String.Copy%2A?displayProperty=nameWithType> метод является статическим методом, который функционирует после выражения он получает и присваивает результирующее значение `bString`.</span><span class="sxs-lookup"><span data-stu-id="41ee3-118">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=nameWithType> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="41ee3-119">Методы экземпляра</span><span class="sxs-lookup"><span data-stu-id="41ee3-119">Instance Methods</span></span>  
 <span data-ttu-id="41ee3-120">Методы экземпляра, в отличие от этого, возникающих из-за определенный экземпляр `String` и должны быть дополнены именем экземпляра.</span><span class="sxs-lookup"><span data-stu-id="41ee3-120">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="41ee3-121">Пример:</span><span class="sxs-lookup"><span data-stu-id="41ee3-121">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#46](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]  
  
 <span data-ttu-id="41ee3-122">В этом примере <xref:System.String.Substring%2A?displayProperty=nameWithType> метод является методом экземпляра `String` (то есть, `aString`).</span><span class="sxs-lookup"><span data-stu-id="41ee3-122">In this example, the <xref:System.String.Substring%2A?displayProperty=nameWithType> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="41ee3-123">Он выполняет операцию над `aString` и присваивает это значение `bString`.</span><span class="sxs-lookup"><span data-stu-id="41ee3-123">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="41ee3-124">Дополнительные сведения см. в документации для <xref:System.String> класса.</span><span class="sxs-lookup"><span data-stu-id="41ee3-124">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41ee3-125">См. также</span><span class="sxs-lookup"><span data-stu-id="41ee3-125">See Also</span></span>  
 [<span data-ttu-id="41ee3-126">Знакомство со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="41ee3-126">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
