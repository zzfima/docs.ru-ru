---
title: Практическое руководство. Создание конструктора копий (руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: aa6feb1b07f491a90a78684e254910d387b9bccd
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714843"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="0186f-102">Практическое руководство. Создание конструктора копий (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="0186f-102">How to write a copy constructor (C# Programming Guide)</span></span>
<span data-ttu-id="0186f-103">В C# не предусмотрен конструктор копии для объектов, однако его можно написать самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="0186f-103">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0186f-104">Пример</span><span class="sxs-lookup"><span data-stu-id="0186f-104">Example</span></span>  
 <span data-ttu-id="0186f-105">В следующем примере [класс](../../language-reference/keywords/class.md)`Person` определяет конструктор копии, который использует экземпляр `Person`в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="0186f-105">In the following example, the `Person`[class](../../language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="0186f-106">Значения свойств аргумента присваиваются свойствам нового экземпляра `Person`.</span><span class="sxs-lookup"><span data-stu-id="0186f-106">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="0186f-107">Код содержит дополнительный конструктор копии, который отправляет свойства `Name` и `Age` экземпляра, который необходимо скопировать конструктору экземпляра класса.</span><span class="sxs-lookup"><span data-stu-id="0186f-107">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#16)]  
  
## <a name="see-also"></a><span data-ttu-id="0186f-108">См. также</span><span class="sxs-lookup"><span data-stu-id="0186f-108">See also</span></span>

- <xref:System.ICloneable>
- [<span data-ttu-id="0186f-109">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0186f-109">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="0186f-110">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="0186f-110">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="0186f-111">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="0186f-111">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="0186f-112">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="0186f-112">Finalizers</span></span>](./destructors.md)
