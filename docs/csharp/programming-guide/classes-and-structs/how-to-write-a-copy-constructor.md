---
title: "Практическое руководство. Создание конструктора копии (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f15d8fabc49cbff5515b78a7d2fb6f9e49d0704e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="74d59-102">Практическое руководство. Создание конструктора копии (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="74d59-102">How to: Write a Copy Constructor (C# Programming Guide)</span></span>
<span data-ttu-id="74d59-103">В C# не предусмотрен конструктор копии для объектов, однако его можно написать самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="74d59-103">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74d59-104">Пример</span><span class="sxs-lookup"><span data-stu-id="74d59-104">Example</span></span>  
 <span data-ttu-id="74d59-105">В следующем примере [класс](../../../csharp/language-reference/keywords/class.md) `Person` определяет конструктор копии, который использует экземпляр `Person`в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="74d59-105">In the following example, the `Person`[class](../../../csharp/language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="74d59-106">Значения свойств аргумента присваиваются свойствам нового экземпляра `Person`.</span><span class="sxs-lookup"><span data-stu-id="74d59-106">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="74d59-107">Код содержит дополнительный конструктор копии, который отправляет свойства `Name` и `Age` экземпляра, который необходимо скопировать конструктору экземпляра класса.</span><span class="sxs-lookup"><span data-stu-id="74d59-107">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-write-a-copy-constructor_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="74d59-108">См. также</span><span class="sxs-lookup"><span data-stu-id="74d59-108">See Also</span></span>  
 <xref:System.ICloneable>  
 [<span data-ttu-id="74d59-109">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="74d59-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="74d59-110">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="74d59-110">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="74d59-111">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="74d59-111">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
 [<span data-ttu-id="74d59-112">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="74d59-112">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
