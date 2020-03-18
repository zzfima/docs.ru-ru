---
title: Написание настраиваемых атрибутов
ms.date: 07/17/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- multiple attribute instances
- AttributeTargets enumeration
- attributes [.NET Framework], custom
- AllowMultiple property
- custom attributes
- AttributeUsageAttribute class, custom attributes
- Inherited property
- attribute classes, declaring
ms.assetid: 97216f69-bde8-49fd-ac40-f18c500ef5dc
ms.openlocfilehash: 6570c6994c0f2e6571361c3eadc73b02a55f1584
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73140585"
---
# <a name="writing-custom-attributes"></a><span data-ttu-id="df27d-102">Написание настраиваемых атрибутов</span><span class="sxs-lookup"><span data-stu-id="df27d-102">Writing Custom Attributes</span></span>
<span data-ttu-id="df27d-103">Чтобы создавать собственные атрибуты, совсем не обязательно в совершенстве овладевать множеством новых понятий.</span><span class="sxs-lookup"><span data-stu-id="df27d-103">To design your own custom attributes, you do not need to master many new concepts.</span></span> <span data-ttu-id="df27d-104">Если вы знакомы с объектно-ориентированным программированием и знаете, как создавать классы, вы уже обладаете почти всеми нужными знаниями.</span><span class="sxs-lookup"><span data-stu-id="df27d-104">If you are familiar with object-oriented programming and know how to design classes, you already have most of the knowledge needed.</span></span> <span data-ttu-id="df27d-105">Настраиваемые атрибуты — это традиционные классы, прямо или косвенно наследующие от <xref:System.Attribute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="df27d-105">Custom attributes are essentially traditional classes that derive directly or indirectly from <xref:System.Attribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="df27d-106">Подобно традиционным классам настраиваемые атрибуты содержат методы, хранящие и извлекающие данные.</span><span class="sxs-lookup"><span data-stu-id="df27d-106">Just like traditional classes, custom attributes contain methods that store and retrieve data.</span></span>  
  
 <span data-ttu-id="df27d-107">Ниже приведены основные этапы правильно выстроенного процесса разработки классов настраиваемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="df27d-107">The primary steps to properly design custom attribute classes are as follows:</span></span>  
  
