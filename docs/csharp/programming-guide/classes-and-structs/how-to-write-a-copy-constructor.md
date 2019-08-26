---
title: Практическое руководство. Создание конструктора копий (руководство по программированию на C#)
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: bdc352566052f4cec1686176131e9b1e1b768794
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69596601"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="42d52-102">Практическое руководство. Создание конструктора копий (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="42d52-102">How to: Write a Copy Constructor (C# Programming Guide)</span></span>
<span data-ttu-id="42d52-103">В C# не предусмотрен конструктор копии для объектов, однако его можно написать самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="42d52-103">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42d52-104">Пример</span><span class="sxs-lookup"><span data-stu-id="42d52-104">Example</span></span>  
 <span data-ttu-id="42d52-105">В следующем примере [класс](../../language-reference/keywords/class.md) `Person` определяет конструктор копии, который использует экземпляр `Person`в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="42d52-105">In the following example, the `Person`[class](../../language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="42d52-106">Значения свойств аргумента присваиваются свойствам нового экземпляра `Person`.</span><span class="sxs-lookup"><span data-stu-id="42d52-106">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="42d52-107">Код содержит дополнительный конструктор копии, который отправляет свойства `Name` и `Age` экземпляра, который необходимо скопировать конструктору экземпляра класса.</span><span class="sxs-lookup"><span data-stu-id="42d52-107">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#16)]  
  
## <a name="see-also"></a><span data-ttu-id="42d52-108">См. также</span><span class="sxs-lookup"><span data-stu-id="42d52-108">See also</span></span>

- <xref:System.ICloneable>
- [<span data-ttu-id="42d52-109">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="42d52-109">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="42d52-110">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="42d52-110">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="42d52-111">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="42d52-111">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="42d52-112">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="42d52-112">Finalizers</span></span>](./destructors.md)
