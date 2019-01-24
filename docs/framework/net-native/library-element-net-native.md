---
title: Элемент &lt;Library&gt; (машинный код .NET)
ms.date: 03/30/2017
ms.assetid: f642276b-33fb-4a81-b882-8808c31ba69e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e6615ab30fdc0d0ab65f135e1df4e206f5548dc7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743793"
---
# <a name="ltlibrarygt-element-net-native"></a><span data-ttu-id="1920e-102">Элемент &lt;Library&gt; (машинный код .NET)</span><span class="sxs-lookup"><span data-stu-id="1920e-102">&lt;Library&gt; Element (.NET Native)</span></span>
<span data-ttu-id="1920e-103">Определяет сборку, содержащую типы и члены типов, метаданные которой доступны для отражения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="1920e-103">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span>  
  
 <span data-ttu-id="1920e-104">Элемент \<Directives></span><span class="sxs-lookup"><span data-stu-id="1920e-104">\<Directives> Element</span></span>  
<span data-ttu-id="1920e-105">Элемент \<Library></span><span class="sxs-lookup"><span data-stu-id="1920e-105">\<Library> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1920e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1920e-106">Syntax</span></span>  
  
```xml  
<Library Name="assembly_name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1920e-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1920e-107">Attributes and Elements</span></span>  
 <span data-ttu-id="1920e-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1920e-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1920e-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1920e-109">Attributes</span></span>  
  
|<span data-ttu-id="1920e-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1920e-110">Attribute</span></span>|<span data-ttu-id="1920e-111">Описание</span><span class="sxs-lookup"><span data-stu-id="1920e-111">Description</span></span>|  
|---------------|-----------------|  
|`Name`|<span data-ttu-id="1920e-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="1920e-112">Required attribute.</span></span> <span data-ttu-id="1920e-113">Задает имя сборки.</span><span class="sxs-lookup"><span data-stu-id="1920e-113">Specifies the name of an assembly.</span></span> <span data-ttu-id="1920e-114">Дочерние элементы данного элемента `<Library>` определяют политику отражения среды выполнения для типов и членов типов в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="1920e-114">Child elements of this `<Library>` element define the runtime reflection policy for types and type members found in this assembly.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="1920e-115">Name - атрибут</span><span class="sxs-lookup"><span data-stu-id="1920e-115">Name attribute</span></span>  
  
|<span data-ttu-id="1920e-116">Значение</span><span class="sxs-lookup"><span data-stu-id="1920e-116">Value</span></span>|<span data-ttu-id="1920e-117">Описание</span><span class="sxs-lookup"><span data-stu-id="1920e-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1920e-118">*assembly_name*</span><span class="sxs-lookup"><span data-stu-id="1920e-118">*assembly_name*</span></span>|<span data-ttu-id="1920e-119">Простое имя сборки без расширения файла.</span><span class="sxs-lookup"><span data-stu-id="1920e-119">The simple name of the assembly, without its file extension.</span></span> <span data-ttu-id="1920e-120">Этот атрибут соответствует свойству <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1920e-120">This attribute corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="1920e-121">Например, имя сборки с именем Extensions.dll является «Extensions».</span><span class="sxs-lookup"><span data-stu-id="1920e-121">For example, the name of an assembly named Extensions.dll is "Extensions".</span></span> <span data-ttu-id="1920e-122">Сведения об особой форме имени сборки *assembly_name* с поддержкой условного включения метаданных сборки см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="1920e-122">See the Remarks section for a special form of *assembly_name* that supports conditional inclusion of metadata from the assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1920e-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1920e-123">Child Elements</span></span>  
  
|<span data-ttu-id="1920e-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="1920e-124">Element</span></span>|<span data-ttu-id="1920e-125">Описание:</span><span class="sxs-lookup"><span data-stu-id="1920e-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1920e-126">\<Assembly></span><span class="sxs-lookup"><span data-stu-id="1920e-126">\<Assembly></span></span>](../../../docs/framework/net-native/assembly-element-net-native.md)|<span data-ttu-id="1920e-127">Применяет политику ко всем типам в определенной сборке.</span><span class="sxs-lookup"><span data-stu-id="1920e-127">Applies policy to all the types in a particular assembly.</span></span>|  
|[<span data-ttu-id="1920e-128">\<Namespace></span><span class="sxs-lookup"><span data-stu-id="1920e-128">\<Namespace></span></span>](../../../docs/framework/net-native/namespace-element-net-native.md)|<span data-ttu-id="1920e-129">Применяет политику ко всем типам в определенном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="1920e-129">Applies policy to all the types in a particular namespace.</span></span>|  
|[<span data-ttu-id="1920e-130">\<Type></span><span class="sxs-lookup"><span data-stu-id="1920e-130">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="1920e-131">Применяет политику для конкретного типа, например, класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="1920e-131">Applies policy to a particular type, such as a class or structure.</span></span>|  
|[<span data-ttu-id="1920e-132">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="1920e-132">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="1920e-133">Применяет политику к сконструированному универсальному типу.</span><span class="sxs-lookup"><span data-stu-id="1920e-133">Applies policy to a constructed generic type.</span></span> <span data-ttu-id="1920e-134">Например, элемент [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) можно использовать для определения политики для типа `List<String>`.</span><span class="sxs-lookup"><span data-stu-id="1920e-134">For example, a [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element could be used to define policy for a `List<String>` type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1920e-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1920e-135">Parent Elements</span></span>  
  
|<span data-ttu-id="1920e-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="1920e-136">Element</span></span>|<span data-ttu-id="1920e-137">Описание</span><span class="sxs-lookup"><span data-stu-id="1920e-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1920e-138">\<Directives></span><span class="sxs-lookup"><span data-stu-id="1920e-138">\<Directives></span></span>](../../../docs/framework/net-native/directives-element-net-native.md)|<span data-ttu-id="1920e-139">Корневой элемент файла директив среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="1920e-139">The root element of a runtime directives file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1920e-140">Примечания</span><span class="sxs-lookup"><span data-stu-id="1920e-140">Remarks</span></span>  
 <span data-ttu-id="1920e-141">Элемент [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) может иметь ноль, один или более элементов `<Library>`.</span><span class="sxs-lookup"><span data-stu-id="1920e-141">The [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) element can contain zero, one, or more `<Library>` elements.</span></span>  
  
 <span data-ttu-id="1920e-142">Элемент `<Library>` используется как контейнер для определения программных элементов, метаданные которых требуются во время выполнения. Этот элемент не выражают политики.</span><span class="sxs-lookup"><span data-stu-id="1920e-142">The `<Library>` element serves as a container to define the program elements whose metadata is needed at run time; this element doesn't express policy.</span></span> <span data-ttu-id="1920e-143">Во время компиляции средства компилятора осуществляют поиск только в библиотеке, назначенной с помощью элемента `<Library>`, на наличие программных элементов, определенных его дочерними элементами.</span><span class="sxs-lookup"><span data-stu-id="1920e-143">At compile time, compiler tools search only the library designated by the `<Library>` element for program elements identified by its child elements.</span></span> <span data-ttu-id="1920e-144">Напротив, средства компилятора проверяют все библиотеки, в том числе основные библиотеки .NET Framework, на наличие программных элементов, которые определяются дочерними элементами элемента [\<Application>](../../../docs/framework/net-native/application-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="1920e-144">In contrast, compiler tools search all libraries, including.NET Framework core libraries, for program elements identified by child elements of the [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element.</span></span>  
  
 <span data-ttu-id="1920e-145">Директивы `<Library>` могут использоваться условно.</span><span class="sxs-lookup"><span data-stu-id="1920e-145">`<Library>` directives may be conditionally utilized.</span></span> <span data-ttu-id="1920e-146">Если имя `<Library>` начинается и заканчивается звездочкой (\*), `<Library>` директива действует только в том случае, если ссылку на его сборку, указанную между звездочками.</span><span class="sxs-lookup"><span data-stu-id="1920e-146">If the name of the `<Library>` element starts and ends with an asterisk (\*), the `<Library>` directive has an effect only if the assembly specified between the asterisks is referenced by the app.</span></span> <span data-ttu-id="1920e-147">Например, следующие директивы среды выполнения применяются только к сборке Utillities.dll, на которую ссылается приложение.</span><span class="sxs-lookup"><span data-stu-id="1920e-147">For example, the following runtime directive applies only if the Utillities.dll assembly is referenced by the app.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Library Name="*Utilities*">  
   ...  
  </Library>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1920e-148">См. также</span><span class="sxs-lookup"><span data-stu-id="1920e-148">See also</span></span>
- [<span data-ttu-id="1920e-149">\<Приложение > элемент</span><span class="sxs-lookup"><span data-stu-id="1920e-149">\<Application> Element</span></span>](../../../docs/framework/net-native/application-element-net-native.md)
- [<span data-ttu-id="1920e-150">\<Директивы > элемент</span><span class="sxs-lookup"><span data-stu-id="1920e-150">\<Directives> Element</span></span>](../../../docs/framework/net-native/directives-element-net-native.md)
- [<span data-ttu-id="1920e-151">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="1920e-151">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="1920e-152">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="1920e-152">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
