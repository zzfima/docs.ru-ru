---
title: Неявно типизированные лямбда-выражения
description: Сведения о том, почему объявление неявно типизированной переменной нельзя использовать для объявления лямбда-выражения.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: a3851da9-e018-4389-9922-233db7d0f841
ms.openlocfilehash: cf16bb4d9ed27f536ae163284f36a0f305877139
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713888"
---
# <a name="implicitly-typed-lambda-expressions"></a><span data-ttu-id="a4783-103">Неявно типизированные лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="a4783-103">Implicitly typed lambda expressions</span></span>

<span data-ttu-id="a4783-104">Объявление неявно типизированной переменной нельзя использовать для объявления лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="a4783-104">You can't use an implicitly typed variable declaration to declare a lambda expression.</span></span>
<span data-ttu-id="a4783-105">В этом случае компилятор сталкивается с проблемой замкнутого цикла.</span><span class="sxs-lookup"><span data-stu-id="a4783-105">It creates a circular logic problem for the compiler.</span></span> <span data-ttu-id="a4783-106">Объявление `var` предписывает компилятору определить тип переменной на основе типа выражения в правой части оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="a4783-106">The `var` declaration tells the compiler to figure out the type of the variable from the type of expression on the right hand side of the assignment operator.</span></span> <span data-ttu-id="a4783-107">Лямбда-выражение не имеет типа во время компиляции, но может быть преобразовано в любой соответствующий тип делегата или выражения.</span><span class="sxs-lookup"><span data-stu-id="a4783-107">A lambda expression does not have a compile time type, but is convertible to any matching delegate or expression type.</span></span> <span data-ttu-id="a4783-108">Когда вы присваиваете лямбда-выражение переменной, имеющей тип делегата или выражения, вы предписываете компилятору выполнить попытку преобразовать лямбда-выражение в выражение или делегат, которые соответствуют сигнатуре этой переменной.</span><span class="sxs-lookup"><span data-stu-id="a4783-108">When you assign a lambda expression to a variable of a delegate or expression type, you tell the compiler to try and convert the lambda expression into an expression or delegate that matches the signature of the 'assigned to' variable.</span></span> <span data-ttu-id="a4783-109">Компилятор должен попытаться сделать так, чтобы правая часть присваивания соответствовала типу левой части.</span><span class="sxs-lookup"><span data-stu-id="a4783-109">The compiler must try to make the thing on the right hand side of the assignment match the type on the left hand side of the assignment.</span></span> 

<span data-ttu-id="a4783-110">Обе части оператора присваивания не могут одновременно предписывать компилятору выполнить проверку объекта в другой части на предмет соответствия типа.</span><span class="sxs-lookup"><span data-stu-id="a4783-110">Both sides of the assignment can't be telling the compiler to look at the object on the other side of the assignment operator and see if my type matches.</span></span>

<span data-ttu-id="a4783-111">Дополнительные сведения о том, почему в языке C# принято такое поведение, см. в [этой статье](https://download.microsoft.com/download/5/4/B/54B83DFE-D7AA-4155-9687-B0CF58FF65D7/type-inference.pdf) (скачиваемый PDF-файл).</span><span class="sxs-lookup"><span data-stu-id="a4783-111">You can get even more details on why the C# language specifies that behavior by reading [this article](https://download.microsoft.com/download/5/4/B/54B83DFE-D7AA-4155-9687-B0CF58FF65D7/type-inference.pdf) (PDF download).</span></span>
