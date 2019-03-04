---
title: Как выполнить Руководство по программированию на C#. Создание конструктора копий
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: 169bdfc53d0c30ffc14e5a9525920679a94fbf23
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56982145"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="73502-102">Как выполнить Руководство по программированию на C#. Создание конструктора копий</span><span class="sxs-lookup"><span data-stu-id="73502-102">How to: Write a Copy Constructor (C# Programming Guide)</span></span>
<span data-ttu-id="73502-103">В C# не предусмотрен конструктор копии для объектов, однако его можно написать самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="73502-103">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73502-104">Пример</span><span class="sxs-lookup"><span data-stu-id="73502-104">Example</span></span>  
 <span data-ttu-id="73502-105">В следующем примере [класс](../../../csharp/language-reference/keywords/class.md) `Person` определяет конструктор копии, который использует экземпляр `Person`в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="73502-105">In the following example, the `Person`[class](../../../csharp/language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="73502-106">Значения свойств аргумента присваиваются свойствам нового экземпляра `Person`.</span><span class="sxs-lookup"><span data-stu-id="73502-106">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="73502-107">Код содержит дополнительный конструктор копии, который отправляет свойства `Name` и `Age` экземпляра, который необходимо скопировать конструктору экземпляра класса.</span><span class="sxs-lookup"><span data-stu-id="73502-107">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#16)]  
  
## <a name="see-also"></a><span data-ttu-id="73502-108">См. также</span><span class="sxs-lookup"><span data-stu-id="73502-108">See also</span></span>

- <xref:System.ICloneable>
- [<span data-ttu-id="73502-109">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="73502-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="73502-110">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="73502-110">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
- [<span data-ttu-id="73502-111">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="73502-111">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)
- [<span data-ttu-id="73502-112">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="73502-112">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
