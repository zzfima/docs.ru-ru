---
title: Практическое руководство. Создание конструктора копии (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: 8a7cc85d40272918f4839d13fcccb79b558eeac7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322501"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="f7c65-102">Практическое руководство. Создание конструктора копии (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="f7c65-102">How to: Write a Copy Constructor (C# Programming Guide)</span></span>
<span data-ttu-id="f7c65-103">В C# не предусмотрен конструктор копии для объектов, однако его можно написать самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="f7c65-103">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7c65-104">Пример</span><span class="sxs-lookup"><span data-stu-id="f7c65-104">Example</span></span>  
 <span data-ttu-id="f7c65-105">В следующем примере [класс](../../../csharp/language-reference/keywords/class.md) `Person` определяет конструктор копии, который использует экземпляр `Person`в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="f7c65-105">In the following example, the `Person`[class](../../../csharp/language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="f7c65-106">Значения свойств аргумента присваиваются свойствам нового экземпляра `Person`.</span><span class="sxs-lookup"><span data-stu-id="f7c65-106">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="f7c65-107">Код содержит дополнительный конструктор копии, который отправляет свойства `Name` и `Age` экземпляра, который необходимо скопировать конструктору экземпляра класса.</span><span class="sxs-lookup"><span data-stu-id="f7c65-107">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-write-a-copy-constructor_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="f7c65-108">См. также</span><span class="sxs-lookup"><span data-stu-id="f7c65-108">See Also</span></span>  
 <xref:System.ICloneable>  
 [<span data-ttu-id="f7c65-109">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f7c65-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f7c65-110">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="f7c65-110">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="f7c65-111">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="f7c65-111">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
 [<span data-ttu-id="f7c65-112">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="f7c65-112">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
