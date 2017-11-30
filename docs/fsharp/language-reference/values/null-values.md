---
title: "Значения NULL (F#)"
description: "Узнайте, как значение null используется в языке F #."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 68ebd261-51cf-4582-b2dc-44c84d1c2500
ms.openlocfilehash: 01c14de00eb5efd0952145ffc8aabe69d65a3a48
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="null-values"></a><span data-ttu-id="c475c-104">Значения NULL</span><span class="sxs-lookup"><span data-stu-id="c475c-104">Null Values</span></span>

<span data-ttu-id="c475c-105">В этом разделе описывается, как значение null используется в F #.</span><span class="sxs-lookup"><span data-stu-id="c475c-105">This topic describes how the null value is used in F#.</span></span>


## <a name="null-value"></a><span data-ttu-id="c475c-106">Значение NULL</span><span class="sxs-lookup"><span data-stu-id="c475c-106">Null Value</span></span>
<span data-ttu-id="c475c-107">Значение null не используется обычно в языке F # для значений или переменных.</span><span class="sxs-lookup"><span data-stu-id="c475c-107">The null value is not normally used in F# for values or variables.</span></span> <span data-ttu-id="c475c-108">Тем не менее null появляется в качестве ненормального значения в определенных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="c475c-108">However, null appears as an abnormal value in certain situations.</span></span> <span data-ttu-id="c475c-109">Если тип определен в языке F #, значение null не разрешаются как регулярным значением, пока [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) атрибут применяется к типу.</span><span class="sxs-lookup"><span data-stu-id="c475c-109">If a type is defined in F#, null is not permitted as a regular value unless the [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) attribute is applied to the type.</span></span> <span data-ttu-id="c475c-110">Если тип определен в какой-либо другой язык .NET, null является возможным значением, и при взаимодействии с такими типами код F # может столкнуться со значениями null.</span><span class="sxs-lookup"><span data-stu-id="c475c-110">If a type is defined in some other .NET language, null is a possible value, and when you are interoperating with such types, your F# code might encounter null values.</span></span>

<span data-ttu-id="c475c-111">Единственный способ создать значение null, непосредственно с помощью библиотеки F # для типа, определенные в языке F # и используются исключительно из F #, является использование [Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) или [Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2).</span><span class="sxs-lookup"><span data-stu-id="c475c-111">For a type defined in F# and used strictly from F#, the only way to create a null value using the F# library directly is to use [Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) or [Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2).</span></span> <span data-ttu-id="c475c-112">Однако для типа F #, используемого из других языков .NET или могут возникать при использовании API-интерфейсы, не записываются в языке F #, например .NET Framework данного типа значения null.</span><span class="sxs-lookup"><span data-stu-id="c475c-112">However, for an F# type that is used from other .NET languages, or if you are using that type with an API that is not written in F#, such as the .NET Framework, null values can occur.</span></span>

<span data-ttu-id="c475c-113">Можно использовать `option` типа в F # можно использовать ссылочные переменные с возможным значением null в другом языке .NET.</span><span class="sxs-lookup"><span data-stu-id="c475c-113">You can use the `option` type in F# when you might use a reference variable with a possible null value in another .NET language.</span></span> <span data-ttu-id="c475c-114">Вместо значения null, с помощью F # `option` типа, используйте значение параметра `None` , если объект отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c475c-114">Instead of null, with an F# `option` type, you use the option value `None` if there is no object.</span></span> <span data-ttu-id="c475c-115">Используйте значение параметра `Some(obj)` с объектом `obj` при отсутствии объекта.</span><span class="sxs-lookup"><span data-stu-id="c475c-115">You use the option value `Some(obj)` with an object `obj` when there is an object.</span></span> <span data-ttu-id="c475c-116">Дополнительные сведения см. в разделе [параметры](../options.md).</span><span class="sxs-lookup"><span data-stu-id="c475c-116">For more information, see [Options](../options.md).</span></span>

