---
title: Перегрузки операторов
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
ms.openlocfilehash: 0999e94c8d77396b237522e89c51206ce1226718
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401223"
---
# <a name="operator-overloads"></a><span data-ttu-id="1ecbb-102">Перегрузки операторов</span><span class="sxs-lookup"><span data-stu-id="1ecbb-102">Operator Overloads</span></span>
<span data-ttu-id="1ecbb-103">Перегрузки оператора позволяют типам фреймворков отображаться так, как если бы они были встроенными примитивами языка.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-103">Operator overloads allow framework types to appear as if they were built-in language primitives.</span></span>

 <span data-ttu-id="1ecbb-104">Хотя это допустимо и полезно в некоторых ситуациях, оператор перегрузки должны использоваться осторожно.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-104">Although allowed and useful in some situations, operator overloads should be used cautiously.</span></span> <span data-ttu-id="1ecbb-105">Есть много случаев, когда перегрузка оператора была злоупотреблять, например, когда конструкторы фреймворков начали использовать операторов для операций, которые должны быть простыми методами.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-105">There are many cases in which operator overloading has been abused, such as when framework designers started to use operators for operations that should be simple methods.</span></span> <span data-ttu-id="1ecbb-106">Следующие рекомендации должны помочь вам решить, когда и как использовать перегрузку оператора.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-106">The following guidelines should help you decide when and how to use operator overloading.</span></span>

 <span data-ttu-id="1ecbb-107">❌AVOID определяет перегрузки оператора, за исключением типов, которые должны чувствовать себя примитивными (встроенными) типами.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-107">❌ AVOID defining operator overloads, except in types that should feel like primitive (built-in) types.</span></span>

 <span data-ttu-id="1ecbb-108">✔️ CONSIDER, определяющий перегрузки оператора в типе, который должен чувствовать себя примитивным типом.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-108">✔️ CONSIDER defining operator overloads in a type that should feel like a primitive type.</span></span>

 <span data-ttu-id="1ecbb-109">Например, <xref:System.String?displayProperty=nameWithType> `operator==` имеет `operator!=` и определяется.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-109">For example, <xref:System.String?displayProperty=nameWithType> has `operator==` and `operator!=` defined.</span></span>

 <span data-ttu-id="1ecbb-110">✔️ DO определяют перегрузки оператора в структурках, представляющих числа <xref:System.Decimal?displayProperty=nameWithType>(например,).</span><span class="sxs-lookup"><span data-stu-id="1ecbb-110">✔️ DO define operator overloads in structs that represent numbers (such as <xref:System.Decimal?displayProperty=nameWithType>).</span></span>

 <span data-ttu-id="1ecbb-111">❌НЕ быть милопри определяя перегрузки оператора.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-111">❌ DO NOT be cute when defining operator overloads.</span></span>

 <span data-ttu-id="1ecbb-112">Перегрузка оператора полезна в тех случаях, когда сразу становится ясно, каким будет результат операции.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-112">Operator overloading is useful in cases in which it is immediately obvious what the result of the operation will be.</span></span> <span data-ttu-id="1ecbb-113">Например, имеет смысл, чтобы иметь <xref:System.DateTime> возможность `DateTime` вычесть <xref:System.TimeSpan>один из другого и получить .</span><span class="sxs-lookup"><span data-stu-id="1ecbb-113">For example, it makes sense to be able to subtract one <xref:System.DateTime> from another `DateTime` and get a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="1ecbb-114">Однако нецелесообразно использовать оператора логического союза для объединения двух запросов базы данных или для записи оператора смены в поток.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-114">However, it is not appropriate to use the logical union operator to union two database queries, or to use the shift operator to write to a stream.</span></span>

 <span data-ttu-id="1ecbb-115">❌НЕ предоставляйте оператору перегрузки, если по крайней мере один из operands не имеет типа, определяющего перегрузку.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-115">❌ DO NOT provide operator overloads unless at least one of the operands is of the type defining the overload.</span></span>

 <span data-ttu-id="1ecbb-116">✔️ перегрузки операторов симметричным образом.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-116">✔️ DO overload operators in a symmetric fashion.</span></span>

 <span data-ttu-id="1ecbb-117">Например, если вы `operator==`перегружаете, `operator!=`вы также должны перегрузить .</span><span class="sxs-lookup"><span data-stu-id="1ecbb-117">For example, if you overload the `operator==`, you should also overload the `operator!=`.</span></span> <span data-ttu-id="1ecbb-118">Аналогичным образом, если `operator<`вы перегружаете `operator>`, вы также должны перегрузить , и так далее.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-118">Similarly, if you overload the `operator<`, you should also overload the `operator>`, and so on.</span></span>

 <span data-ttu-id="1ecbb-119">✔️ CONSIDER предоставляет методы с дружественными именами, которые соответствуют каждому перегруженного оператора.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-119">✔️ CONSIDER providing methods with friendly names that correspond to each overloaded operator.</span></span>

 <span data-ttu-id="1ecbb-120">Многие языки не поддерживают перегрузку оператора.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-120">Many languages do not support operator overloading.</span></span> <span data-ttu-id="1ecbb-121">По этой причине рекомендуется, чтобы типы, перегружающие операторов, включали вторичный метод с соответствующим доменным именем, обеспечивающим эквивалентную функциональность.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-121">For this reason, it is recommended that types that overload operators include a secondary method with an appropriate domain-specific name that provides equivalent functionality.</span></span>

 <span data-ttu-id="1ecbb-122">Следующая таблица содержит список операторов и соответствующие имена дружественных методов.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-122">The following table contains a list of operators and the corresponding friendly method names.</span></span>