- [<span data-ttu-id="df27d-108">Применение атрибута AttributeUsageAttribute</span><span class="sxs-lookup"><span data-stu-id="df27d-108">Applying the AttributeUsageAttribute</span></span>](#applying-the-attributeusageattribute)  
  
- [<span data-ttu-id="df27d-109">Объявление класса атрибута</span><span class="sxs-lookup"><span data-stu-id="df27d-109">Declaring the attribute class</span></span>](#declaring-the-attribute-class)  
  
- [<span data-ttu-id="df27d-110">Объявление конструкторов</span><span class="sxs-lookup"><span data-stu-id="df27d-110">Declaring constructors</span></span>](#declaring-constructors)  
  
- [<span data-ttu-id="df27d-111">Объявление свойств</span><span class="sxs-lookup"><span data-stu-id="df27d-111">Declaring properties</span></span>](#declaring-properties)  
  
 <span data-ttu-id="df27d-112">В этом разделе описано каждое из этих действий. В конце приведен [пример настраиваемого атрибута](#custom-attribute-example).</span><span class="sxs-lookup"><span data-stu-id="df27d-112">This section describes each of these steps and concludes with a [custom attribute example](#custom-attribute-example).</span></span>  
  
## <a name="applying-the-attributeusageattribute"></a><span data-ttu-id="df27d-113">Применение атрибута AttributeUsageAttribute</span><span class="sxs-lookup"><span data-stu-id="df27d-113">Applying the AttributeUsageAttribute</span></span>  
 <span data-ttu-id="df27d-114">Объявление настраиваемого атрибута начинается с <xref:System.AttributeUsageAttribute?displayProperty=nameWithType>, что определяет некоторые ключевые характеристики класса атрибута.</span><span class="sxs-lookup"><span data-stu-id="df27d-114">A custom attribute declaration begins with the <xref:System.AttributeUsageAttribute?displayProperty=nameWithType>, which defines some of the key characteristics of your attribute class.</span></span> <span data-ttu-id="df27d-115">Например, можно указать, может ли атрибут быть унаследован другими классами, или указать элементы языка, к которым может применяться этот атрибут.</span><span class="sxs-lookup"><span data-stu-id="df27d-115">For example, you can specify whether your attribute can be inherited by other classes or specify which elements the attribute can be applied to.</span></span> <span data-ttu-id="df27d-116">В следующем фрагменте кода демонстрируется использование <xref:System.AttributeUsageAttribute>.</span><span class="sxs-lookup"><span data-stu-id="df27d-116">The following code fragment demonstrates how to use the <xref:System.AttributeUsageAttribute>.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#5)]
 [!code-csharp[Conceptual.Attributes.Usage#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#5)]
 [!code-vb[Conceptual.Attributes.Usage#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#5)]  
  
 <span data-ttu-id="df27d-117">В <xref:System.AttributeUsageAttribute> есть три члена, которые важны для создания настраиваемых атрибутов: [AttributeTargets](#attributetargets-member), [Inherited](#inherited-property)и [AllowMultiple](#allowmultiple-property).</span><span class="sxs-lookup"><span data-stu-id="df27d-117">The <xref:System.AttributeUsageAttribute> has three members that are important for the creation of custom attributes: [AttributeTargets](#attributetargets-member), [Inherited](#inherited-property), and [AllowMultiple](#allowmultiple-property).</span></span>  
  
### <a name="attributetargets-member"></a><span data-ttu-id="df27d-118">Член AttributeTargets</span><span class="sxs-lookup"><span data-stu-id="df27d-118">AttributeTargets Member</span></span>  
 <span data-ttu-id="df27d-119">В предыдущем примере использовался элемент <xref:System.AttributeTargets.All?displayProperty=nameWithType>, указывающий, что этот атрибут может применяться ко всем элементам программы.</span><span class="sxs-lookup"><span data-stu-id="df27d-119">In the previous example, <xref:System.AttributeTargets.All?displayProperty=nameWithType> is specified, indicating that this attribute can be applied to all program elements.</span></span> <span data-ttu-id="df27d-120">Можно также задать <xref:System.AttributeTargets.Class?displayProperty=nameWithType>, чтобы атрибут применялся только к классам, или <xref:System.AttributeTargets.Method?displayProperty=nameWithType>, чтобы атрибут применялся только к методам.</span><span class="sxs-lookup"><span data-stu-id="df27d-120">Alternatively, you can specify <xref:System.AttributeTargets.Class?displayProperty=nameWithType>, indicating that your attribute can be applied only to a class, or <xref:System.AttributeTargets.Method?displayProperty=nameWithType>, indicating that your attribute can be applied only to a method.</span></span> <span data-ttu-id="df27d-121">Подобным образом с помощью настраиваемых атрибутов можно выделить любые элементы программы с целью их последующего описания.</span><span class="sxs-lookup"><span data-stu-id="df27d-121">All program elements can be marked for description by a custom attribute in this manner.</span></span>  
  
 <span data-ttu-id="df27d-122">Вы также можете передать несколько значений <xref:System.AttributeTargets>.</span><span class="sxs-lookup"><span data-stu-id="df27d-122">You can also pass multiple <xref:System.AttributeTargets> values.</span></span> <span data-ttu-id="df27d-123">В следующем фрагменте кода задается применение настраиваемого атрибута к любому классу или методу.</span><span class="sxs-lookup"><span data-stu-id="df27d-123">The following code fragment specifies that a custom attribute can be applied to any class or method.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#6)]
 [!code-csharp[Conceptual.Attributes.Usage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#6)]
 [!code-vb[Conceptual.Attributes.Usage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#6)]  
  
### <a name="inherited-property"></a><span data-ttu-id="df27d-124">Свойство Inherited</span><span class="sxs-lookup"><span data-stu-id="df27d-124">Inherited Property</span></span>  
 <span data-ttu-id="df27d-125">Свойство <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> указывает, может ли атрибут быть унаследован классами, производными от класса, к которому этот атрибут применен.</span><span class="sxs-lookup"><span data-stu-id="df27d-125">The <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> property indicates whether your attribute can be inherited by classes that are derived from the classes to which your attribute is applied.</span></span> <span data-ttu-id="df27d-126">Это свойство принимает флаг `true` (по умолчанию) или `false`.</span><span class="sxs-lookup"><span data-stu-id="df27d-126">This property takes either a `true` (the default) or `false` flag.</span></span> <span data-ttu-id="df27d-127">В следующем примере в классе `MyAttribute` для свойства <xref:System.AttributeUsageAttribute.Inherited%2A> по умолчанию указано значение `true`, а в классе `YourAttribute` для свойства <xref:System.AttributeUsageAttribute.Inherited%2A> указано значение `false`.</span><span class="sxs-lookup"><span data-stu-id="df27d-127">In the following example, `MyAttribute` has a default <xref:System.AttributeUsageAttribute.Inherited%2A> value of `true`, while `YourAttribute` has an <xref:System.AttributeUsageAttribute.Inherited%2A> value of `false`.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#7)]
 [!code-csharp[Conceptual.Attributes.Usage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#7)]
 [!code-vb[Conceptual.Attributes.Usage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#7)]  
  
 <span data-ttu-id="df27d-128">Затем эти два атрибута применяются к методу в базовом классе `MyClass`.</span><span class="sxs-lookup"><span data-stu-id="df27d-128">The two attributes are then applied to a method in the base class `MyClass`.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#9)]
 [!code-csharp[Conceptual.Attributes.Usage#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#9)]
 [!code-vb[Conceptual.Attributes.Usage#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#9)]  
  
 <span data-ttu-id="df27d-129">Наконец, класс `YourClass` наследуется от базового класса `MyClass`.</span><span class="sxs-lookup"><span data-stu-id="df27d-129">Finally, the class `YourClass` is inherited from the base class `MyClass`.</span></span> <span data-ttu-id="df27d-130">Метод `MyMethod` использует атрибут `MyAttribute`, но не `YourAttribute`.</span><span class="sxs-lookup"><span data-stu-id="df27d-130">The method `MyMethod` shows `MyAttribute`, but not `YourAttribute`.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#10](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#10)]
 [!code-csharp[Conceptual.Attributes.Usage#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#10)]
 [!code-vb[Conceptual.Attributes.Usage#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#10)]  
  
### <a name="allowmultiple-property"></a><span data-ttu-id="df27d-131">Свойство AllowMultiple</span><span class="sxs-lookup"><span data-stu-id="df27d-131">AllowMultiple Property</span></span>  
 <span data-ttu-id="df27d-132">Свойство <xref:System.AttributeUsageAttribute.AllowMultiple%2A?displayProperty=nameWithType> указывает, можно ли применять к элементу несколько экземпляров атрибута.</span><span class="sxs-lookup"><span data-stu-id="df27d-132">The <xref:System.AttributeUsageAttribute.AllowMultiple%2A?displayProperty=nameWithType> property indicates whether multiple instances of your attribute can exist on an element.</span></span> <span data-ttu-id="df27d-133">Если его значение равно `true`, допускается существование нескольких экземпляров. Если значение равно `false` (по умолчанию), можно использовать только один экземпляр.</span><span class="sxs-lookup"><span data-stu-id="df27d-133">If set to `true`, multiple instances are allowed; if set to `false` (the default), only one instance is allowed.</span></span>  
  
 <span data-ttu-id="df27d-134">В следующем примере в классе `MyAttribute` для свойства <xref:System.AttributeUsageAttribute.AllowMultiple%2A> задано значение `false`, а для `YourAttribute` — `true`.</span><span class="sxs-lookup"><span data-stu-id="df27d-134">In the following example, `MyAttribute` has a default <xref:System.AttributeUsageAttribute.AllowMultiple%2A> value of `false`, while `YourAttribute` has a value of `true`.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#11)]
 [!code-csharp[Conceptual.Attributes.Usage#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#11)]
 [!code-vb[Conceptual.Attributes.Usage#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#11)]  
  
 <span data-ttu-id="df27d-135">При применении нескольких экземпляров этих атрибутов атрибут `MyAttribute` вызывает ошибку компилятора.</span><span class="sxs-lookup"><span data-stu-id="df27d-135">When multiple instances of these attributes are applied, `MyAttribute` produces a compiler error.</span></span> <span data-ttu-id="df27d-136">В следующем примере кода показано правильное использование атрибута `YourAttribute` и неправильное использование атрибута `MyAttribute`.</span><span class="sxs-lookup"><span data-stu-id="df27d-136">The following code example shows the valid use of `YourAttribute` and the invalid use of `MyAttribute`.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#13](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#13)]
 [!code-csharp[Conceptual.Attributes.Usage#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#13)]
 [!code-vb[Conceptual.Attributes.Usage#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#13)]  
  
 <span data-ttu-id="df27d-137">Если оба свойства <xref:System.AttributeUsageAttribute.AllowMultiple%2A> и <xref:System.AttributeUsageAttribute.Inherited%2A> имеют значение `true`, то класс, наследуемый от другого класса, может наследовать атрибуты и иметь дополнительные экземпляры атрибута, применяемого в этом же дочернем классе.</span><span class="sxs-lookup"><span data-stu-id="df27d-137">If both the <xref:System.AttributeUsageAttribute.AllowMultiple%2A> property and the <xref:System.AttributeUsageAttribute.Inherited%2A> property are set to `true`, a class that is inherited from another class can inherit an attribute and have another instance of the same attribute applied in the same child class.</span></span> <span data-ttu-id="df27d-138">Если <xref:System.AttributeUsageAttribute.AllowMultiple%2A> имеет значение `false`, значения атрибутов в родительском классе будут перезаписаны новыми экземплярами того же самого атрибута в дочернем классе.</span><span class="sxs-lookup"><span data-stu-id="df27d-138">If <xref:System.AttributeUsageAttribute.AllowMultiple%2A> is set to `false`, the values of any attributes in the parent class will be overwritten by new instances of the same attribute in the child class.</span></span>  
  
## <a name="declaring-the-attribute-class"></a><span data-ttu-id="df27d-139">Объявление класса атрибута</span><span class="sxs-lookup"><span data-stu-id="df27d-139">Declaring the Attribute Class</span></span>  
 <span data-ttu-id="df27d-140">После применения <xref:System.AttributeUsageAttribute>можно начать определение характеристик атрибута.</span><span class="sxs-lookup"><span data-stu-id="df27d-140">After you apply the <xref:System.AttributeUsageAttribute>, you can begin to define the specifics of your attribute.</span></span> <span data-ttu-id="df27d-141">Объявление класса атрибута выглядит аналогично объявлению традиционного класса, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="df27d-141">The declaration of an attribute class looks similar to the declaration of a traditional class, as demonstrated by the following code.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#14)]
 [!code-csharp[Conceptual.Attributes.Usage#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#14)]
 [!code-vb[Conceptual.Attributes.Usage#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#14)]  
  
 <span data-ttu-id="df27d-142">В этом определении атрибута демонстрируются следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="df27d-142">This attribute definition demonstrates the following points:</span></span>  
  
- <span data-ttu-id="df27d-143">Классы атрибутов должны объявляться как открытые классы.</span><span class="sxs-lookup"><span data-stu-id="df27d-143">Attribute classes must be declared as public classes.</span></span>  
  
- <span data-ttu-id="df27d-144">В соответствии с соглашением имя класса атрибута должно завершаться словом **Attribute**.</span><span class="sxs-lookup"><span data-stu-id="df27d-144">By convention, the name of the attribute class ends with the word **Attribute**.</span></span> <span data-ttu-id="df27d-145">Это условие не обязательно, но рекомендуется для повышения удобства чтения.</span><span class="sxs-lookup"><span data-stu-id="df27d-145">While not required, this convention is recommended for readability.</span></span> <span data-ttu-id="df27d-146">При применении атрибута использование слова Attribute является необязательным.</span><span class="sxs-lookup"><span data-stu-id="df27d-146">When the attribute is applied, the inclusion of the word Attribute is optional.</span></span>  
  
- <span data-ttu-id="df27d-147">Все классы атрибутов должны прямо или косвенно наследовать от класса <xref:System.Attribute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="df27d-147">All attribute classes must inherit directly or indirectly from <xref:System.Attribute?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="df27d-148">В Microsoft Visual Basic все классы настраиваемых атрибутов должны иметь атрибут <xref:System.AttributeUsageAttribute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="df27d-148">In Microsoft Visual Basic, all custom attribute classes must have the <xref:System.AttributeUsageAttribute?displayProperty=nameWithType> attribute.</span></span>  
  
## <a name="declaring-constructors"></a><span data-ttu-id="df27d-149">Объявление конструкторов</span><span class="sxs-lookup"><span data-stu-id="df27d-149">Declaring Constructors</span></span>  
 <span data-ttu-id="df27d-150">Атрибуты инициализируются с помощью конструкторов точно так же, как и традиционные классы.</span><span class="sxs-lookup"><span data-stu-id="df27d-150">Attributes are initialized with constructors in the same way as traditional classes.</span></span> <span data-ttu-id="df27d-151">В следующем фрагменте кода показан типичный конструктор атрибута.</span><span class="sxs-lookup"><span data-stu-id="df27d-151">The following code fragment illustrates a typical attribute constructor.</span></span> <span data-ttu-id="df27d-152">Этот открытый конструктор получает параметр и устанавливает его значение равным переменной-члену.</span><span class="sxs-lookup"><span data-stu-id="df27d-152">This public constructor takes a parameter and sets a member variable equal to its value.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#15](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#15)]
 [!code-csharp[Conceptual.Attributes.Usage#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#15)]
 [!code-vb[Conceptual.Attributes.Usage#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#15)]  
  
 <span data-ttu-id="df27d-153">Чтобы использовать различные сочетания значений, можно выполнить перегрузку конструктора.</span><span class="sxs-lookup"><span data-stu-id="df27d-153">You can overload the constructor to accommodate different combinations of values.</span></span> <span data-ttu-id="df27d-154">Если для класса настраиваемого атрибута также определяется и [свойство](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v=vs.120)) , при инициализации атрибута можно использовать сочетание именованных и позиционных параметров.</span><span class="sxs-lookup"><span data-stu-id="df27d-154">If you also define a [property](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v=vs.120)) for your custom attribute class, you can use a combination of named and positional parameters when initializing the attribute.</span></span> <span data-ttu-id="df27d-155">Как правило, все обязательные параметры определяются как позиционные, а все необязательные — как именованные.</span><span class="sxs-lookup"><span data-stu-id="df27d-155">Typically, you define all required parameters as positional and all optional parameters as named.</span></span> <span data-ttu-id="df27d-156">В этом случае атрибут нельзя инициализировать без обязательного параметра.</span><span class="sxs-lookup"><span data-stu-id="df27d-156">In this case, the attribute cannot be initialized without the required parameter.</span></span> <span data-ttu-id="df27d-157">Все остальные параметры являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="df27d-157">All other parameters are optional.</span></span> <span data-ttu-id="df27d-158">Обратите внимание, что в Visual Basic конструкторы для классов атрибутов не могут использовать аргумент ParamArray.</span><span class="sxs-lookup"><span data-stu-id="df27d-158">Note that in Visual Basic, constructors for an attribute class should not use a ParamArray argument.</span></span>  
  
 <span data-ttu-id="df27d-159">В следующем примере кода показано, как атрибут, использующий приведенный выше конструктор, можно использовать с обязательными и необязательными параметрами.</span><span class="sxs-lookup"><span data-stu-id="df27d-159">The following code example shows how an attribute that uses the previous constructor can be applied using optional and required parameters.</span></span> <span data-ttu-id="df27d-160">Предполагается, что этот атрибут имеет один обязательный логический параметр и одно необязательное строковое свойство.</span><span class="sxs-lookup"><span data-stu-id="df27d-160">It assumes that the attribute has one required Boolean value and one optional string property.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#17)]
 [!code-csharp[Conceptual.Attributes.Usage#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#17)]
 [!code-vb[Conceptual.Attributes.Usage#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#17)]  
  
## <a name="declaring-properties"></a><span data-ttu-id="df27d-161">Объявление свойств</span><span class="sxs-lookup"><span data-stu-id="df27d-161">Declaring Properties</span></span>  
 <span data-ttu-id="df27d-162">Если необходимо определить именованный параметр или предоставить простой способ получения значений, хранящихся в атрибуте, можно объявить [свойство](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="df27d-162">If you want to define a named parameter or provide an easy way to return the values stored by your attribute, declare a [property](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v=vs.120)).</span></span> <span data-ttu-id="df27d-163">Свойства атрибута следует объявлять как открытые сущности с описанием типа данных, который будет возвращен.</span><span class="sxs-lookup"><span data-stu-id="df27d-163">Attribute properties should be declared as public entities with a description of the data type that will be returned.</span></span> <span data-ttu-id="df27d-164">Определите переменную, которая будет хранить значение свойства, и свяжите ее с методами **get** и **set** .</span><span class="sxs-lookup"><span data-stu-id="df27d-164">Define the variable that will hold the value of your property and associate it with the **get** and **set** methods.</span></span> <span data-ttu-id="df27d-165">В следующем примере кода показана реализация простого свойства в атрибуте.</span><span class="sxs-lookup"><span data-stu-id="df27d-165">The following code example demonstrates how to implement a simple property in your attribute.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#16](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#16)]
 [!code-csharp[Conceptual.Attributes.Usage#16](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#16)]
 [!code-vb[Conceptual.Attributes.Usage#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#16)]  
  
## <a name="custom-attribute-example"></a><span data-ttu-id="df27d-166">Пример настраиваемого атрибута</span><span class="sxs-lookup"><span data-stu-id="df27d-166">Custom Attribute Example</span></span>  
 <span data-ttu-id="df27d-167">В этом разделе используются приведенные выше сведения и демонстрируется пример создания простого атрибута, содержащего данные об авторе раздела кода.</span><span class="sxs-lookup"><span data-stu-id="df27d-167">This section incorporates the previous information and shows how to design a simple attribute that documents information about the author of a section of code.</span></span> <span data-ttu-id="df27d-168">Атрибут в этом примере хранит имя и уровень программиста, а также данные об изменениях, внесенных в код.</span><span class="sxs-lookup"><span data-stu-id="df27d-168">The attribute in this example stores the name and level of the programmer, and whether the code has been reviewed.</span></span> <span data-ttu-id="df27d-169">Для хранения текущих сохраняемых значений в нем используются три закрытые переменные.</span><span class="sxs-lookup"><span data-stu-id="df27d-169">It uses three private variables to store the actual values to save.</span></span> <span data-ttu-id="df27d-170">Каждая переменная представлена открытым свойством, которое возвращает и задает значения.</span><span class="sxs-lookup"><span data-stu-id="df27d-170">Each variable is represented by a public property that gets and sets the values.</span></span> <span data-ttu-id="df27d-171">Наконец, в примере определяется конструктор с двумя обязательными параметрами.</span><span class="sxs-lookup"><span data-stu-id="df27d-171">Finally, the constructor is defined with two required parameters.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#4)]
 [!code-csharp[Conceptual.Attributes.Usage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#4)]
 [!code-vb[Conceptual.Attributes.Usage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#4)]  
  
 <span data-ttu-id="df27d-172">Этот атрибут можно применять с помощью полного имени `DeveloperAttribute` или сокращенного имени `Developer` одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="df27d-172">You can apply this attribute using the full name, `DeveloperAttribute`, or using the abbreviated name, `Developer`, in one of the following ways.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#12)]
 [!code-csharp[Conceptual.Attributes.Usage#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#12)]
 [!code-vb[Conceptual.Attributes.Usage#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#12)]  
  
 <span data-ttu-id="df27d-173">В первом примере этот атрибут применяется только с обязательными именованными параметрами, а во втором примере атрибут применяется и с обязательными, и с необязательными параметрами.</span><span class="sxs-lookup"><span data-stu-id="df27d-173">The first example shows the attribute applied with only the required named parameters, while the second example shows the attribute applied with both the required and optional parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df27d-174">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="df27d-174">See also</span></span>

- <xref:System.Attribute?displayProperty=nameWithType>
- <xref:System.AttributeUsageAttribute?displayProperty=nameWithType>
- [<span data-ttu-id="df27d-175">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="df27d-175">Attributes</span></span>](../../../docs/standard/attributes/index.md)
