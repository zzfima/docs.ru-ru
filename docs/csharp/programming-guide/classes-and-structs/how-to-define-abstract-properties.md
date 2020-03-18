---
title: Практическое руководство. Определение абстрактных свойств (руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], abstract
- abstract properties [C#]
ms.assetid: 672a90eb-47b9-4ae0-9914-af53852fddcb
ms.openlocfilehash: c46f36133b68a550a17cf882844fd2481eee8851
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705617"
---
# <a name="how-to-define-abstract-properties-c-programming-guide"></a><span data-ttu-id="f89f0-102">Практическое руководство. Определение абстрактных свойств (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="f89f0-102">How to define abstract properties (C# Programming Guide)</span></span>
<span data-ttu-id="f89f0-103">В следующем примере показано, как определять [абстрактные](../../language-reference/keywords/abstract.md) свойства.</span><span class="sxs-lookup"><span data-stu-id="f89f0-103">The following example shows how to define [abstract](../../language-reference/keywords/abstract.md) properties.</span></span> <span data-ttu-id="f89f0-104">В объявлении абстрактного свойства не предоставляется реализация методов доступа к свойству. В нем объявляется, что класс поддерживает свойства, однако реализация методов доступа к ним передается в производные классы.</span><span class="sxs-lookup"><span data-stu-id="f89f0-104">An abstract property declaration does not provide an implementation of the property accessors -- it declares that the class supports properties, but leaves the accessor implementation to derived classes.</span></span> <span data-ttu-id="f89f0-105">В следующем примере показано, как реализовать абстрактные свойства, наследуемые от базового класса.</span><span class="sxs-lookup"><span data-stu-id="f89f0-105">The following example demonstrates how to implement the abstract properties inherited from a base class.</span></span>  
  
 <span data-ttu-id="f89f0-106">Этот пример включает три файла, каждый из которых компилируется отдельно в сборку, на которую задаются ссылки при последующей компиляции:</span><span class="sxs-lookup"><span data-stu-id="f89f0-106">This sample consists of three files, each of which is compiled individually and its resulting assembly is referenced by the next compilation:</span></span>  
  
- <span data-ttu-id="f89f0-107">abstractshape.cs: класс `Shape`, который содержит абстрактное свойство `Area`.</span><span class="sxs-lookup"><span data-stu-id="f89f0-107">abstractshape.cs: the `Shape` class that contains an abstract `Area` property.</span></span>  
  
- <span data-ttu-id="f89f0-108">shapes.cs: подклассы класса `Shape`.</span><span class="sxs-lookup"><span data-stu-id="f89f0-108">shapes.cs: The subclasses of the `Shape` class.</span></span>  
  
- <span data-ttu-id="f89f0-109">shapetest.cs: тестовая программа для отображения областей некоторых объектов, производных от `Shape`.</span><span class="sxs-lookup"><span data-stu-id="f89f0-109">shapetest.cs: A test program to display the areas of some `Shape`-derived objects.</span></span>  
  
 <span data-ttu-id="f89f0-110">Чтобы скомпилировать этот пример, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f89f0-110">To compile the example, use the following command:</span></span>  
  
 `csc abstractshape.cs shapes.cs shapetest.cs`  
  
 <span data-ttu-id="f89f0-111">При этом будет создан исполняемый файл shapetest.exe.</span><span class="sxs-lookup"><span data-stu-id="f89f0-111">This will create the executable file shapetest.exe.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f89f0-112">Пример</span><span class="sxs-lookup"><span data-stu-id="f89f0-112">Example</span></span>  
 <span data-ttu-id="f89f0-113">В этом файле объявляется класс `Shape`, который содержит свойство `Area` типа `double`.</span><span class="sxs-lookup"><span data-stu-id="f89f0-113">This file declares the `Shape` class that contains the `Area` property of the type `double`.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#1)]  
  
- <span data-ttu-id="f89f0-114">Модификаторы свойства помещаются в само объявление свойства.</span><span class="sxs-lookup"><span data-stu-id="f89f0-114">Modifiers on the property are placed on the property declaration itself.</span></span> <span data-ttu-id="f89f0-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="f89f0-115">For example:</span></span>  
  
    ```csharp  
    public abstract double Area  
    ```  
  
- <span data-ttu-id="f89f0-116">При объявлении абстрактного свойства, такого как `Area` в этом примере, вы просто указываете используемые методы доступа, но не реализуете их.</span><span class="sxs-lookup"><span data-stu-id="f89f0-116">When declaring an abstract property (such as `Area` in this example), you simply indicate what property accessors are available, but do not implement them.</span></span> <span data-ttu-id="f89f0-117">В этом примере используется только метод доступа [get](../../language-reference/keywords/get.md), поэтому свойство будет доступно только для чтения.</span><span class="sxs-lookup"><span data-stu-id="f89f0-117">In this example, only a [get](../../language-reference/keywords/get.md) accessor is available, so the property is read-only.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f89f0-118">Пример</span><span class="sxs-lookup"><span data-stu-id="f89f0-118">Example</span></span>  
 <span data-ttu-id="f89f0-119">В следующем коде представлены три подкласса класса `Shape` и демонстрируется, как они переопределяют свойство `Area` для получения его собственной реализации.</span><span class="sxs-lookup"><span data-stu-id="f89f0-119">The following code shows three subclasses of `Shape` and how they override the `Area` property to provide their own implementation.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#2)]  
  
## <a name="example"></a><span data-ttu-id="f89f0-120">Пример</span><span class="sxs-lookup"><span data-stu-id="f89f0-120">Example</span></span>  
 <span data-ttu-id="f89f0-121">В следующем коде показана тестовая программа, которая создает несколько производных от `Shape` объектов и печатает их области.</span><span class="sxs-lookup"><span data-stu-id="f89f0-121">The following code shows a test program that creates a number of `Shape`-derived objects and prints out their areas.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#3)]  
  
## <a name="see-also"></a><span data-ttu-id="f89f0-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f89f0-122">See also</span></span>

- [<span data-ttu-id="f89f0-123">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f89f0-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f89f0-124">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="f89f0-124">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="f89f0-125">Абстрактные и запечатанные классы и члены классов</span><span class="sxs-lookup"><span data-stu-id="f89f0-125">Abstract and Sealed Classes and Class Members</span></span>](./abstract-and-sealed-classes-and-class-members.md)
- [<span data-ttu-id="f89f0-126">Свойства</span><span class="sxs-lookup"><span data-stu-id="f89f0-126">Properties</span></span>](./properties.md)