|<span data-ttu-id="1ecbb-123">Символ оператора СЗ</span><span class="sxs-lookup"><span data-stu-id="1ecbb-123">C# Operator Symbol</span></span>|<span data-ttu-id="1ecbb-124">Имя метаданных</span><span class="sxs-lookup"><span data-stu-id="1ecbb-124">Metadata Name</span></span>|<span data-ttu-id="1ecbb-125">Понятное имя</span><span class="sxs-lookup"><span data-stu-id="1ecbb-125">Friendly Name</span></span>|
|-------------------------|-------------------|-------------------|
|`N/A`|`op_Implicit`|`To<TypeName>/From<TypeName>`|
|`N/A`|`op_Explicit`|`To<TypeName>/From<TypeName>`|
|`+ (binary)`|`op_Addition`|`Add`|
|`- (binary)`|`op_Subtraction`|`Subtract`|
|`* (binary)`|`op_Multiply`|`Multiply`|
|`/`|`op_Division`|`Divide`|
|`%`|`op_Modulus`|`Mod or Remainder`|
|`^`|`op_ExclusiveOr`|`Xor`|
|`& (binary)`|`op_BitwiseAnd`|`BitwiseAnd`|
|<code>&#124;</code>|`op_BitwiseOr`|`BitwiseOr`|
|`&&`|`op_LogicalAnd`|`And`|
|<code>&#124;&#124;</code>|`op_LogicalOr`|`Or`|
|`=`|`op_Assign`|`Assign`|
|`<<`|`op_LeftShift`|`LeftShift`|
|`>>`|`op_RightShift`|`RightShift`|
|`N/A`|`op_SignedRightShift`|`SignedRightShift`|
|`N/A`|`op_UnsignedRightShift`|`UnsignedRightShift`|
|`==`|`op_Equality`|`Equals`|
|`!=`|`op_Inequality`|`Equals`|
|`>`|`op_GreaterThan`|`CompareTo`|
|`<`|`op_LessThan`|`CompareTo`|
|`>=`|`op_GreaterThanOrEqual`|`CompareTo`|
|`<=`|`op_LessThanOrEqual`|`CompareTo`|
|`*=`|`op_MultiplicationAssignment`|`Multiply`|
|`-=`|`op_SubtractionAssignment`|`Subtract`|
|`^=`|`op_ExclusiveOrAssignment`|`Xor`|
|`<<=`|`op_LeftShiftAssignment`|`LeftShift`|
|`%=`|`op_ModulusAssignment`|`Mod`|
|`+=`|`op_AdditionAssignment`|`Add`|
|`&=`|`op_BitwiseAndAssignment`|`BitwiseAnd`|
|<code>&#124;=</code>|`op_BitwiseOrAssignment`|`BitwiseOr`|
|`,`|`op_Comma`|`Comma`|
|`/=`|`op_DivisionAssignment`|`Divide`|
|`--`|`op_Decrement`|`Decrement`|
|`++`|`op_Increment`|`Increment`|
|`- (unary)`|`op_UnaryNegation`|`Negate`|
|`+ (unary)`|`op_UnaryPlus`|`Plus`|
|`~`|`op_OnesComplement`|`OnesComplement`|

### <a name="overloading-operator-"></a><span data-ttu-id="1ecbb-126">Оператор перегрузки</span><span class="sxs-lookup"><span data-stu-id="1ecbb-126">Overloading Operator ==</span></span>
 <span data-ttu-id="1ecbb-127">Перегрузка `operator ==` довольно сложна.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-127">Overloading `operator ==` is quite complicated.</span></span> <span data-ttu-id="1ecbb-128">Семантика оператора должна быть совместима с несколькими <xref:System.Object.Equals%2A?displayProperty=nameWithType>другими участниками, такими как .</span><span class="sxs-lookup"><span data-stu-id="1ecbb-128">The semantics of the operator need to be compatible with several other members, such as <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span></span>

