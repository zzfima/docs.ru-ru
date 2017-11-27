---
title: "Элементы директив среды выполнения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3fe5848c-ecd7-4136-970b-8e48d250bde6
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3143c6b78749f3339e7e7195b551b5a5c31fad12
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="runtime-directive-elements"></a><span data-ttu-id="25415-102">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="25415-102">Runtime Directive Elements</span></span>
<span data-ttu-id="25415-103">Формат файла директив (rd.xml) среды выполнения поддерживает следующие элементы директивы среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="25415-103">The runtime directives (rd.xml) file format supports the following runtime directive elements.</span></span> <span data-ttu-id="25415-104">Иерархическое представление см. в разделе [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="25415-104">See [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md) for a hierarchical representation.</span></span>  
  
 [<span data-ttu-id="25415-105">\<Application></span><span class="sxs-lookup"><span data-stu-id="25415-105">\<Application></span></span>](../../../docs/framework/net-native/application-element-net-native.md)  
 <span data-ttu-id="25415-106">Применяется политика отражения среды выполнения для всех типов, используемых в приложении и служит в качестве контейнера для приложения типы и члены типов, метаданные которого доступны для отражения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="25415-106">Applies runtime reflection policy to all types used by the app, and serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="25415-107">Это дочерний элемент для элемента [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="25415-107">This is a child of the [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) element.</span></span>  
  
 [<span data-ttu-id="25415-108">\<Assembly></span><span class="sxs-lookup"><span data-stu-id="25415-108">\<Assembly></span></span>](../../../docs/framework/net-native/assembly-element-net-native.md)  
 <span data-ttu-id="25415-109">Применяет политику среды выполнения ко всем типам в сборке.</span><span class="sxs-lookup"><span data-stu-id="25415-109">Applies runnntime policy to all the types in an assembly.</span></span> <span data-ttu-id="25415-110">Это дочерний элемент элементов [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) и [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="25415-110">This is a child of the [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) and [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="25415-111">\<AttributeImplies></span><span class="sxs-lookup"><span data-stu-id="25415-111">\<AttributeImplies></span></span>](../../../docs/framework/net-native/attributeimplies-element-net-native.md)  
 <span data-ttu-id="25415-112">Если содержащая директива [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) является атрибутом, применяет политику среды выполнения к элементам кода, к которым применяется атрибут.</span><span class="sxs-lookup"><span data-stu-id="25415-112">If its containing [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) directive is an attribute, applies runtime policy to code elements to which that attribute is applied.</span></span>  
  
 [<span data-ttu-id="25415-113">\<Directives></span><span class="sxs-lookup"><span data-stu-id="25415-113">\<Directives></span></span>](../../../docs/framework/net-native/directives-element-net-native.md)  
 <span data-ttu-id="25415-114">Корневой элемент в любом файле директив среды выполнения для [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25415-114">The root element in every runtime directives file for [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="25415-115">Его дочерними элементами являются элементы [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) и [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="25415-115">Its child elements are [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) and [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).</span></span>  
  
 [<span data-ttu-id="25415-116">\<Event></span><span class="sxs-lookup"><span data-stu-id="25415-116">\<Event></span></span>](../../../docs/framework/net-native/event-element-net-native.md)  
 <span data-ttu-id="25415-117">Применяет политику среды выполнения к событию.</span><span class="sxs-lookup"><span data-stu-id="25415-117">Applies runtime policy to an event.</span></span> <span data-ttu-id="25415-118">Это дочерний элемент элементов [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) и [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="25415-118">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="25415-119">\<Field></span><span class="sxs-lookup"><span data-stu-id="25415-119">\<Field></span></span>](../../../docs/framework/net-native/field-element-net-native.md)  
 <span data-ttu-id="25415-120">Применяет политику среды выполнения к полю.</span><span class="sxs-lookup"><span data-stu-id="25415-120">Applies runtime policy to a field.</span></span> <span data-ttu-id="25415-121">Это дочерний элемент элементов [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) и [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="25415-121">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="25415-122">\<GenericParameter></span><span class="sxs-lookup"><span data-stu-id="25415-122">\<GenericParameter></span></span>](../../../docs/framework/net-native/genericparameter-element-net-native.md)  
 <span data-ttu-id="25415-123">Применяет политику среды выполнения к параметру типа универсального типа или метода.</span><span class="sxs-lookup"><span data-stu-id="25415-123">Applies runtime policy to the parameter type of a generic type or method.</span></span>  
  
 [<span data-ttu-id="25415-124">\<ImpliesType></span><span class="sxs-lookup"><span data-stu-id="25415-124">\<ImpliesType></span></span>](../../../docs/framework/net-native/impliestype-element-net-native.md)  
 <span data-ttu-id="25415-125">Применяет политику среды выполнения к типу, если политика была применена к содержащему типу или методу.</span><span class="sxs-lookup"><span data-stu-id="25415-125">Applies runtime policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
 [<span data-ttu-id="25415-126">\<Library></span><span class="sxs-lookup"><span data-stu-id="25415-126">\<Library></span></span>](../../../docs/framework/net-native/library-element-net-native.md)  
 <span data-ttu-id="25415-127">Применяет политику среды выполнения ко всем типам в сборке.</span><span class="sxs-lookup"><span data-stu-id="25415-127">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="25415-128">Это дочерний элемент элементов [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) и [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="25415-128">This is a child of the [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) and [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="25415-129">\<Method></span><span class="sxs-lookup"><span data-stu-id="25415-129">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)  
 <span data-ttu-id="25415-130">Применяет политику среды выполнения к методу.</span><span class="sxs-lookup"><span data-stu-id="25415-130">Applies runtime policy to a method.</span></span> <span data-ttu-id="25415-131">Это дочерний элемент элементов [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) и [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="25415-131">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="25415-132">\<MethodInstantiation></span><span class="sxs-lookup"><span data-stu-id="25415-132">\<MethodInstantiation></span></span>](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)  
 <span data-ttu-id="25415-133">Применяет политику среды выполнения к сконструированному универсальному методу.</span><span class="sxs-lookup"><span data-stu-id="25415-133">Applies runtime policy to a constructed generic method.</span></span> <span data-ttu-id="25415-134">Это дочерний элемент элементов [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) и [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="25415-134">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="25415-135">\<Namespace></span><span class="sxs-lookup"><span data-stu-id="25415-135">\<Namespace></span></span>](../../../docs/framework/net-native/namespace-element-net-native.md)  
 <span data-ttu-id="25415-136">Применяет политику среды выполнения ко всем типам в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="25415-136">Applies runtime policy to all the types in a namespace.</span></span>  
  
 [<span data-ttu-id="25415-137">\<Parameter></span><span class="sxs-lookup"><span data-stu-id="25415-137">\<Parameter></span></span>](../../../docs/framework/net-native/parameter-element-net-native.md)  
 <span data-ttu-id="25415-138">Применяет политику среды выполнения к типу аргумента, переданного методу.</span><span class="sxs-lookup"><span data-stu-id="25415-138">Applies runtime policy to the type of the argument passed to a method.</span></span>  
  
 [<span data-ttu-id="25415-139">\<Property></span><span class="sxs-lookup"><span data-stu-id="25415-139">\<Property></span></span>](../../../docs/framework/net-native/property-element-net-native.md)  
 <span data-ttu-id="25415-140">Применяет политику среды выполнения к свойству.</span><span class="sxs-lookup"><span data-stu-id="25415-140">Applies runtime policy to a property.</span></span> <span data-ttu-id="25415-141">Это дочерний элемент элементов [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) и [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="25415-141">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="25415-142">\<Subtypes></span><span class="sxs-lookup"><span data-stu-id="25415-142">\<Subtypes></span></span>](../../../docs/framework/net-native/subtypes-element-net-native.md)  
 <span data-ttu-id="25415-143">Применяет политику среды выполнения для всех классов, унаследованных из содержащего типа.</span><span class="sxs-lookup"><span data-stu-id="25415-143">Applies runtime policy to all classes inherited from the containing type.</span></span>  
  
 [<span data-ttu-id="25415-144">\<Type></span><span class="sxs-lookup"><span data-stu-id="25415-144">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)  
 <span data-ttu-id="25415-145">Применяет политику среды выполнения к типу.</span><span class="sxs-lookup"><span data-stu-id="25415-145">Applies runtime policy to a type.</span></span>  
  
 [<span data-ttu-id="25415-146">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="25415-146">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)  
 <span data-ttu-id="25415-147">Применяет политику среды выполнения к сконструированному универсальному типу.</span><span class="sxs-lookup"><span data-stu-id="25415-147">Applies runtime policy to a constructed generic type.</span></span>  
  
 [<span data-ttu-id="25415-148">\<TypeParameter></span><span class="sxs-lookup"><span data-stu-id="25415-148">\<TypeParameter></span></span>](../../../docs/framework/net-native/typeparameter-element-net-native.md)  
 <span data-ttu-id="25415-149">Применяет политику среды выполнения к типу, представленному аргументом <xref:System.Type>, переданным методу.</span><span class="sxs-lookup"><span data-stu-id="25415-149">Applies runtime policy to the type represented by a <xref:System.Type> argument passed to a method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25415-150">См. также</span><span class="sxs-lookup"><span data-stu-id="25415-150">See Also</span></span>  
 [<span data-ttu-id="25415-151">Справочник по конфигурационному файлу rd.xml</span><span class="sxs-lookup"><span data-stu-id="25415-151">rd.xml Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
