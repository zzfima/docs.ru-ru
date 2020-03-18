---
title: AttributeUsage (C#)
ms.date: 04/25/2018
ms.openlocfilehash: a3a82e33d7259ec56ec3e907bc3d4d9f8a01167d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "61668722"
---
# <a name="attributeusage-c"></a><span data-ttu-id="a91bb-102">AttributeUsage (C#)</span><span class="sxs-lookup"><span data-stu-id="a91bb-102">AttributeUsage (C#)</span></span>

<span data-ttu-id="a91bb-103">Определяет, как можно использовать пользовательский класс атрибутов.</span><span class="sxs-lookup"><span data-stu-id="a91bb-103">Determines how a custom attribute class can be used.</span></span> <span data-ttu-id="a91bb-104"><xref:System.AttributeUsageAttribute> — это атрибут, примененный к определениям настраиваемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="a91bb-104"><xref:System.AttributeUsageAttribute> is an attribute you apply to custom attribute definitions.</span></span> <span data-ttu-id="a91bb-105">С помощью атрибута `AttributeUsage` можно контролировать:</span><span class="sxs-lookup"><span data-stu-id="a91bb-105">The `AttributeUsage` attribute enables you to control:</span></span>

- <span data-ttu-id="a91bb-106">Какой атрибут элементов программы можно применить.</span><span class="sxs-lookup"><span data-stu-id="a91bb-106">Which program elements attribute may be applied to.</span></span> <span data-ttu-id="a91bb-107">Если вы не ограничите использование, атрибут можно применить к любому из следующих элементов программы:</span><span class="sxs-lookup"><span data-stu-id="a91bb-107">Unless you restrict its usage, an attribute may be applied to any of the following program elements:</span></span>
  - <span data-ttu-id="a91bb-108">сборка</span><span class="sxs-lookup"><span data-stu-id="a91bb-108">assembly</span></span>
  - <span data-ttu-id="a91bb-109">module</span><span class="sxs-lookup"><span data-stu-id="a91bb-109">module</span></span>
  - <span data-ttu-id="a91bb-110">поле</span><span class="sxs-lookup"><span data-stu-id="a91bb-110">field</span></span>
  - <span data-ttu-id="a91bb-111">событие</span><span class="sxs-lookup"><span data-stu-id="a91bb-111">event</span></span>
  - <span data-ttu-id="a91bb-112">method</span><span class="sxs-lookup"><span data-stu-id="a91bb-112">method</span></span>
  - <span data-ttu-id="a91bb-113">param</span><span class="sxs-lookup"><span data-stu-id="a91bb-113">param</span></span>
  - <span data-ttu-id="a91bb-114">Свойство</span><span class="sxs-lookup"><span data-stu-id="a91bb-114">property</span></span>
  - <span data-ttu-id="a91bb-115">return</span><span class="sxs-lookup"><span data-stu-id="a91bb-115">return</span></span>
  - <span data-ttu-id="a91bb-116">type</span><span class="sxs-lookup"><span data-stu-id="a91bb-116">type</span></span>
- <span data-ttu-id="a91bb-117">Можно ли применить атрибут к одному элементу программы несколько раз.</span><span class="sxs-lookup"><span data-stu-id="a91bb-117">Whether an attribute can be applied to a single program element multiple times.</span></span>
- <span data-ttu-id="a91bb-118">Могут ли атрибуты наследоваться производными классами.</span><span class="sxs-lookup"><span data-stu-id="a91bb-118">Whether attributes are inherited by derived classes.</span></span>

<span data-ttu-id="a91bb-119">При явном применении параметры по умолчанию выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a91bb-119">The default settings look like the following example when applied explicitly:</span></span>

[!code-csharp[Define a new attribute](../../../../../samples/snippets/csharp/attributes/NewAttribute.cs#1)]

<span data-ttu-id="a91bb-120">В этом примере класс `NewAttribute` можно применить к любому поддерживаемому элементу программы.</span><span class="sxs-lookup"><span data-stu-id="a91bb-120">In this example, the `NewAttribute` class can be applied to any supported program element.</span></span> <span data-ttu-id="a91bb-121">Но он применяется к каждому объекту только один раз.</span><span class="sxs-lookup"><span data-stu-id="a91bb-121">But it can be applied only once to each entity.</span></span> <span data-ttu-id="a91bb-122">Атрибут наследуется производными классами при применении к базовому классу.</span><span class="sxs-lookup"><span data-stu-id="a91bb-122">The attribute is inherited by derived classes when applied to a base class.</span></span>

<span data-ttu-id="a91bb-123">Аргументы <xref:System.AttributeUsageAttribute.AllowMultiple> и <xref:System.AttributeUsageAttribute.Inherited> являются необязательными, так что следующий код имеет тот же результат:</span><span class="sxs-lookup"><span data-stu-id="a91bb-123">The <xref:System.AttributeUsageAttribute.AllowMultiple> and <xref:System.AttributeUsageAttribute.Inherited> arguments are optional, so the following code has the same effect:</span></span>

[!code-csharp[Omit optional attributes](../../../../../samples/snippets/csharp/attributes/NewAttribute.cs#2)]

<span data-ttu-id="a91bb-124">Первый аргумент <xref:System.AttributeUsageAttribute> должен состоять из одного или нескольких элементов перечисления <xref:System.AttributeTargets>.</span><span class="sxs-lookup"><span data-stu-id="a91bb-124">The first <xref:System.AttributeUsageAttribute> argument must be one or more elements of the <xref:System.AttributeTargets> enumeration.</span></span> <span data-ttu-id="a91bb-125">Несколько типов целевого объекта можно связать с помощью оператора OR, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="a91bb-125">Multiple target types can be linked together with the OR operator, like the following example shows:</span></span>

[!code-csharp[Create an attribute for fields or properties](../../../../../samples/snippets/csharp/attributes/NewPropertyOrFieldAttribute.cs#1)]

<span data-ttu-id="a91bb-126">Начиная с C# 7.3 атрибуты могут применяться либо к свойству, либо к резервному полю для автоматически реализуемого свойства.</span><span class="sxs-lookup"><span data-stu-id="a91bb-126">Beginning in C# 7.3, attributes can be applied to either the property or the backing field for an auto-implemented property.</span></span> <span data-ttu-id="a91bb-127">Атрибут применяется к свойству, если не указан описатель `field` для атрибута.</span><span class="sxs-lookup"><span data-stu-id="a91bb-127">The attribute applies to the property, unless you specify the `field` specifier on the attribute.</span></span> <span data-ttu-id="a91bb-128">Оба случая показаны в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="a91bb-128">Both are shown in the following example:</span></span>

[!code-csharp[Create an attribute for fields or properties](../../../../../samples/snippets/csharp/attributes/NewPropertyOrFieldAttribute.cs#2)]

<span data-ttu-id="a91bb-129">Если аргументу <xref:System.AttributeUsageAttribute.AllowMultiple> присвоено значение `true`, то результирующий атрибут можно применить несколько раз к одной сущности, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="a91bb-129">If the <xref:System.AttributeUsageAttribute.AllowMultiple> argument is `true`, then the resulting attribute can be applied more than once to a single entity, as shown in the following example:</span></span>

[!code-csharp[Create and use an attribute that can be applied multiple times](../../../../../samples/snippets/csharp/attributes/MultiUseAttribute.cs#1)]

<span data-ttu-id="a91bb-130">В этом случае `MultiUseAttribute` можно применять несколько раз, так как `AllowMultiple` имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="a91bb-130">In this case, `MultiUseAttribute` can be applied repeatedly because `AllowMultiple` is set to `true`.</span></span> <span data-ttu-id="a91bb-131">Для применения нескольких атрибутов допускаются оба показанных формата.</span><span class="sxs-lookup"><span data-stu-id="a91bb-131">Both formats shown for applying multiple attributes are valid.</span></span>

<span data-ttu-id="a91bb-132">Если <xref:System.AttributeUsageAttribute.Inherited> — `false`, атрибут не наследуется классами, производными от класса атрибутов.</span><span class="sxs-lookup"><span data-stu-id="a91bb-132">If <xref:System.AttributeUsageAttribute.Inherited> is `false`, then the attribute isn't inherited by classes derived from an attributed class.</span></span> <span data-ttu-id="a91bb-133">Пример:</span><span class="sxs-lookup"><span data-stu-id="a91bb-133">For example:</span></span>

[!code-csharp[Create and use an attribute that can be applied multiple times](../../../../../samples/snippets/csharp/attributes/NonInheritedAttribute.cs#1)]

<span data-ttu-id="a91bb-134">В этом случае `NonInheritedAttribute` не применяется к `DClass` путем наследования.</span><span class="sxs-lookup"><span data-stu-id="a91bb-134">In this case `NonInheritedAttribute` isn't applied to `DClass` via inheritance.</span></span>

## <a name="remarks"></a><span data-ttu-id="a91bb-135">Remarks</span><span class="sxs-lookup"><span data-stu-id="a91bb-135">Remarks</span></span>

<span data-ttu-id="a91bb-136">Атрибут `AttributeUsage` можно использовать только один раз — его нельзя повторно применять к одному и тому же классу.</span><span class="sxs-lookup"><span data-stu-id="a91bb-136">The `AttributeUsage` attribute is a single-use attribute--it can't be applied more than once to the same class.</span></span> <span data-ttu-id="a91bb-137">`AttributeUsage` является псевдонимом для <xref:System.AttributeUsageAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a91bb-137">`AttributeUsage` is an alias for <xref:System.AttributeUsageAttribute>.</span></span>

<span data-ttu-id="a91bb-138">Дополнительные сведения см. в разделе [Обращение к атрибутам с помощью отражения (C#)](accessing-attributes-by-using-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="a91bb-138">For more information, see [Accessing Attributes by Using Reflection (C#)](accessing-attributes-by-using-reflection.md).</span></span>

## <a name="example"></a><span data-ttu-id="a91bb-139">Пример</span><span class="sxs-lookup"><span data-stu-id="a91bb-139">Example</span></span>

<span data-ttu-id="a91bb-140">В приведенном ниже примере демонстрируется действие аргументов <xref:System.AttributeUsageAttribute.Inherited> и <xref:System.AttributeUsageAttribute.AllowMultiple> по отношению к атрибуту <xref:System.AttributeUsageAttribute>, а также способ перечисления настраиваемых атрибутов, примененных к классу.</span><span class="sxs-lookup"><span data-stu-id="a91bb-140">The following example demonstrates the effect of the <xref:System.AttributeUsageAttribute.Inherited> and <xref:System.AttributeUsageAttribute.AllowMultiple> arguments to the <xref:System.AttributeUsageAttribute> attribute, and how the custom attributes applied to a class can be enumerated.</span></span>

[!code-csharp[Applying and querying attributes](../../../../../samples/snippets/csharp/attributes/Program.cs#1)]

## <a name="sample-output"></a><span data-ttu-id="a91bb-141">Пример выходных данных</span><span class="sxs-lookup"><span data-stu-id="a91bb-141">Sample Output</span></span>

```text
Attributes on Base Class:
FirstAttribute
SecondAttribute
Attributes on Derived Class:
ThirdAttribute
ThirdAttribute
SecondAttribute
```

## <a name="see-also"></a><span data-ttu-id="a91bb-142">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a91bb-142">See also</span></span>

- <xref:System.Attribute>
- <xref:System.Reflection>
- [<span data-ttu-id="a91bb-143">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a91bb-143">C# Programming Guide</span></span>](../..//index.md)
- [<span data-ttu-id="a91bb-144">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a91bb-144">Attributes</span></span>](../../../..//standard/attributes/index.md)
- [<span data-ttu-id="a91bb-145">Отражение (C#)</span><span class="sxs-lookup"><span data-stu-id="a91bb-145">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="a91bb-146">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a91bb-146">Attributes</span></span>](index.md)
- [<span data-ttu-id="a91bb-147">Создание настраиваемых атрибутов (C#)</span><span class="sxs-lookup"><span data-stu-id="a91bb-147">Creating Custom Attributes (C#)</span></span>](creating-custom-attributes.md)
- [<span data-ttu-id="a91bb-148">Обращение к атрибутам с помощью отражения (C#)</span><span class="sxs-lookup"><span data-stu-id="a91bb-148">Accessing Attributes by Using Reflection (C#)</span></span>](accessing-attributes-by-using-reflection.md)
