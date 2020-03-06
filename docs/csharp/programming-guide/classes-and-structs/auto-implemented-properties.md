---
title: Руководство по программированию на C#. Автоматически реализуемые свойства
ms.date: 01/31/2020
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: 989266bfc2de9bd5ce2948f09a2b9f19dd2c782e
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628297"
---
# <a name="auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="d39e2-102">Автоматически реализуемые свойства (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="d39e2-102">Auto-Implemented Properties (C# Programming Guide)</span></span>

<span data-ttu-id="d39e2-103">В C# 3.0 и более поздних версиях автоматически реализуемые свойства делают объявление свойств более лаконичным, когда в методах доступа к свойствам не требуется дополнительная логика.</span><span class="sxs-lookup"><span data-stu-id="d39e2-103">In C# 3.0 and later, auto-implemented properties make property-declaration more concise when no additional logic is required in the property accessors.</span></span> <span data-ttu-id="d39e2-104">Они также позволяют клиентскому коду создавать объекты.</span><span class="sxs-lookup"><span data-stu-id="d39e2-104">They also enable client code to create objects.</span></span> <span data-ttu-id="d39e2-105">При объявлении свойства, как показано в следующем примере, компилятор создает закрытое анонимное резервное поле, которое может быть доступно только через методы доступа `get` и `set` свойства.</span><span class="sxs-lookup"><span data-stu-id="d39e2-105">When you declare a property as shown in the following example, the compiler creates a private, anonymous backing field that can only be accessed through the property's `get` and `set` accessors.</span></span>
  
## <a name="example"></a><span data-ttu-id="d39e2-106">Пример</span><span class="sxs-lookup"><span data-stu-id="d39e2-106">Example</span></span>

<span data-ttu-id="d39e2-107">В следующем примере показан простой класс, имеющий несколько автоматически реализуемых свойств.</span><span class="sxs-lookup"><span data-stu-id="d39e2-107">The following example shows a simple class that has some auto-implemented properties:</span></span>  

[!code-csharp[csProgGuideLINQ#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#28)]  

<span data-ttu-id="d39e2-108">В интерфейсах невозможно объявлять автоматически реализуемые свойства.</span><span class="sxs-lookup"><span data-stu-id="d39e2-108">You can't declare auto-implemented properties in interfaces.</span></span> <span data-ttu-id="d39e2-109">Автоматически реализуемые свойства объявляют резервное поле частного экземпляра, а интерфейсы могут не объявлять поля экземпляров.</span><span class="sxs-lookup"><span data-stu-id="d39e2-109">Auto-implemented properties declare a private instance backing field, and interfaces may not declare instance fields.</span></span> <span data-ttu-id="d39e2-110">Объявление свойства в интерфейсе без определения тела приводит к объявлению свойства с методами доступа, которые должны реализовываться каждым типом, реализующим этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="d39e2-110">Declaring a property in an interface without defining a body declares a property with accessors that must be implemented by each type that implements that interface.</span></span>

<span data-ttu-id="d39e2-111">В C# 6 и более поздних версиях можно инициализировать автоматически реализуемые свойства аналогично полям.</span><span class="sxs-lookup"><span data-stu-id="d39e2-111">In C# 6 and later, you can initialize auto-implemented properties similarly to fields:</span></span>  
 
```csharp  
public string FirstName { get; set; } = "Jane";  
```  
 
<span data-ttu-id="d39e2-112">Класс, который показан в предыдущем примере, является изменяемым.</span><span class="sxs-lookup"><span data-stu-id="d39e2-112">The class that is shown in the previous example is mutable.</span></span> <span data-ttu-id="d39e2-113">Клиентский код может изменить значения в объектах после создания.</span><span class="sxs-lookup"><span data-stu-id="d39e2-113">Client code can change the values in objects after creation.</span></span> <span data-ttu-id="d39e2-114">В сложных классах, которые содержат значительные возможности (методы) и данные, часто необходимо иметь открытые свойства.</span><span class="sxs-lookup"><span data-stu-id="d39e2-114">In complex classes that contain significant behavior (methods) as well as data, it's often necessary to have public properties.</span></span> <span data-ttu-id="d39e2-115">Однако для небольших классов или структур, которые просто инкапсулируют набор значений (данных) и имеют мало функциональных возможностей или совсем их не имеют, вы должны сделать объекты неизменяемыми либо путем объявления метода доступа set как [закрытого](../../language-reference/keywords/private.md) (неизменяемого для потребителей), либо путем объявления только метода доступа get (неизменяемого везде, кроме конструктора).</span><span class="sxs-lookup"><span data-stu-id="d39e2-115">However, for small classes or structs that just encapsulate a set of values (data) and have little or no behaviors, you should either make the objects immutable by declaring the set accessor as [private](../../language-reference/keywords/private.md) (immutable to consumers) or by declaring only a get accessor (immutable everywhere except the constructor).</span></span>  <span data-ttu-id="d39e2-116">Дополнительные сведения см. в статье [Практическое руководство. Реализация облегченного класса с автоматически реализуемыми свойствами](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d39e2-116">For more information, see [How to implement a lightweight class with auto-implemented properties](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d39e2-117">См. также</span><span class="sxs-lookup"><span data-stu-id="d39e2-117">See also</span></span>

- [<span data-ttu-id="d39e2-118">Свойства</span><span class="sxs-lookup"><span data-stu-id="d39e2-118">Properties</span></span>](./properties.md)
- [<span data-ttu-id="d39e2-119">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="d39e2-119">Modifiers</span></span>](/dotnet/csharp/language-reference/keywords)
