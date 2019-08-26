---
title: Руководство по программированию на C#. Автоматически реализуемые свойства
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: 44f3beb9de8c9d339c42db26bb9c510998abc7d7
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69597134"
---
# <a name="auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="bec0d-102">Автоматически реализуемые свойства (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="bec0d-102">Auto-Implemented Properties (C# Programming Guide)</span></span>
<span data-ttu-id="bec0d-103">В C# 3.0 и более поздних версиях автоматически реализуемые свойства делают объявление свойств более лаконичным, когда в методах доступа к свойствам не требуется дополнительная логика.</span><span class="sxs-lookup"><span data-stu-id="bec0d-103">In C# 3.0 and later, auto-implemented properties make property-declaration more concise when no additional logic is required in the property accessors.</span></span> <span data-ttu-id="bec0d-104">Они также позволяют клиентскому коду создавать объекты.</span><span class="sxs-lookup"><span data-stu-id="bec0d-104">They also enable client code to create objects.</span></span> <span data-ttu-id="bec0d-105">При объявлении свойства, как показано в следующем примере, компилятор создает закрытое анонимное резервное поле, которое может быть доступно только через методы доступа `get` и `set` свойства.</span><span class="sxs-lookup"><span data-stu-id="bec0d-105">When you declare a property as shown in the following example, the compiler creates a private, anonymous backing field that can only be accessed through the property's `get` and `set` accessors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bec0d-106">Пример</span><span class="sxs-lookup"><span data-stu-id="bec0d-106">Example</span></span>  
 <span data-ttu-id="bec0d-107">В следующем примере показан простой класс, имеющий несколько автоматически реализуемых свойств.</span><span class="sxs-lookup"><span data-stu-id="bec0d-107">The following example shows a simple class that has some auto-implemented properties:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#28)]  
  
 <span data-ttu-id="bec0d-108">В C# 6 и более поздних версиях можно инициализировать автоматически реализуемые свойства аналогично полям.</span><span class="sxs-lookup"><span data-stu-id="bec0d-108">In C# 6 and later, you can initialize auto-implemented properties similarly to fields:</span></span>  
  
```csharp  
public string FirstName { get; set; } = "Jane";  
```  
  
 <span data-ttu-id="bec0d-109">Класс, который показан в предыдущем примере, является изменяемым.</span><span class="sxs-lookup"><span data-stu-id="bec0d-109">The class that is shown in the previous example is mutable.</span></span> <span data-ttu-id="bec0d-110">Клиентский код может изменить значения в объектах после их создания.</span><span class="sxs-lookup"><span data-stu-id="bec0d-110">Client code can change the values in objects after they are created.</span></span> <span data-ttu-id="bec0d-111">В сложных классах, которые содержат значительные возможности (методы) и данные, часто необходимо иметь открытые свойства.</span><span class="sxs-lookup"><span data-stu-id="bec0d-111">In complex classes that contain significant behavior (methods) as well as data, it is often necessary to have public properties.</span></span> <span data-ttu-id="bec0d-112">Однако для небольших классов или структур, которые просто инкапсулируют набор значений (данных) и имеют мало функциональных возможностей или совсем их не имеют, вы должны сделать объекты неизменяемыми либо путем объявления метода доступа set как [закрытого](../../language-reference/keywords/private.md) (неизменяемого для потребителей), либо путем объявления только метода доступа get (неизменяемого везде, кроме конструктора).</span><span class="sxs-lookup"><span data-stu-id="bec0d-112">However, for small classes or structs that just encapsulate a set of values (data) and have little or no behaviors, you should either make the objects immutable by declaring the set accessor as [private](../../language-reference/keywords/private.md) (immutable to consumers) or by declaring only a get accessor (immutable everywhere except the constructor).</span></span>  <span data-ttu-id="bec0d-113">Дополнительные сведения см. в разделе [Практическое руководство. реализации облегченного класса с автоматически реализуемыми свойствами](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="bec0d-113">For more information, see [How to: Implement a Lightweight Class with Auto-Implemented Properties](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bec0d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="bec0d-114">See also</span></span>

- [<span data-ttu-id="bec0d-115">Свойства</span><span class="sxs-lookup"><span data-stu-id="bec0d-115">Properties</span></span>](./properties.md)
- [<span data-ttu-id="bec0d-116">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="bec0d-116">Modifiers</span></span>](../../language-reference/keywords/modifiers.md)
