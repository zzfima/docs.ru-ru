---
title: Как выполнить Руководство по программированию на C#. Объявление и использование свойств чтения и записи
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- get accessor [C#], declaring properties
- set accessor [C#]
- properties [C#], declaring
- read/write properties [C#]
- accessors [C#], declaring properties with
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
ms.openlocfilehash: b4dc9364e64f7ebfd495671b852b98d8f56c80b5
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969045"
---
# <a name="how-to-declare-and-use-read-write-properties-c-programming-guide"></a><span data-ttu-id="d671f-102">Как выполнить Руководство по программированию на C#. Объявление и использование свойств чтения и записи</span><span class="sxs-lookup"><span data-stu-id="d671f-102">How to: Declare and Use Read Write Properties (C# Programming Guide)</span></span>
<span data-ttu-id="d671f-103">Свойства имеют все преимущества открытых членов данных, но не связаны с рисками незащищенного, неконтролируемого и несанкционированного доступа к данным объекта.</span><span class="sxs-lookup"><span data-stu-id="d671f-103">Properties provide the convenience of public data members without the risks that come with unprotected, uncontrolled, and unverified access to an object's data.</span></span> <span data-ttu-id="d671f-104">Это достигается благодаря применению *методов доступа*, которые представляют собой особые методы для присвоения и извлечения значений базового члена данных.</span><span class="sxs-lookup"><span data-stu-id="d671f-104">This is accomplished through *accessors*: special methods that assign and retrieve values from the underlying data member.</span></span> <span data-ttu-id="d671f-105">Метод доступа [set](../../../csharp/language-reference/keywords/set.md) присваивает значения членам данных, а метод доступа [get](../../../csharp/language-reference/keywords/get.md) извлекает их.</span><span class="sxs-lookup"><span data-stu-id="d671f-105">The [set](../../../csharp/language-reference/keywords/set.md) accessor enables data members to be assigned, and the [get](../../../csharp/language-reference/keywords/get.md) accessor retrieves data member values.</span></span>  
  
 <span data-ttu-id="d671f-106">Это можно продемонстрировать на примере класса `Person`, который содержит два свойства: `Name` (string) и `Age` (int).</span><span class="sxs-lookup"><span data-stu-id="d671f-106">This sample shows a `Person` class that has two properties: `Name` (string) and `Age` (int).</span></span> <span data-ttu-id="d671f-107">Для обоих свойств реализованы методы доступа `get` и `set`, благодаря чему они доступны и для чтения, и для записи.</span><span class="sxs-lookup"><span data-stu-id="d671f-107">Both properties provide `get` and `set` accessors, so they are considered read/write properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d671f-108">Пример</span><span class="sxs-lookup"><span data-stu-id="d671f-108">Example</span></span>  
 [!code-csharp[csProgGuideObjects#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#33)]  
  
## <a name="robust-programming"></a><span data-ttu-id="d671f-109">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="d671f-109">Robust Programming</span></span>  
 <span data-ttu-id="d671f-110">В предыдущем примере свойства `Name` и `Age` являются [открытыми](../../../csharp/language-reference/keywords/public.md) и содержат одновременно методы доступа `get` и `set`.</span><span class="sxs-lookup"><span data-stu-id="d671f-110">In the previous example, the `Name` and `Age` properties are [public](../../../csharp/language-reference/keywords/public.md) and include both a `get` and a `set` accessor.</span></span> <span data-ttu-id="d671f-111">Благодаря этому объект может считывать эти свойства и записывать их.</span><span class="sxs-lookup"><span data-stu-id="d671f-111">This allows any object to read and write these properties.</span></span> <span data-ttu-id="d671f-112">Тем не менее в некоторых случаях необходимо исключить один из методов доступа.</span><span class="sxs-lookup"><span data-stu-id="d671f-112">It is sometimes desirable, however, to exclude one of the accessors.</span></span> <span data-ttu-id="d671f-113">Например, свойство без метода доступа `set` будет доступно только для чтения:</span><span class="sxs-lookup"><span data-stu-id="d671f-113">Omitting the `set` accessor, for example, makes the property read-only:</span></span>  
  
 [!code-csharp[csProgGuideObjects#87](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#87)]  
  
 <span data-ttu-id="d671f-114">Кроме того, можно сделать один метод доступа открытым, а другой оставить частным или защищенным.</span><span class="sxs-lookup"><span data-stu-id="d671f-114">Alternatively, you can expose one accessor publicly but make the other private or protected.</span></span> <span data-ttu-id="d671f-115">Дополнительные сведения см. в разделе [Асимметричные методы доступа](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span><span class="sxs-lookup"><span data-stu-id="d671f-115">For more information, see [Asymmetric Accessor Accessibility](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span></span>  
  
 <span data-ttu-id="d671f-116">После объявления свойств их можно использовать так же, как поля класса.</span><span class="sxs-lookup"><span data-stu-id="d671f-116">Once the properties are declared, they can be used as if they were fields of the class.</span></span> <span data-ttu-id="d671f-117">Это позволяет получить естественный синтаксис извлечения и установки значения свойства, как показано на примере следующих операторов:</span><span class="sxs-lookup"><span data-stu-id="d671f-117">This allows for a very natural syntax when both getting and setting the value of a property, as in the following statements:</span></span>  
  
 [!code-csharp[csProgGuideObjects#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#35)]  
  
 <span data-ttu-id="d671f-118">Обратите внимание, что в методе `set` свойства доступна специальная переменная `value`.</span><span class="sxs-lookup"><span data-stu-id="d671f-118">Note that in a property `set` method a special `value` variable is available.</span></span> <span data-ttu-id="d671f-119">Она содержит значение, заданное пользователем, например:</span><span class="sxs-lookup"><span data-stu-id="d671f-119">This variable contains the value that the user specified, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#36)]  
  
 <span data-ttu-id="d671f-120">Обратите внимание на простой синтаксис приращения свойства `Age` для объекта `Person`:</span><span class="sxs-lookup"><span data-stu-id="d671f-120">Notice the clean syntax for incrementing the `Age` property on a `Person` object:</span></span>  
  
 [!code-csharp[csProgGuideObjects#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#37)]  
  
 <span data-ttu-id="d671f-121">Если для моделирования свойств использовать отдельные методы `set` и `get`, аналогичный код может иметь следующий вид:</span><span class="sxs-lookup"><span data-stu-id="d671f-121">If separate `set` and `get` methods were used to model properties, the equivalent code might look like this:</span></span>  
  
```csharp  
person.SetAge(person.GetAge() + 1);   
```  
  
 <span data-ttu-id="d671f-122">В этом примере переопределяется метод `ToString`:</span><span class="sxs-lookup"><span data-stu-id="d671f-122">The `ToString` method is overridden in this example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#38)]  
  
 <span data-ttu-id="d671f-123">Обратите внимание, что метод `ToString` не используется в этой программе явно.</span><span class="sxs-lookup"><span data-stu-id="d671f-123">Notice that `ToString` is not explicitly used in the program.</span></span> <span data-ttu-id="d671f-124">Он вызывается по умолчанию при вызове `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="d671f-124">It is invoked by default by the `WriteLine` calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d671f-125">См. также</span><span class="sxs-lookup"><span data-stu-id="d671f-125">See also</span></span>

- [<span data-ttu-id="d671f-126">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d671f-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="d671f-127">Свойства</span><span class="sxs-lookup"><span data-stu-id="d671f-127">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
- [<span data-ttu-id="d671f-128">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="d671f-128">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
