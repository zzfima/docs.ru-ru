---
title: Практическое руководство. Объявление и использование свойств чтения и записи (руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- get accessor [C#], declaring properties
- set accessor [C#]
- properties [C#], declaring
- read/write properties [C#]
- accessors [C#], declaring properties with
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
ms.openlocfilehash: 4b9db5f15746ab9a1f42239150c6783154723371
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79170290"
---
# <a name="how-to-declare-and-use-read-write-properties-c-programming-guide"></a><span data-ttu-id="9ea20-102">Практическое руководство. Объявление и использование свойств чтения и записи (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="9ea20-102">How to declare and use read write properties (C# Programming Guide)</span></span>
<span data-ttu-id="9ea20-103">Свойства имеют все преимущества открытых членов данных, но не связаны с рисками незащищенного, неконтролируемого и несанкционированного доступа к данным объекта.</span><span class="sxs-lookup"><span data-stu-id="9ea20-103">Properties provide the convenience of public data members without the risks that come with unprotected, uncontrolled, and unverified access to an object's data.</span></span> <span data-ttu-id="9ea20-104">Это достигается благодаря применению *методов доступа*, которые представляют собой особые методы для присвоения и извлечения значений базового члена данных.</span><span class="sxs-lookup"><span data-stu-id="9ea20-104">This is accomplished through *accessors*: special methods that assign and retrieve values from the underlying data member.</span></span> <span data-ttu-id="9ea20-105">Метод доступа [set](../../language-reference/keywords/set.md) присваивает значения членам данных, а метод доступа [get](../../language-reference/keywords/get.md) извлекает их.</span><span class="sxs-lookup"><span data-stu-id="9ea20-105">The [set](../../language-reference/keywords/set.md) accessor enables data members to be assigned, and the [get](../../language-reference/keywords/get.md) accessor retrieves data member values.</span></span>  
  
 <span data-ttu-id="9ea20-106">Это можно продемонстрировать на примере класса `Person`, который содержит два свойства: `Name` (string) и `Age` (int).</span><span class="sxs-lookup"><span data-stu-id="9ea20-106">This sample shows a `Person` class that has two properties: `Name` (string) and `Age` (int).</span></span> <span data-ttu-id="9ea20-107">Для обоих свойств реализованы методы доступа `get` и `set`, благодаря чему они доступны и для чтения, и для записи.</span><span class="sxs-lookup"><span data-stu-id="9ea20-107">Both properties provide `get` and `set` accessors, so they are considered read/write properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ea20-108">Пример</span><span class="sxs-lookup"><span data-stu-id="9ea20-108">Example</span></span>  
 [!code-csharp[csProgGuideObjects#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#33)]  
  
## <a name="robust-programming"></a><span data-ttu-id="9ea20-109">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="9ea20-109">Robust Programming</span></span>  
 <span data-ttu-id="9ea20-110">В предыдущем примере свойства `Name` и `Age` являются [открытыми](../../language-reference/keywords/public.md) и содержат одновременно методы доступа `get` и `set`.</span><span class="sxs-lookup"><span data-stu-id="9ea20-110">In the previous example, the `Name` and `Age` properties are [public](../../language-reference/keywords/public.md) and include both a `get` and a `set` accessor.</span></span> <span data-ttu-id="9ea20-111">Благодаря этому объект может считывать эти свойства и записывать их.</span><span class="sxs-lookup"><span data-stu-id="9ea20-111">This allows any object to read and write these properties.</span></span> <span data-ttu-id="9ea20-112">Тем не менее в некоторых случаях необходимо исключить один из методов доступа.</span><span class="sxs-lookup"><span data-stu-id="9ea20-112">It is sometimes desirable, however, to exclude one of the accessors.</span></span> <span data-ttu-id="9ea20-113">Например, свойство без метода доступа `set` будет доступно только для чтения:</span><span class="sxs-lookup"><span data-stu-id="9ea20-113">Omitting the `set` accessor, for example, makes the property read-only:</span></span>  
  
 [!code-csharp[csProgGuideObjects#87](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#87)]  
  
 <span data-ttu-id="9ea20-114">Кроме того, можно сделать один метод доступа открытым, а другой оставить частным или защищенным.</span><span class="sxs-lookup"><span data-stu-id="9ea20-114">Alternatively, you can expose one accessor publicly but make the other private or protected.</span></span> <span data-ttu-id="9ea20-115">Дополнительные сведения см. в разделе [Асимметричные методы доступа](./restricting-accessor-accessibility.md).</span><span class="sxs-lookup"><span data-stu-id="9ea20-115">For more information, see [Asymmetric Accessor Accessibility](./restricting-accessor-accessibility.md).</span></span>  
  
 <span data-ttu-id="9ea20-116">После объявления свойств их можно использовать так же, как поля класса.</span><span class="sxs-lookup"><span data-stu-id="9ea20-116">Once the properties are declared, they can be used as if they were fields of the class.</span></span> <span data-ttu-id="9ea20-117">Это позволяет получить естественный синтаксис извлечения и установки значения свойства, как показано на примере следующих операторов:</span><span class="sxs-lookup"><span data-stu-id="9ea20-117">This allows for a very natural syntax when both getting and setting the value of a property, as in the following statements:</span></span>  
  
 [!code-csharp[csProgGuideObjects#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#35)]  
  
 <span data-ttu-id="9ea20-118">Обратите внимание, что в методе `set` свойства доступна специальная переменная `value`.</span><span class="sxs-lookup"><span data-stu-id="9ea20-118">Note that in a property `set` method a special `value` variable is available.</span></span> <span data-ttu-id="9ea20-119">Она содержит значение, заданное пользователем, например:</span><span class="sxs-lookup"><span data-stu-id="9ea20-119">This variable contains the value that the user specified, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#36)]  
  
 <span data-ttu-id="9ea20-120">Обратите внимание на простой синтаксис приращения свойства `Age` для объекта `Person`:</span><span class="sxs-lookup"><span data-stu-id="9ea20-120">Notice the clean syntax for incrementing the `Age` property on a `Person` object:</span></span>  
  
 [!code-csharp[csProgGuideObjects#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#37)]  
  
 <span data-ttu-id="9ea20-121">Если для моделирования свойств использовать отдельные методы `set` и `get`, аналогичный код может иметь следующий вид:</span><span class="sxs-lookup"><span data-stu-id="9ea20-121">If separate `set` and `get` methods were used to model properties, the equivalent code might look like this:</span></span>  
  
```csharp  
person.SetAge(person.GetAge() + 1);
```  
  
 <span data-ttu-id="9ea20-122">В этом примере переопределяется метод `ToString`:</span><span class="sxs-lookup"><span data-stu-id="9ea20-122">The `ToString` method is overridden in this example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#38)]  
  
 <span data-ttu-id="9ea20-123">Обратите внимание, что метод `ToString` не используется в этой программе явно.</span><span class="sxs-lookup"><span data-stu-id="9ea20-123">Notice that `ToString` is not explicitly used in the program.</span></span> <span data-ttu-id="9ea20-124">Он вызывается по умолчанию при вызове `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="9ea20-124">It is invoked by default by the `WriteLine` calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ea20-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9ea20-125">See also</span></span>

- [<span data-ttu-id="9ea20-126">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="9ea20-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="9ea20-127">Свойства</span><span class="sxs-lookup"><span data-stu-id="9ea20-127">Properties</span></span>](./properties.md)
- [<span data-ttu-id="9ea20-128">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="9ea20-128">Classes and Structs</span></span>](./index.md)
