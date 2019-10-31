---
title: Элемент <Method> (.NET Native)
ms.date: 03/30/2017
ms.assetid: 348b49e5-589d-4eb2-a597-d6ff60ab52d1
ms.openlocfilehash: 7b0e77e6dea29cbd5218ab3f6f992002efd51656
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128338"
---
# <a name="method-element-net-native"></a><span data-ttu-id="37a6c-102">Элемент > метода \<(.NET Native)</span><span class="sxs-lookup"><span data-stu-id="37a6c-102">\<Method> Element (.NET Native)</span></span>
<span data-ttu-id="37a6c-103">Применяет политику отражения среды выполнения к конструктору или методу.</span><span class="sxs-lookup"><span data-stu-id="37a6c-103">Applies runtime reflection policy to a constructor or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37a6c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="37a6c-104">Syntax</span></span>  
  
```xml  
<Method Name="method_name"  
        Signature="method_signature"  
        Browse="policy_type"  
        Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37a6c-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="37a6c-105">Attributes and Elements</span></span>  
 <span data-ttu-id="37a6c-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="37a6c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="37a6c-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="37a6c-107">Attributes</span></span>  
  
|<span data-ttu-id="37a6c-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="37a6c-108">Attribute</span></span>|<span data-ttu-id="37a6c-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="37a6c-109">Attribute type</span></span>|<span data-ttu-id="37a6c-110">Описание</span><span class="sxs-lookup"><span data-stu-id="37a6c-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="37a6c-111">Общее</span><span class="sxs-lookup"><span data-stu-id="37a6c-111">General</span></span>|<span data-ttu-id="37a6c-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="37a6c-112">Required attribute.</span></span> <span data-ttu-id="37a6c-113">Задает имя метода.</span><span class="sxs-lookup"><span data-stu-id="37a6c-113">Specifies the method name.</span></span>|  
|`Signature`|<span data-ttu-id="37a6c-114">Общее</span><span class="sxs-lookup"><span data-stu-id="37a6c-114">General</span></span>|<span data-ttu-id="37a6c-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="37a6c-115">Optional attribute.</span></span> <span data-ttu-id="37a6c-116">Задает подпись метода.</span><span class="sxs-lookup"><span data-stu-id="37a6c-116">Specifies the method signature.</span></span> <span data-ttu-id="37a6c-117">При наличии нескольких параметров, они разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="37a6c-117">If multiple parameters are present, they are separated by commas.</span></span> <span data-ttu-id="37a6c-118">Например, следующий элемент `<Method>` определяет политику для метода <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29>.</span><span class="sxs-lookup"><span data-stu-id="37a6c-118">For example, the following `<Method>` element defines policy for the <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29> method.</span></span><br /><br /> `<Type Name="System.DateTime">    <Method Name="ToString" Signature="System.String,System.IFormatProvider"            Dynamic="Required" /> </Type>`<br /><br /> <span data-ttu-id="37a6c-119">Если атрибут отсутствует, директива среды выполнения применяется для всех перегруженных версий метода.</span><span class="sxs-lookup"><span data-stu-id="37a6c-119">If the attribute is absent, the runtime directive applies to all overloads of the method.</span></span>|  
|`Browse`|<span data-ttu-id="37a6c-120">Отражение</span><span class="sxs-lookup"><span data-stu-id="37a6c-120">Reflection</span></span>|<span data-ttu-id="37a6c-121">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="37a6c-121">Optional attribute.</span></span> <span data-ttu-id="37a6c-122">Определяет запрос для получения сведений о методе или перечисляет методы, но не включает динамический вызов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="37a6c-122">Controls querying for information about or enumerating a method but does not enable any dynamic invocation at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="37a6c-123">Отражение</span><span class="sxs-lookup"><span data-stu-id="37a6c-123">Reflection</span></span>|<span data-ttu-id="37a6c-124">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="37a6c-124">Optional attribute.</span></span> <span data-ttu-id="37a6c-125">Управляет доступом среды выполнения к конструктору или методу для включения динамического программирования.</span><span class="sxs-lookup"><span data-stu-id="37a6c-125">Controls runtime access to a constructor or method to enable dynamic programming.</span></span> <span data-ttu-id="37a6c-126">Эта политика гарантирует, что член может быть вызван динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="37a6c-126">This policy ensures that a member can be invoked dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="37a6c-127">Name - атрибут</span><span class="sxs-lookup"><span data-stu-id="37a6c-127">Name attribute</span></span>  
  
|<span data-ttu-id="37a6c-128">значения</span><span class="sxs-lookup"><span data-stu-id="37a6c-128">Value</span></span>|<span data-ttu-id="37a6c-129">Описание</span><span class="sxs-lookup"><span data-stu-id="37a6c-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="37a6c-130">*method_name*</span><span class="sxs-lookup"><span data-stu-id="37a6c-130">*method_name*</span></span>|<span data-ttu-id="37a6c-131">Имя метода.</span><span class="sxs-lookup"><span data-stu-id="37a6c-131">The method name.</span></span> <span data-ttu-id="37a6c-132">Тип метода определяется родительским элементом [\<Type>](type-element-net-native.md) или [\<TypeInstantiation>](typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="37a6c-132">The type of the method is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="signature-attribute"></a><span data-ttu-id="37a6c-133">Сигнатура атрибута</span><span class="sxs-lookup"><span data-stu-id="37a6c-133">Signature attribute</span></span>  
  
|<span data-ttu-id="37a6c-134">значения</span><span class="sxs-lookup"><span data-stu-id="37a6c-134">Value</span></span>|<span data-ttu-id="37a6c-135">Описание</span><span class="sxs-lookup"><span data-stu-id="37a6c-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="37a6c-136">*method_signature*</span><span class="sxs-lookup"><span data-stu-id="37a6c-136">*method_signature*</span></span>|<span data-ttu-id="37a6c-137">Типы параметров, которые образуют сигнатуру метода.</span><span class="sxs-lookup"><span data-stu-id="37a6c-137">The parameter types that form the method signature.</span></span> <span data-ttu-id="37a6c-138">Несколько параметров разделяются запятыми, например, `"System.String,System.Int32,System.Int32)"`.</span><span class="sxs-lookup"><span data-stu-id="37a6c-138">Multiple parameters are separated by commas, for example, `"System.String,System.Int32,System.Int32)"`.</span></span> <span data-ttu-id="37a6c-139">Имена параметров типа должно быть полными.</span><span class="sxs-lookup"><span data-stu-id="37a6c-139">Parameter type names should be fully qualified.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="37a6c-140">Все остальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="37a6c-140">All other attributes</span></span>  
  
|<span data-ttu-id="37a6c-141">значения</span><span class="sxs-lookup"><span data-stu-id="37a6c-141">Value</span></span>|<span data-ttu-id="37a6c-142">Описание</span><span class="sxs-lookup"><span data-stu-id="37a6c-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="37a6c-143">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="37a6c-143">*policy_setting*</span></span>|<span data-ttu-id="37a6c-144">Параметр, применяемый для этого типа политики.</span><span class="sxs-lookup"><span data-stu-id="37a6c-144">The setting to apply to this policy type.</span></span> <span data-ttu-id="37a6c-145">Допустимые значения: `Auto`, `Excluded`, `Included` и `Required`.</span><span class="sxs-lookup"><span data-stu-id="37a6c-145">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="37a6c-146">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="37a6c-146">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="37a6c-147">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="37a6c-147">Child Elements</span></span>  
  
|<span data-ttu-id="37a6c-148">Элемент</span><span class="sxs-lookup"><span data-stu-id="37a6c-148">Element</span></span>|<span data-ttu-id="37a6c-149">Описание</span><span class="sxs-lookup"><span data-stu-id="37a6c-149">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37a6c-150">\<Parameter></span><span class="sxs-lookup"><span data-stu-id="37a6c-150">\<Parameter></span></span>](parameter-element-net-native.md)|<span data-ttu-id="37a6c-151">Применяет политику к типу аргумента, переданного методу.</span><span class="sxs-lookup"><span data-stu-id="37a6c-151">Applies policy to the type of the argument passed to a method.</span></span>|  
|[<span data-ttu-id="37a6c-152">\<GenericParameter></span><span class="sxs-lookup"><span data-stu-id="37a6c-152">\<GenericParameter></span></span>](genericparameter-element-net-native.md)|<span data-ttu-id="37a6c-153">Применяет политику к параметру типа универсального типа или метода.</span><span class="sxs-lookup"><span data-stu-id="37a6c-153">Applies policy to the parameter type of a generic type or method.</span></span>|  
|[<span data-ttu-id="37a6c-154">\<ImpliesType></span><span class="sxs-lookup"><span data-stu-id="37a6c-154">\<ImpliesType></span></span>](impliestype-element-net-native.md)|<span data-ttu-id="37a6c-155">Применяет политику к типу, если политика была применена для метода, представленного содержащим элементом `<Method>`.</span><span class="sxs-lookup"><span data-stu-id="37a6c-155">Applies policy to a type, if that policy has been applied to the method represented by the containing `<Method>` element.</span></span>|  
|[<span data-ttu-id="37a6c-156">\<TypeParameter></span><span class="sxs-lookup"><span data-stu-id="37a6c-156">\<TypeParameter></span></span>](typeparameter-element-net-native.md)|<span data-ttu-id="37a6c-157">Применяет политику к типу, представленному аргументом <xref:System.Type>, переданным методу.</span><span class="sxs-lookup"><span data-stu-id="37a6c-157">Applies policy to the type represented by a <xref:System.Type> argument passed to a method.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="37a6c-158">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="37a6c-158">Parent Elements</span></span>  
  
|<span data-ttu-id="37a6c-159">Элемент</span><span class="sxs-lookup"><span data-stu-id="37a6c-159">Element</span></span>|<span data-ttu-id="37a6c-160">Описание</span><span class="sxs-lookup"><span data-stu-id="37a6c-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37a6c-161">\<Type></span><span class="sxs-lookup"><span data-stu-id="37a6c-161">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="37a6c-162">Применяет политику отражения к типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="37a6c-162">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="37a6c-163">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="37a6c-163">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)|<span data-ttu-id="37a6c-164">Применяет политику отражения к сконструированному универсальному типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="37a6c-164">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37a6c-165">Заметки</span><span class="sxs-lookup"><span data-stu-id="37a6c-165">Remarks</span></span>  
 <span data-ttu-id="37a6c-166">Элемент `<Method>` универсального метода применяет свою политику для всех экземпляров, которые не имеют собственной политики.</span><span class="sxs-lookup"><span data-stu-id="37a6c-166">A `<Method>` element of a generic method applies its policy to all instantiations that do not have their own policy.</span></span>  
  
 <span data-ttu-id="37a6c-167">Можно использовать атрибут `Signature`, чтобы задать политику для перегрузки определенного метода.</span><span class="sxs-lookup"><span data-stu-id="37a6c-167">You can use the `Signature` attribute to specify policy for a particular method overload.</span></span> <span data-ttu-id="37a6c-168">В противном случае, если атрибут `Signature` отсутствует, директива среды выполнения применяется для всех перегруженных версий метода.</span><span class="sxs-lookup"><span data-stu-id="37a6c-168">Otherwise, if the `Signature` attribute is absent, the runtime directive applies to all overloads of the method.</span></span>  
  
 <span data-ttu-id="37a6c-169">Нельзя определить политику отражения среды выполнения для конструктора, используя элемент `<Method>`.</span><span class="sxs-lookup"><span data-stu-id="37a6c-169">You cannot define the runtime reflection policy for a constructor by using the `<Method>` element.</span></span> <span data-ttu-id="37a6c-170">Вместо этого используйте атрибут `Activate` элемента [\<Assembly>](assembly-element-net-native.md), [\<Namespace>](namespace-element-net-native.md), [\<Type>](type-element-net-native.md) или [\<TypeInstantiation>](typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="37a6c-170">Instead, use the `Activate` attribute of the  [\<Assembly>](assembly-element-net-native.md), [\<Namespace>](namespace-element-net-native.md), [\<Type>](type-element-net-native.md), or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37a6c-171">Пример</span><span class="sxs-lookup"><span data-stu-id="37a6c-171">Example</span></span>  
 <span data-ttu-id="37a6c-172">Метод `Stringify` в следующем примере – это универсальный метод форматирования, который использует отражение для преобразования объекта в строковое представление.</span><span class="sxs-lookup"><span data-stu-id="37a6c-172">The `Stringify` method in the following example is a general-purpose formatting method that uses reflection to convert an object to its string representation.</span></span> <span data-ttu-id="37a6c-173">Помимо вызова метода  `ToString` по умолчанию объекта , метод может создать отформатированную результирующую строку путем передачи методу  `ToString` объекта строки формата, реализации <xref:System.IFormatProvider>, или и то и другое.</span><span class="sxs-lookup"><span data-stu-id="37a6c-173">In addition to calling the object's default `ToString` method, the method can produce a formatted result string by passing an object's `ToString` method a format string, an <xref:System.IFormatProvider> implementation, or both.</span></span> <span data-ttu-id="37a6c-174">Он также может вызвать одну из перегрузок <xref:System.Convert.ToString%2A?displayProperty=nameWithType>, которая преобразует число в двоичное, шестнадцатеричное или восьмеричное представление.</span><span class="sxs-lookup"><span data-stu-id="37a6c-174">It can also call one of the <xref:System.Convert.ToString%2A?displayProperty=nameWithType> overloads that converts a number to its binary, hexadecimal, or octal representation.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/method1.cs#7)]  
  
 <span data-ttu-id="37a6c-175">Метод `Stringify` может быть вызван таким кодом, как указан ниже:</span><span class="sxs-lookup"><span data-stu-id="37a6c-175">The `Stringify` method can be called by code like the following:</span></span>  
  
 [!code-csharp[ProjectN_Reflection#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/method1.cs#7)]  
  
 <span data-ttu-id="37a6c-176">Тем не менее при компиляции с .NET Native пример может вызвать ряд исключений во время выполнения, включая исключения <xref:System.NullReferenceException> и [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md). Это происходит потому, что метод `Stringify` предназначен главным образом для поддержки динамического форматирования простых типов в библиотеке классов платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="37a6c-176">However, when compiled with .NET Native, the example can throw an number of exceptions at runtime, including <xref:System.NullReferenceException> and [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) exceptions, This occurs because the `Stringify` method is intended primarily to support dynamically formatting the primitive types in the .NET Framework Class Library.</span></span> <span data-ttu-id="37a6c-177">Однако их метаданные не становятся доступными в файле директив по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="37a6c-177">However, their metadata is not made available by the default directives file.</span></span> <span data-ttu-id="37a6c-178">Даже в том случае, если метаданные доступны, в примере возникают исключения [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md), поскольку соответствующие реализации `ToString` не были включены в машинный код.</span><span class="sxs-lookup"><span data-stu-id="37a6c-178">Even when their metadata is made available, however, the example throws [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) exceptions because the appropriate `ToString` implementations have not been include in the native code.</span></span>  
  
 <span data-ttu-id="37a6c-179">Чтобы устранить все эти исключения, необходимо определить типы, метаданные которых должны быть представлены, с помощью элемента [\<Type>](type-element-net-native.md) и добавить элементы `<Method>`, чтобы гарантировать наличие перегрузок методов, которые могут быть вызваны динамически.</span><span class="sxs-lookup"><span data-stu-id="37a6c-179">These exceptions can all be eliminated by using the [\<Type>](type-element-net-native.md) element to define the types whose metadata must be present, and by adding `<Method>` elements to ensure that the implementation of method overloads that can be called dynamically is also present.</span></span> <span data-ttu-id="37a6c-180">Ниже приведен файл default.rd.xml, который устраняет эти исключения и позволяет выполнить пример без ошибок.</span><span class="sxs-lookup"><span data-stu-id="37a6c-180">The following is the default.rd.xml file that eliminates these exceptions and allows the example to execute without error.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
     <Assembly Name="*Application*" Dynamic="Required All" />  
  
     <Type Name = "System.Convert" Browse="Required Public" Dynamic="Required Public" >  
        <Method Name="ToString"    Dynamic ="Required" />  
     </Type>  
     <Type Name="System.Double" Browse="Required Public">  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Type Name ="System.Int32" Browse="Required Public" >  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Type Name ="System.Int64" Browse="Required Public" >  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Namespace Name="System" >  
        <Type Name="Byte" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="DateTime" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Decimal" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Guid" Browse ="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Int16" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="SByte" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Single" Browse="Required Public" >  
          <Method Name="ToString" Dynamic="Required" />           
        </Type>  
        <Type Name="TimeSpan" Browse="Required Public" >  
          <Method Name="ToString" Dynamic="Required" />           
        </Type>  
        <Type Name="UInt16" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="UInt32" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="UInt64" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
     </Namespace>  
  </Application>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="37a6c-181">См. также</span><span class="sxs-lookup"><span data-stu-id="37a6c-181">See also</span></span>

- [<span data-ttu-id="37a6c-182">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="37a6c-182">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="37a6c-183">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="37a6c-183">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="37a6c-184">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="37a6c-184">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="37a6c-185">\<Элемент MethodInstantiation></span><span class="sxs-lookup"><span data-stu-id="37a6c-185">\<MethodInstantiation> Element</span></span>](methodinstantiation-element-net-native.md)