### <a name="conversion-operators"></a><span data-ttu-id="1ecbb-129">Операторы преобразования</span><span class="sxs-lookup"><span data-stu-id="1ecbb-129">Conversion Operators</span></span>
 <span data-ttu-id="1ecbb-130">Операторы конверсии являются неопроизвонелыми операторами, которые позволяют конверсировать из одного типа в другой.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-130">Conversion operators are unary operators that allow conversion from one type to another.</span></span> <span data-ttu-id="1ecbb-131">Операторы должны быть определены как статические члены либо на операнде, либо на типе возврата.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-131">The operators must be defined as static members on either the operand or the return type.</span></span> <span data-ttu-id="1ecbb-132">Существует два типа операторов конверсий: неявный и явный.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-132">There are two types of conversion operators: implicit and explicit.</span></span>

 <span data-ttu-id="1ecbb-133">❌НЕ предоставляйте оператора конверсии, если такое преобразование явно не ожидается конечными пользователями.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-133">❌ DO NOT provide a conversion operator if such conversion is not clearly expected by the end users.</span></span>

 <span data-ttu-id="1ecbb-134">❌НЕ определяйте операторов конверсии за пределами домена типа.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-134">❌ DO NOT define conversion operators outside of a type’s domain.</span></span>

 <span data-ttu-id="1ecbb-135">Например, <xref:System.Int32> <xref:System.Double>, <xref:System.Decimal> и все численные типы, в то время как <xref:System.DateTime> нет.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-135">For example, <xref:System.Int32>, <xref:System.Double>, and <xref:System.Decimal> are all numeric types, whereas <xref:System.DateTime> is not.</span></span> <span data-ttu-id="1ecbb-136">Таким образом, не должно быть `Double(long)` оператора `DateTime`преобразования для преобразования в .</span><span class="sxs-lookup"><span data-stu-id="1ecbb-136">Therefore, there should be no conversion operator to convert a `Double(long)` to a `DateTime`.</span></span> <span data-ttu-id="1ecbb-137">В таком случае предпочтительнее конструктор.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-137">A constructor is preferred in such a case.</span></span>

 <span data-ttu-id="1ecbb-138">❌НЕ предоставляйте оператора неявного преобразования, если преобразование потенциально убыточно.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-138">❌ DO NOT provide an implicit conversion operator if the conversion is potentially lossy.</span></span>

 <span data-ttu-id="1ecbb-139">Например, не должно быть неявного преобразования от `Double` к потому, `Int32` что `Double` имеет более широкий диапазон, чем `Int32`.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-139">For example, there should not be an implicit conversion from `Double` to `Int32` because `Double` has a wider range than `Int32`.</span></span> <span data-ttu-id="1ecbb-140">Оператор явного преобразования может быть предоставлен, даже если конверсия потенциально убыточна.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-140">An explicit conversion operator can be provided even if the conversion is potentially lossy.</span></span>

 <span data-ttu-id="1ecbb-141">❌НЕ выбрасывайте исключения из неявных слепков.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-141">❌ DO NOT throw exceptions from implicit casts.</span></span>

 <span data-ttu-id="1ecbb-142">Конечным пользователям очень трудно понять, что происходит, потому что они могут не знать, что происходит преобразование.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-142">It is very difficult for end users to understand what is happening, because they might not be aware that a conversion is taking place.</span></span>

 <span data-ttu-id="1ecbb-143">✔️ DO <xref:System.InvalidCastException?displayProperty=nameWithType> throw, если вызов литой оператора приводит к убыточной конверсии и договор оператора не позволяет убыточные преобразования.</span><span class="sxs-lookup"><span data-stu-id="1ecbb-143">✔️ DO throw <xref:System.InvalidCastException?displayProperty=nameWithType> if a call to a cast operator results in a lossy conversion and the contract of the operator does not allow lossy conversions.</span></span>

 <span data-ttu-id="1ecbb-144">*Порции © 2005, 2009 Microsoft Corporation. Все права зарезервированы.*</span><span class="sxs-lookup"><span data-stu-id="1ecbb-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="1ecbb-145">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="1ecbb-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="1ecbb-146">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1ecbb-146">See also</span></span>

- [<span data-ttu-id="1ecbb-147">Правила разработки членов</span><span class="sxs-lookup"><span data-stu-id="1ecbb-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="1ecbb-148">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="1ecbb-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