<span data-ttu-id="c475c-117">`null` Ключевое слово является допустимым ключевым словом в языке F #, и необходимо использовать при работе с API платформы .NET Framework или другие API, которые записываются на другом языке .NET.</span><span class="sxs-lookup"><span data-stu-id="c475c-117">The `null` keyword is a valid keyword in the F# language, and you have to use it when you are working with .NET Framework APIs or other APIs that are written in another .NET language.</span></span> <span data-ttu-id="c475c-118">Две ситуации, в которых может понадобиться значение null: при вызове .NET API и передайте значение null в качестве аргумента, и при интерпретации возвращаемого значения или выходного параметра из вызова метода .NET.</span><span class="sxs-lookup"><span data-stu-id="c475c-118">The two situations in which you might need a null value are when you call a .NET API and pass a null value as an argument, and when you interpret the return value or an output parameter from a .NET method call.</span></span>

<span data-ttu-id="c475c-119">Чтобы передать значение null в метод .NET, просто используйте `null` ключевое слово в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="c475c-119">To pass a null value to a .NET method, just use the `null` keyword in the calling code.</span></span> <span data-ttu-id="c475c-120">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="c475c-120">The following code example illustrates this.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

<span data-ttu-id="c475c-121">Для интерпретации значения null, полученного от метода .NET, используйте сопоставление шаблонов, если это возможно.</span><span class="sxs-lookup"><span data-stu-id="c475c-121">To interpret a null value that is obtained from a .NET method, use pattern matching if you can.</span></span> <span data-ttu-id="c475c-122">В следующем примере кода показано, как использовать сопоставление шаблонов для интерпретации значения null, возвращаемые из `ReadLine` при попытке чтения за концом входной поток.</span><span class="sxs-lookup"><span data-stu-id="c475c-122">The following code example shows how to use pattern matching to interpret the null value that is returned from `ReadLine` when it tries to read past the end of an input stream.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

<span data-ttu-id="c475c-123">Значения NULL для типов F # также может возникать в других целях, например при использовании `Array.zeroCreate`, который вызывает `Unchecked.defaultof`.</span><span class="sxs-lookup"><span data-stu-id="c475c-123">Null values for F# types can also be generated in other ways, such as when you use `Array.zeroCreate`, which calls `Unchecked.defaultof`.</span></span> <span data-ttu-id="c475c-124">Будьте внимательны с такой код, чтобы сохранить значения null, содержащийся.</span><span class="sxs-lookup"><span data-stu-id="c475c-124">You must be careful with such code to keep the null values encapsulated.</span></span> <span data-ttu-id="c475c-125">В библиотеке, предназначенная только для F # проверку наличия значений null в каждой функции, не нужно.</span><span class="sxs-lookup"><span data-stu-id="c475c-125">In a library intended only for F#, you do not have to check for null values in every function.</span></span> <span data-ttu-id="c475c-126">При создании библиотеки для взаимодействия с другими языками .NET, может потребоваться добавить входные параметры проверки на значение null и исключение `ArgumentNullException`, так же как и в коде C# или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c475c-126">If you are writing a library for interoperation with other .NET languages, you might have to add checks for null input parameters and throw an `ArgumentNullException`, just as you do in C# or Visual Basic code.</span></span>

<span data-ttu-id="c475c-127">Можно использовать следующий код для проверки, если произвольное значение null.</span><span class="sxs-lookup"><span data-stu-id="c475c-127">You can use the following code to check if an arbitrary value is null.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a><span data-ttu-id="c475c-128">См. также</span><span class="sxs-lookup"><span data-stu-id="c475c-128">See Also</span></span>
[<span data-ttu-id="c475c-129">Значения</span><span class="sxs-lookup"><span data-stu-id="c475c-129">Values</span></span>](index.md)

[<span data-ttu-id="c475c-130">Выражения match</span><span class="sxs-lookup"><span data-stu-id="c475c-130">Match Expressions</span></span>](../match-expressions.md)
