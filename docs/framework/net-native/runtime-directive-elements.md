---
title: Элементы директив среды выполнения
ms.date: 03/30/2017
ms.assetid: 3fe5848c-ecd7-4136-970b-8e48d250bde6
ms.openlocfilehash: c900516382c8e526a6b0021bb2b681486283f3ab
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128172"
---
# <a name="runtime-directive-elements"></a><span data-ttu-id="a3c90-102">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="a3c90-102">Runtime Directive Elements</span></span>
<span data-ttu-id="a3c90-103">Формат файла директив (rd.xml) среды выполнения поддерживает следующие элементы директивы среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="a3c90-103">The runtime directives (rd.xml) file format supports the following runtime directive elements.</span></span> <span data-ttu-id="a3c90-104">Иерархическое представление см. в разделе [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="a3c90-104">See [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md) for a hierarchical representation.</span></span>  
  
 [<span data-ttu-id="a3c90-105">\<Application></span><span class="sxs-lookup"><span data-stu-id="a3c90-105">\<Application></span></span>](application-element-net-native.md)  
 <span data-ttu-id="a3c90-106">Применяется политика отражения среды выполнения для всех типов, используемых в приложении и служит в качестве контейнера для приложения типы и члены типов, метаданные которого доступны для отражения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a3c90-106">Applies runtime reflection policy to all types used by the app, and serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="a3c90-107">Это дочерний элемент для элемента [\<Directives>](directives-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="a3c90-107">This is a child of the [\<Directives>](directives-element-net-native.md) element.</span></span>  
  
 [<span data-ttu-id="a3c90-108">\<Assembly></span><span class="sxs-lookup"><span data-stu-id="a3c90-108">\<Assembly></span></span>](assembly-element-net-native.md)  
 <span data-ttu-id="a3c90-109">Применяет политику среды выполнения ко всем типам в сборке.</span><span class="sxs-lookup"><span data-stu-id="a3c90-109">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="a3c90-110">Это дочерний элемент элементов [\<Application>](application-element-net-native.md) и [\<Library>](library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="a3c90-110">This is a child of the [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="a3c90-111">\<AttributeImplies></span><span class="sxs-lookup"><span data-stu-id="a3c90-111">\<AttributeImplies></span></span>](attributeimplies-element-net-native.md)  
 <span data-ttu-id="a3c90-112">Если содержащая директива [\<Type>](type-element-net-native.md) является атрибутом, применяет политику среды выполнения к элементам кода, к которым применяется атрибут.</span><span class="sxs-lookup"><span data-stu-id="a3c90-112">If its containing [\<Type>](type-element-net-native.md) directive is an attribute, applies runtime policy to code elements to which that attribute is applied.</span></span>  
  
 [<span data-ttu-id="a3c90-113">\<Directives></span><span class="sxs-lookup"><span data-stu-id="a3c90-113">\<Directives></span></span>](directives-element-net-native.md)  
 <span data-ttu-id="a3c90-114">Корневой элемент в каждом файле директив среды выполнения для .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a3c90-114">The root element in every runtime directives file for .NET Native.</span></span> <span data-ttu-id="a3c90-115">Его дочерними элементами являются элементы [\<Application>](application-element-net-native.md) и [\<Library>](library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="a3c90-115">Its child elements are [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md).</span></span>  
  
 [<span data-ttu-id="a3c90-116">\<Event></span><span class="sxs-lookup"><span data-stu-id="a3c90-116">\<Event></span></span>](event-element-net-native.md)  
 <span data-ttu-id="a3c90-117">Применяет политику среды выполнения к событию.</span><span class="sxs-lookup"><span data-stu-id="a3c90-117">Applies runtime policy to an event.</span></span> <span data-ttu-id="a3c90-118">Это дочерний элемент элементов [\<Type>](type-element-net-native.md) и [\<TypeInstantiation>](typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="a3c90-118">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="a3c90-119">\<Field></span><span class="sxs-lookup"><span data-stu-id="a3c90-119">\<Field></span></span>](field-element-net-native.md)  
 <span data-ttu-id="a3c90-120">Применяет политику среды выполнения к полю.</span><span class="sxs-lookup"><span data-stu-id="a3c90-120">Applies runtime policy to a field.</span></span> <span data-ttu-id="a3c90-121">Это дочерний элемент элементов [\<Type>](type-element-net-native.md) и [\<TypeInstantiation>](typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="a3c90-121">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="a3c90-122">\<GenericParameter></span><span class="sxs-lookup"><span data-stu-id="a3c90-122">\<GenericParameter></span></span>](genericparameter-element-net-native.md)  
 <span data-ttu-id="a3c90-123">Применяет политику среды выполнения к параметру типа универсального типа или метода.</span><span class="sxs-lookup"><span data-stu-id="a3c90-123">Applies runtime policy to the parameter type of a generic type or method.</span></span>  
  
 [<span data-ttu-id="a3c90-124">\<ImpliesType></span><span class="sxs-lookup"><span data-stu-id="a3c90-124">\<ImpliesType></span></span>](impliestype-element-net-native.md)  
 <span data-ttu-id="a3c90-125">Применяет политику среды выполнения к типу, если политика была применена к содержащему типу или методу.</span><span class="sxs-lookup"><span data-stu-id="a3c90-125">Applies runtime policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
 [<span data-ttu-id="a3c90-126">\<Library></span><span class="sxs-lookup"><span data-stu-id="a3c90-126">\<Library></span></span>](library-element-net-native.md)  
 <span data-ttu-id="a3c90-127">Применяет политику среды выполнения ко всем типам в сборке.</span><span class="sxs-lookup"><span data-stu-id="a3c90-127">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="a3c90-128">Это дочерний элемент элементов [\<Application>](application-element-net-native.md) и [\<Library>](library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="a3c90-128">This is a child of the [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="a3c90-129">\<Method></span><span class="sxs-lookup"><span data-stu-id="a3c90-129">\<Method></span></span>](method-element-net-native.md)  
 <span data-ttu-id="a3c90-130">Применяет политику среды выполнения к методу.</span><span class="sxs-lookup"><span data-stu-id="a3c90-130">Applies runtime policy to a method.</span></span> <span data-ttu-id="a3c90-131">Это дочерний элемент элементов [\<Type>](type-element-net-native.md) и [\<TypeInstantiation>](typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="a3c90-131">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="a3c90-132">\<MethodInstantiation></span><span class="sxs-lookup"><span data-stu-id="a3c90-132">\<MethodInstantiation></span></span>](methodinstantiation-element-net-native.md)  
 <span data-ttu-id="a3c90-133">Применяет политику среды выполнения к сконструированному универсальному методу.</span><span class="sxs-lookup"><span data-stu-id="a3c90-133">Applies runtime policy to a constructed generic method.</span></span> <span data-ttu-id="a3c90-134">Это дочерний элемент элементов [\<Type>](type-element-net-native.md) и [\<TypeInstantiation>](typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="a3c90-134">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="a3c90-135">\<Namespace></span><span class="sxs-lookup"><span data-stu-id="a3c90-135">\<Namespace></span></span>](namespace-element-net-native.md)  
 <span data-ttu-id="a3c90-136">Применяет политику среды выполнения ко всем типам в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="a3c90-136">Applies runtime policy to all the types in a namespace.</span></span>  
  
 [<span data-ttu-id="a3c90-137">\<Parameter></span><span class="sxs-lookup"><span data-stu-id="a3c90-137">\<Parameter></span></span>](parameter-element-net-native.md)  
 <span data-ttu-id="a3c90-138">Применяет политику среды выполнения к типу аргумента, переданного методу.</span><span class="sxs-lookup"><span data-stu-id="a3c90-138">Applies runtime policy to the type of the argument passed to a method.</span></span>  
  
 [<span data-ttu-id="a3c90-139">\<Property></span><span class="sxs-lookup"><span data-stu-id="a3c90-139">\<Property></span></span>](property-element-net-native.md)  
 <span data-ttu-id="a3c90-140">Применяет политику среды выполнения к свойству.</span><span class="sxs-lookup"><span data-stu-id="a3c90-140">Applies runtime policy to a property.</span></span> <span data-ttu-id="a3c90-141">Это дочерний элемент элементов [\<Type>](type-element-net-native.md) и [\<TypeInstantiation>](typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="a3c90-141">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="a3c90-142">\<Subtypes></span><span class="sxs-lookup"><span data-stu-id="a3c90-142">\<Subtypes></span></span>](subtypes-element-net-native.md)  
 <span data-ttu-id="a3c90-143">Применяет политику среды выполнения для всех классов, унаследованных из содержащего типа.</span><span class="sxs-lookup"><span data-stu-id="a3c90-143">Applies runtime policy to all classes inherited from the containing type.</span></span>  
  
 [<span data-ttu-id="a3c90-144">\<Type></span><span class="sxs-lookup"><span data-stu-id="a3c90-144">\<Type></span></span>](type-element-net-native.md)  
 <span data-ttu-id="a3c90-145">Применяет политику среды выполнения к типу.</span><span class="sxs-lookup"><span data-stu-id="a3c90-145">Applies runtime policy to a type.</span></span>  
  
 [<span data-ttu-id="a3c90-146">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="a3c90-146">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)  
 <span data-ttu-id="a3c90-147">Применяет политику среды выполнения к сконструированному универсальному типу.</span><span class="sxs-lookup"><span data-stu-id="a3c90-147">Applies runtime policy to a constructed generic type.</span></span>  
  
 [<span data-ttu-id="a3c90-148">\<TypeParameter></span><span class="sxs-lookup"><span data-stu-id="a3c90-148">\<TypeParameter></span></span>](typeparameter-element-net-native.md)  
 <span data-ttu-id="a3c90-149">Применяет политику среды выполнения к типу, представленному аргументом <xref:System.Type>, переданным методу.</span><span class="sxs-lookup"><span data-stu-id="a3c90-149">Applies runtime policy to the type represented by a <xref:System.Type> argument passed to a method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3c90-150">См. также</span><span class="sxs-lookup"><span data-stu-id="a3c90-150">See also</span></span>

- [<span data-ttu-id="a3c90-151">Справочник по конфигурационному файлу rd.xml</span><span class="sxs-lookup"><span data-stu-id="a3c90-151">rd.xml Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
