---
title: "Практическое руководство. Объявление и использование свойств чтения и записи (руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- get accessor [C#], declaring properties
- set accessor [C#]
- properties [C#], declaring
- read/write properties [C#]
- accessors [C#], declaring properties with
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e5e4ca1feff203dc2ab88c0d1dfae8098508fec7
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-declare-and-use-read-write-properties-c-programming-guide"></a><span data-ttu-id="f2bc9-102">Практическое руководство. Объявление и использование свойств чтения и записи (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="f2bc9-102">How to: Declare and Use Read Write Properties (C# Programming Guide)</span></span>
<span data-ttu-id="f2bc9-103">Свойства имеют все преимущества открытых членов данных, но не связаны с рисками незащищенного, неконтролируемого и несанкционированного доступа к данным объекта.</span><span class="sxs-lookup"><span data-stu-id="f2bc9-103">Properties provide the convenience of public data members without the risks that come with unprotected, uncontrolled, and unverified access to an object's data.</span></span> <span data-ttu-id="f2bc9-104">Это достигается благодаря применению *методов доступа*, которые представляют собой особые методы для присвоения и извлечения значений базового члена данных.</span><span class="sxs-lookup"><span data-stu-id="f2bc9-104">This is accomplished through *accessors*: special methods that assign and retrieve values from the underlying data member.</span></span> <span data-ttu-id="f2bc9-105">Метод доступа [set](../../../csharp/language-reference/keywords/set.md) присваивает значения членам данных, а метод доступа [get](../../../csharp/language-reference/keywords/get.md) извлекает их.</span><span class="sxs-lookup"><span data-stu-id="f2bc9-105">The [set](../../../csharp/language-reference/keywords/set.md) accessor enables data members to be assigned, and the [get](../../../csharp/language-reference/keywords/get.md) accessor retrieves data member values.</span></span>  
  
 <span data-ttu-id="f2bc9-106">Это можно продемонстрировать на примере класса `Person`, который содержит два свойства: `Name` (string) и `Age` (int).</span><span class="sxs-lookup"><span data-stu-id="f2bc9-106">This sample shows a `Person` class that has two properties: `Name` (string) and `Age` (int).</span></span> <span data-ttu-id="f2bc9-107">Для обоих свойств реализованы методы доступа `get` и `set`, благодаря чему они доступны и для чтения, и для записи.</span><span class="sxs-lookup"><span data-stu-id="f2bc9-107">Both properties provide `get` and `set` accessors, so they are considered read/write properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2bc9-108">Пример</span><span class="sxs-lookup"><span data-stu-id="f2bc9-108">Example</span></span>  
 <span data-ttu-id="f2bc9-109">[!code-cs[csProgGuideObjects#33](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f2bc9-109">[!code-cs[csProgGuideObjects#33](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_1.cs)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f2bc9-110">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="f2bc9-110">Robust Programming</span></span>  
 <span data-ttu-id="f2bc9-111">В предыдущем примере свойства `Name` и `Age` являются [открытыми](../../../csharp/language-reference/keywords/public.md) и содержат одновременно методы доступа `get` и `set`.</span><span class="sxs-lookup"><span data-stu-id="f2bc9-111">In the previous example, the `Name` and `Age` properties are [public](../../../csharp/language-reference/keywords/public.md) and include both a `get` and a `set` accessor.</span></span> <span data-ttu-id="f2bc9-112">Благодаря этому объект может считывать эти свойства и записывать их.</span><span class="sxs-lookup"><span data-stu-id="f2bc9-112">This allows any object to read and write these properties.</span></span> <span data-ttu-id="f2bc9-113">Тем не менее в некоторых случаях необходимо исключить один из методов доступа.</span><span class="sxs-lookup"><span data-stu-id="f2bc9-113">It is sometimes desirable, however, to exclude one of the accessors.</span></span> <span data-ttu-id="f2bc9-114">Например, свойство без метода доступа `set` будет доступно только для чтения:</span><span class="sxs-lookup"><span data-stu-id="f2bc9-114">Omitting the `set` accessor, for example, makes the property read-only:</span></span>  
  
 <span data-ttu-id="f2bc9-115">[!code-cs[csProgGuideObjects#87](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f2bc9-115">[!code-cs[csProgGuideObjects#87](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_2.cs)]</span></span>  
  
 <span data-ttu-id="f2bc9-116">Кроме того, можно сделать один метод доступа открытым, а другой оставить частным или защищенным.</span><span class="sxs-lookup"><span data-stu-id="f2bc9-116">Alternatively, you can expose one accessor publicly but make the other private or protected.</span></span> <span data-ttu-id="f2bc9-117">Дополнительные сведения см. в разделе [Асимметричные методы доступа](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span><span class="sxs-lookup"><span data-stu-id="f2bc9-117">For more information, see [Asymmetric Accessor Accessibility](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span></span>  
  
 <span data-ttu-id="f2bc9-118">После объявления свойств их можно использовать так же, как поля класса.</span><span class="sxs-lookup"><span data-stu-id="f2bc9-118">Once the properties are declared, they can be used as if they were fields of the class.</span></span> <span data-ttu-id="f2bc9-119">Это позволяет получить естественный синтаксис извлечения и установки значения свойства, как показано на примере следующих операторов:</span><span class="sxs-lookup"><span data-stu-id="f2bc9-119">This allows for a very natural syntax when both getting and setting the value of a property, as in the following statements:</span></span>  
  
 <span data-ttu-id="f2bc9-120">[!code-cs[csProgGuideObjects#35](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="f2bc9-120">[!code-cs[csProgGuideObjects#35](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_3.cs)]</span></span>  
  
 <span data-ttu-id="f2bc9-121">Обратите внимание, что в методе `set` свойства доступна специальная переменная `value`.</span><span class="sxs-lookup"><span data-stu-id="f2bc9-121">Note that in a property `set` method a special `value` variable is available.</span></span> <span data-ttu-id="f2bc9-122">Она содержит значение, заданное пользователем, например:</span><span class="sxs-lookup"><span data-stu-id="f2bc9-122">This variable contains the value that the user specified, for example:</span></span>  
  
 <span data-ttu-id="f2bc9-123">[!code-cs[csProgGuideObjects#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="f2bc9-123">[!code-cs[csProgGuideObjects#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_4.cs)]</span></span>  
  
 <span data-ttu-id="f2bc9-124">Обратите внимание на простой синтаксис приращения свойства `Age` для объекта `Person`:</span><span class="sxs-lookup"><span data-stu-id="f2bc9-124">Notice the clean syntax for incrementing the `Age` property on a `Person` object:</span></span>  
  
 <span data-ttu-id="f2bc9-125">[!code-cs[csProgGuideObjects#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="f2bc9-125">[!code-cs[csProgGuideObjects#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_5.cs)]</span></span>  
  
 <span data-ttu-id="f2bc9-126">Если для моделирования свойств использовать отдельные методы `set` и `get`, аналогичный код может иметь следующий вид:</span><span class="sxs-lookup"><span data-stu-id="f2bc9-126">If separate `set` and `get` methods were used to model properties, the equivalent code might look like this:</span></span>  
  
```  
person.SetAge(person.GetAge() + 1);   
```  
  
 <span data-ttu-id="f2bc9-127">В этом примере переопределяется метод `ToString`:</span><span class="sxs-lookup"><span data-stu-id="f2bc9-127">The `ToString` method is overridden in this example:</span></span>  
  
 <span data-ttu-id="f2bc9-128">[!code-cs[csProgGuideObjects#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="f2bc9-128">[!code-cs[csProgGuideObjects#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_6.cs)]</span></span>  
  
 <span data-ttu-id="f2bc9-129">Обратите внимание, что метод `ToString` не используется в этой программе явно.</span><span class="sxs-lookup"><span data-stu-id="f2bc9-129">Notice that `ToString` is not explicitly used in the program.</span></span> <span data-ttu-id="f2bc9-130">Он вызывается по умолчанию при вызове `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="f2bc9-130">It is invoked by default by the `WriteLine` calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2bc9-131">См. также</span><span class="sxs-lookup"><span data-stu-id="f2bc9-131">See Also</span></span>  
 <span data-ttu-id="f2bc9-132">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f2bc9-132">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f2bc9-133">[Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md) </span><span class="sxs-lookup"><span data-stu-id="f2bc9-133">[Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) </span></span>  
 [<span data-ttu-id="f2bc9-134">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="f2bc9-134">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)

