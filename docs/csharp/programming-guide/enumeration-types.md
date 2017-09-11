---
title: "Типы перечислений (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- enumerations [C#]
- enums [C#]
- C# Language, enums
- bit flags [C#]
ms.assetid: 64a9b731-9e3c-4336-8a09-018db2aa10b7
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 677de7c6e0c0f72b600ce8ee5a8bad265725f6d3
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="enumeration-types-c-programming-guide"></a><span data-ttu-id="5fee0-102">Типы перечислений (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="5fee0-102">Enumeration Types (C# Programming Guide)</span></span>
<span data-ttu-id="5fee0-103">Тип перечисления (называемый также перечислением) предоставляет эффективный способ определения набора именованных целочисленных констант, который можно назначить переменной.</span><span class="sxs-lookup"><span data-stu-id="5fee0-103">An enumeration type (also named an enumeration or an enum) provides an efficient way to define a set of named integral constants that may be assigned to a variable.</span></span> <span data-ttu-id="5fee0-104">Например, предположим, что нужно определить переменную, значение которого должно представлять день недели.</span><span class="sxs-lookup"><span data-stu-id="5fee0-104">For example, assume that you have to define a variable whose value will represent a day of the week.</span></span> <span data-ttu-id="5fee0-105">Имеется только семь имеющих смысл значений, которые может принимать переменная.</span><span class="sxs-lookup"><span data-stu-id="5fee0-105">There are only seven meaningful values which that variable will ever store.</span></span> <span data-ttu-id="5fee0-106">Для определения этих значений можно использовать тип перечисления, который объявлен с помощью ключевого слова [enum](../../csharp/language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="5fee0-106">To define those values, you can use an enumeration type, which is declared by using the [enum](../../csharp/language-reference/keywords/enum.md) keyword.</span></span>  
  
 <span data-ttu-id="5fee0-107">[!code-cs[csProgGuideEnums#1](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5fee0-107">[!code-cs[csProgGuideEnums#1](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_1.cs)]</span></span>  
  
 <span data-ttu-id="5fee0-108">По умолчанию базовым типом каждого элемента перечисления является [int](../../csharp/language-reference/keywords/int.md).</span><span class="sxs-lookup"><span data-stu-id="5fee0-108">By default the underlying type of each element in the enum is [int](../../csharp/language-reference/keywords/int.md).</span></span> <span data-ttu-id="5fee0-109">Можно задать другой целочисленный тип, используя двоеточие, как показано в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="5fee0-109">You can specify another integral numeric type by using a colon, as shown in the previous example.</span></span> <span data-ttu-id="5fee0-110">Полный список возможных типов см. в разделе [enum (справочник по C#)](../../csharp/language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="5fee0-110">For a full list of possible types, see [enum (C# Reference)](../../csharp/language-reference/keywords/enum.md).</span></span>  
  
 <span data-ttu-id="5fee0-111">Чтобы проверить основные числовые значения путем приведения в базовый тип, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5fee0-111">You can verify the underlying numeric values by casting  to the underlying type, as the following example shows.</span></span>  
  
```csharp  
Days today = Days.Monday;  
int dayNumber =(int)today;  
Console.WriteLine("{0} is day number #{1}.", today, dayNumber);  
  
Months thisMonth = Months.Dec;  
byte monthNumber = (byte)thisMonth;  
Console.WriteLine("{0} is month number #{1}.", thisMonth, monthNumber);  
  
// Output:  
// Monday is day number #1.  
// Dec is month number #11.  
```  
  
 <span data-ttu-id="5fee0-112">Далее указаны преимущества использования enum вместо числового типа.</span><span class="sxs-lookup"><span data-stu-id="5fee0-112">The following are advantages of using an enum instead of a numeric type:</span></span>  
  
-   <span data-ttu-id="5fee0-113">Для клиентского кода ясно задается, какие значения допустимы для переменной.</span><span class="sxs-lookup"><span data-stu-id="5fee0-113">You clearly specify for client code which values are valid for the variable.</span></span>  
  
-   <span data-ttu-id="5fee0-114">В [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] IntelliSense выводит список определенных значений.</span><span class="sxs-lookup"><span data-stu-id="5fee0-114">In [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], IntelliSense lists the defined values.</span></span>  
  
 <span data-ttu-id="5fee0-115">Если не указать значения этих элементов в списке перечислителя, значения будут автоматически увеличиваться на 1.</span><span class="sxs-lookup"><span data-stu-id="5fee0-115">When you do not specify values for the elements in the enumerator list, the values are automatically incremented by 1.</span></span> <span data-ttu-id="5fee0-116">В предыдущем примере `Days.Sunday` имеет значение 0, `Days.Monday` имеет значение 1 и т. д.</span><span class="sxs-lookup"><span data-stu-id="5fee0-116">In the previous example, `Days.Sunday` has a value of 0, `Days.Monday` has a value of 1, and so on.</span></span> <span data-ttu-id="5fee0-117">Когда создается новый объект `Days`, он будет иметь значение по умолчанию `Days.Sunday` (0), только ему явно не присвоить значение.</span><span class="sxs-lookup"><span data-stu-id="5fee0-117">When you create a new `Days` object, it will have a default value of `Days.Sunday` (0) if you do not explicitly assign it a value.</span></span> <span data-ttu-id="5fee0-118">При создании перечисления выберите наиболее логичное используемое по умолчанию значение и присвойте ему значение нуль.</span><span class="sxs-lookup"><span data-stu-id="5fee0-118">When you create an enum, select the most logical default value and give it a value of zero.</span></span> <span data-ttu-id="5fee0-119">В результате этого все перечисления, если при их создании им явно не задать значение, будут иметь по умолчанию это значение.</span><span class="sxs-lookup"><span data-stu-id="5fee0-119">That will cause all enums to have that default value if they are not explicitly assigned a value when they are created.</span></span>  
  
 <span data-ttu-id="5fee0-120">Если переменная `meetingDay` имеет тип `Days`, ей можно (без явного приведения) присвоить только одно из значений, определенных в `Days`.</span><span class="sxs-lookup"><span data-stu-id="5fee0-120">If the variable `meetingDay` is of type `Days`, then (without an explicit cast) you can only assign it one of the values defined by `Days`.</span></span> <span data-ttu-id="5fee0-121">И если день встречи изменяется, можно назначить новое значение из `Days` переменной `meetingDay`:</span><span class="sxs-lookup"><span data-stu-id="5fee0-121">And if the meeting day changes, you can assign a new value from `Days` to `meetingDay`:</span></span>  
  
 <span data-ttu-id="5fee0-122">[!code-cs[csProgGuideEnums#4](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="5fee0-122">[!code-cs[csProgGuideEnums#4](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_2.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5fee0-123">Переменной `meetingDay` можно присвоить любое произвольное целое значение.</span><span class="sxs-lookup"><span data-stu-id="5fee0-123">It is possible to assign any arbitrary integer value to `meetingDay`.</span></span> <span data-ttu-id="5fee0-124">Например, эта строка кода не создает ошибку: `meetingDay = (Days) 42`.</span><span class="sxs-lookup"><span data-stu-id="5fee0-124">For example, this line of code does not produce an error: `meetingDay = (Days) 42`.</span></span> <span data-ttu-id="5fee0-125">Но этого делать нельзя, поскольку неявно ожидается, что переменная перечисления принимает одно из значений, определяемых перечислением.</span><span class="sxs-lookup"><span data-stu-id="5fee0-125">However, you should not do this because the implicit expectation is that an enum variable will only hold one of the values defined by the enum.</span></span> <span data-ttu-id="5fee0-126">Присвоение переменной типа перечисления произвольного значения связано с большим риском возникновения ошибок.</span><span class="sxs-lookup"><span data-stu-id="5fee0-126">To assign an arbitrary value to a variable of an enumeration type is to introduce a high risk for errors.</span></span>  
  
 <span data-ttu-id="5fee0-127">Элементам списка перечислителя типа перечисления можно присвоить любые значения, и можно также использовать вычисленные значения:</span><span class="sxs-lookup"><span data-stu-id="5fee0-127">You can assign any values to the elements in the enumerator list of an enumeration type, and you can also use computed values:</span></span>  
  
 <span data-ttu-id="5fee0-128">[!code-cs[csProgGuideEnums#3](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="5fee0-128">[!code-cs[csProgGuideEnums#3](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_3.cs)]</span></span>  
  
## <a name="enumeration-types-as-bit-flags"></a><span data-ttu-id="5fee0-129">Типы перечислений как битовые флаги</span><span class="sxs-lookup"><span data-stu-id="5fee0-129">Enumeration Types as Bit Flags</span></span>  
 <span data-ttu-id="5fee0-130">Тип перечисления можно использовать для определения битовых флагов, благодаря чему экземпляр типа перечисления может хранить любую комбинацию значений, определенных в списке перечислителя.</span><span class="sxs-lookup"><span data-stu-id="5fee0-130">You can use an enumeration type to define bit flags, which enables an instance of the enumeration type to store any combination of the values that are defined in the enumerator list.</span></span> <span data-ttu-id="5fee0-131">(Конечно, некоторые комбинации могут не иметь смысла или быть недопустимы в коде программы.)</span><span class="sxs-lookup"><span data-stu-id="5fee0-131">(Of course, some combinations may not be meaningful or allowed in your program code.)</span></span>  
  
 <span data-ttu-id="5fee0-132">Чтобы создать перечисление битовых флагов, нужно применить атрибут <xref:System.FlagsAttribute?displayProperty=fullName> и определить значения так, чтобы для них могли выполняться битовые операции `AND`, `OR`, `NOT` и `XOR`.</span><span class="sxs-lookup"><span data-stu-id="5fee0-132">You create a bit flags enum by applying the <xref:System.FlagsAttribute?displayProperty=fullName> attribute and defining the values appropriately so that `AND`, `OR`, `NOT` and `XOR` bitwise operations can be performed on them.</span></span> <span data-ttu-id="5fee0-133">В перечисление битовых флагов включите именованную константу с нулевым значением, что означает "флаги не установлены".</span><span class="sxs-lookup"><span data-stu-id="5fee0-133">In a bit flags enum, include a named constant with a value of zero that means "no flags are set."</span></span> <span data-ttu-id="5fee0-134">Не придавайте флагу нулевое значение, если оно не означает "флаги не установлены".</span><span class="sxs-lookup"><span data-stu-id="5fee0-134">Do not give a flag a value of zero if it does not mean "no flags are set".</span></span>  
  
 <span data-ttu-id="5fee0-135">В следующем примере определена другая версия перечисления `Days`, которая называется `Days2`.</span><span class="sxs-lookup"><span data-stu-id="5fee0-135">In the following example, another version of the `Days` enum, which is named `Days2`, is defined.</span></span> <span data-ttu-id="5fee0-136">У `Days2` имеется атрибут `Flags`, и каждому значению присваивается следующая степень числа 2.</span><span class="sxs-lookup"><span data-stu-id="5fee0-136">`Days2` has the `Flags` attribute and each value is assigned the next greater power of 2.</span></span> <span data-ttu-id="5fee0-137">Это позволяет создать переменную `Days2` со значением `Days2.Tuesday` и `Days2.Thursday`.</span><span class="sxs-lookup"><span data-stu-id="5fee0-137">This enables you to create a `Days2` variable whose value is `Days2.Tuesday` and `Days2.Thursday`.</span></span>  
  
 <span data-ttu-id="5fee0-138">[!code-cs[csProgGuideEnums#2](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="5fee0-138">[!code-cs[csProgGuideEnums#2](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_4.cs)]</span></span>  
  
 <span data-ttu-id="5fee0-139">Чтобы установить флаг на перечислении, используйте побитовый оператор `OR`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="5fee0-139">To set a flag on an enum, use the bitwise `OR` operator as shown in the following example:</span></span>  
  
 <span data-ttu-id="5fee0-140">[!code-cs[csProgGuideEnums#6](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="5fee0-140">[!code-cs[csProgGuideEnums#6](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_5.cs)]</span></span>  
  
 <span data-ttu-id="5fee0-141">Чтобы определить, установлен ли конкретный флаг, используйте побитовый оператор `AND`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="5fee0-141">To determine whether a specific flag is set, use a bitwise `AND` operation, as shown in the following example:</span></span>  
  
 <span data-ttu-id="5fee0-142">[!code-cs[csProgGuideEnums#7](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="5fee0-142">[!code-cs[csProgGuideEnums#7](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_6.cs)]</span></span>  
  
 <span data-ttu-id="5fee0-143">Дополнительные сведения о том, что необходимо учитывать при определении типов перечислений при помощи атрибута <xref:System.FlagsAttribute?displayProperty=fullName>, см. в статье <xref:System.Enum?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="5fee0-143">For more information about what to consider when you define enumeration types with the <xref:System.FlagsAttribute?displayProperty=fullName> attribute, see <xref:System.Enum?displayProperty=fullName>.</span></span>  
  
## <a name="using-the-systemenum-methods-to-discover-and-manipulate-enum-values"></a><span data-ttu-id="5fee0-144">Использование методов System.Enum для получения и обработки значений перечисления</span><span class="sxs-lookup"><span data-stu-id="5fee0-144">Using the System.Enum Methods to Discover and Manipulate Enum Values</span></span>  
 <span data-ttu-id="5fee0-145">Все перечисления являются экземплярами типа <xref:System.Enum?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="5fee0-145">All enums are instances of the <xref:System.Enum?displayProperty=fullName> type.</span></span> <span data-ttu-id="5fee0-146">Нельзя унаследовать новые классы от класса <xref:System.Enum?displayProperty=fullName>, но можно использовать его методы для получения и изменения данных об экземпляре перечисления.</span><span class="sxs-lookup"><span data-stu-id="5fee0-146">You cannot derive new classes from <xref:System.Enum?displayProperty=fullName>, but you can use its methods to discover information about and manipulate values in an enum instance.</span></span>  
  
 <span data-ttu-id="5fee0-147">[!code-cs[csProgGuideEnums#5](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="5fee0-147">[!code-cs[csProgGuideEnums#5](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_7.cs)]</span></span>  
  
 <span data-ttu-id="5fee0-148">Для получения дополнительной информации см. <xref:System.Enum?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="5fee0-148">For more information, see <xref:System.Enum?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="5fee0-149">Можно также создать для перечисления новый метод, используя метод расширения.</span><span class="sxs-lookup"><span data-stu-id="5fee0-149">You can also create a new method for an enum by using an extension method.</span></span> <span data-ttu-id="5fee0-150">Дополнительные сведения см. в разделе [Практическое руководство. Создание нового метода для перечисления](../../csharp/programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="5fee0-150">For more information, see [How to: Create a New Method for an Enumeration](../../csharp/programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="5fee0-151">См. также</span><span class="sxs-lookup"><span data-stu-id="5fee0-151">See Also</span></span>  
 <span data-ttu-id="5fee0-152"><xref:System.Enum?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="5fee0-152"><xref:System.Enum?displayProperty=fullName></span></span>   
 <span data-ttu-id="5fee0-153">[Руководство по программированию на C#](../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5fee0-153">[C# Programming Guide](../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="5fee0-154">enum</span><span class="sxs-lookup"><span data-stu-id="5fee0-154">enum</span></span>](../../csharp/language-reference/keywords/enum.md)

