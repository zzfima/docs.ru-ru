---
title: "Ссылка на файл конфигурации директив среды выполнения (rd.xml)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8241523f-d8e1-4fb6-bf6a-b29bfe07b38a
caps.latest.revision: "27"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2ecfc61c5b586dd3385890d73ded729a38fb41c2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="runtime-directives-rdxml-configuration-file-reference"></a><span data-ttu-id="a24a0-102">Ссылка на файл конфигурации директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="a24a0-102">Runtime Directives (rd.xml) Configuration File Reference</span></span>
<span data-ttu-id="a24a0-103">Файл директив среды выполнения (. rd.xml) — это файл конфигурации XML, который определяет, доступны ли элементы в указанной программе для отражения.</span><span class="sxs-lookup"><span data-stu-id="a24a0-103">A runtime directives (.rd.xml) file is an XML configuration file that specifies whether designated program elements are available for reflection.</span></span> <span data-ttu-id="a24a0-104">Ниже приведен пример файла директив среды выполнения:</span><span class="sxs-lookup"><span data-stu-id="a24a0-104">Here’s an example of a runtime directives file:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
<Application>  
  <Namespace Name="Contoso.Cloud.AppServices" Serialize="Required Public" />  
  <Namespace Name="ContosoClient.ViewModels" Serialize="Required Public" />  
  <Namespace Name="ContosoClient.DataModel" Serialize="Required Public" />  
  <Namespace Name="Contoso.Reader.UtilityLib" Serialize="Required Public" />  
  
  <Namespace Name="System.Collections.ObjectModel" >  
    <TypeInstantiation Name="ObservableCollection"   
          Arguments="ContosoClient.DataModel.ProductItem" Serialize="Public" />  
    <TypeInstantiation Name="ReadOnlyObservableCollection"   
          Arguments="ContosoClient.DataModel.ProductGroup" Serialize="Public" />  
  </Namespace>  
</Application>  
</Directives>  
```  
  
## <a name="the-structure-of-a-runtime-directives-file"></a><span data-ttu-id="a24a0-105">Структура файла директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="a24a0-105">The structure of a runtime directives file</span></span>  
 <span data-ttu-id="a24a0-106">Файл директив среды выполнения использует пространство имен `http://schemas.microsoft.com/netfx/2013/01/metadata`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-106">The runtime directives file uses the `http://schemas.microsoft.com/netfx/2013/01/metadata` namespace.</span></span>  
  
 <span data-ttu-id="a24a0-107">Корневой элемент — элемент [Directives](../../../docs/framework/net-native/directives-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="a24a0-107">The root element is the [Directives](../../../docs/framework/net-native/directives-element-net-native.md) element.</span></span> <span data-ttu-id="a24a0-108">Он может содержать ноль или больше элементов [Library](../../../docs/framework/net-native/library-element-net-native.md) и ноль или один элемент [Application](../../../docs/framework/net-native/application-element-net-native.md), как показано в следующей структуре.</span><span class="sxs-lookup"><span data-stu-id="a24a0-108">It can contain zero or more [Library](../../../docs/framework/net-native/library-element-net-native.md) elements, and zero or one [Application](../../../docs/framework/net-native/application-element-net-native.md) element, as shown in the following structure.</span></span> <span data-ttu-id="a24a0-109">Атрибуты элемента [Application](../../../docs/framework/net-native/application-element-net-native.md) могут определять политику отражения среды выполнения для приложения или служить контейнером для дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="a24a0-109">The attributes of the [Application](../../../docs/framework/net-native/application-element-net-native.md) element can define application-wide runtime reflection policy, or it can serve as a container for child elements.</span></span> <span data-ttu-id="a24a0-110">Элемент [Library](../../../docs/framework/net-native/library-element-net-native.md), с другой стороны, это просто контейнер.</span><span class="sxs-lookup"><span data-stu-id="a24a0-110">The [Library](../../../docs/framework/net-native/library-element-net-native.md) element, on the other hand, is simply a container.</span></span> <span data-ttu-id="a24a0-111">Дочерние элементы элементов [Application](../../../docs/framework/net-native/application-element-net-native.md) и [Library](../../../docs/framework/net-native/library-element-net-native.md) определяют типы, методы, поля, свойства и события, доступные для отражения.</span><span class="sxs-lookup"><span data-stu-id="a24a0-111">The children of the [Application](../../../docs/framework/net-native/application-element-net-native.md) and [Library](../../../docs/framework/net-native/library-element-net-native.md) elements define the types, methods, fields, properties, and events that are available for reflection.</span></span>  
  
 <span data-ttu-id="a24a0-112">Для получения справочной информации выберите элементы из приведенной ниже структуры или см. раздел [Элементы директив среды выполнения](../../../docs/framework/net-native/runtime-directive-elements.md).</span><span class="sxs-lookup"><span data-stu-id="a24a0-112">For reference information, choose elements from the following structure or see [Runtime Directive Elements](../../../docs/framework/net-native/runtime-directive-elements.md).</span></span> <span data-ttu-id="a24a0-113">В следующей иерархии многоточие отмечает рекурсивную структуру.</span><span class="sxs-lookup"><span data-stu-id="a24a0-113">In the following hierarchy, the ellipsis marks a recursive structure.</span></span> <span data-ttu-id="a24a0-114">Информация в скобках указывает, является этот элемент необязательным или обязательным, и если он используется, сколько экземпляров (один или несколько) разрешено.</span><span class="sxs-lookup"><span data-stu-id="a24a0-114">The information in brackets indicates whether that element is optional or required, and if it is used, how many instances (one or many) are allowed.</span></span>  
  
 <span data-ttu-id="a24a0-115">[Directives](../../../docs/framework/net-native/directives-element-net-native.md) [1:1]</span><span class="sxs-lookup"><span data-stu-id="a24a0-115">[Directives](../../../docs/framework/net-native/directives-element-net-native.md) [1:1]</span></span>  
 <span data-ttu-id="a24a0-116">[Application](../../../docs/framework/net-native/application-element-net-native.md) [0:1]</span><span class="sxs-lookup"><span data-stu-id="a24a0-116">[Application](../../../docs/framework/net-native/application-element-net-native.md) [0:1]</span></span>  
 <span data-ttu-id="a24a0-117">[Assembly](../../../docs/framework/net-native/assembly-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-117">[Assembly](../../../docs/framework/net-native/assembly-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-118">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-118">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-119">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-119">.</span></span> <span data-ttu-id="a24a0-120">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-120">.</span></span> <span data-ttu-id="a24a0-121">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-121">.</span></span>  
 <span data-ttu-id="a24a0-122">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-122">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-123">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-123">.</span></span> <span data-ttu-id="a24a0-124">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-124">.</span></span> <span data-ttu-id="a24a0-125">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-125">.</span></span>  
 <span data-ttu-id="a24a0-126">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (сконструированного универсального типа) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-126">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="a24a0-127">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-127">.</span></span> <span data-ttu-id="a24a0-128">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-128">.</span></span> <span data-ttu-id="a24a0-129">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-129">.</span></span>  
 <span data-ttu-id="a24a0-130">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-130">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-131">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-131">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-132">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-132">.</span></span> <span data-ttu-id="a24a0-133">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-133">.</span></span> <span data-ttu-id="a24a0-134">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-134">.</span></span>  
 <span data-ttu-id="a24a0-135">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-135">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-136">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-136">.</span></span> <span data-ttu-id="a24a0-137">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-137">.</span></span> <span data-ttu-id="a24a0-138">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-138">.</span></span>  
 <span data-ttu-id="a24a0-139">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (сконструированного универсального типа) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-139">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="a24a0-140">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-140">.</span></span> <span data-ttu-id="a24a0-141">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-141">.</span></span> <span data-ttu-id="a24a0-142">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-142">.</span></span>  
 <span data-ttu-id="a24a0-143">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-143">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-144">[Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md) (подклассы содержащего типа) [O:1]</span><span class="sxs-lookup"><span data-stu-id="a24a0-144">[Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md) (subclasses of the containing type) [O:1]</span></span>  
 <span data-ttu-id="a24a0-145">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-145">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-146">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-146">.</span></span> <span data-ttu-id="a24a0-147">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-147">.</span></span> <span data-ttu-id="a24a0-148">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-148">.</span></span>  
 <span data-ttu-id="a24a0-149">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (сконструированного универсального типа) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-149">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="a24a0-150">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-150">.</span></span> <span data-ttu-id="a24a0-151">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-151">.</span></span> <span data-ttu-id="a24a0-152">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-152">.</span></span>  
 <span data-ttu-id="a24a0-153">[AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md) (содержащий тип является атрибутом) [O:1]</span><span class="sxs-lookup"><span data-stu-id="a24a0-153">[AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md) (containing type is an attribute) [O:1]</span></span>  
 <span data-ttu-id="a24a0-154">[GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-154">[GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-155">[Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-155">[Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-156">[Parameter](../../../docs/framework/net-native/parameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-156">[Parameter](../../../docs/framework/net-native/parameter-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-157">[TypeParameter](../../../docs/framework/net-native/typeparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-157">[TypeParameter](../../../docs/framework/net-native/typeparameter-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-158">[GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-158">[GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-159">[MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md) (сконструированного универсального типа) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-159">[MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>  
 <span data-ttu-id="a24a0-160">[Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-160">[Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-161">[Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-161">[Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-162">[Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-162">[Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-163">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (сконструированного универсального типа) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-163">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="a24a0-164">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-164">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-165">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-165">.</span></span> <span data-ttu-id="a24a0-166">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-166">.</span></span> <span data-ttu-id="a24a0-167">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-167">.</span></span>  
 <span data-ttu-id="a24a0-168">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (сконструированного универсального типа) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-168">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="a24a0-169">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-169">.</span></span> <span data-ttu-id="a24a0-170">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-170">.</span></span> <span data-ttu-id="a24a0-171">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-171">.</span></span>  
 <span data-ttu-id="a24a0-172">[Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-172">[Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-173">[Parameter](../../../docs/framework/net-native/parameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-173">[Parameter](../../../docs/framework/net-native/parameter-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-174">[TypeParameter](../../../docs/framework/net-native/typeparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-174">[TypeParameter](../../../docs/framework/net-native/typeparameter-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-175">[GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-175">[GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-176">[MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md) (сконструированного универсального типа) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-176">[MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>  
 <span data-ttu-id="a24a0-177">[Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-177">[Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-178">[Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-178">[Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-179">[Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-179">[Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-180">[Library](../../../docs/framework/net-native/library-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-180">[Library](../../../docs/framework/net-native/library-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-181">[Assembly](../../../docs/framework/net-native/assembly-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-181">[Assembly](../../../docs/framework/net-native/assembly-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-182">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-182">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-183">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-183">.</span></span> <span data-ttu-id="a24a0-184">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-184">.</span></span> <span data-ttu-id="a24a0-185">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-185">.</span></span>  
 <span data-ttu-id="a24a0-186">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-186">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-187">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-187">.</span></span> <span data-ttu-id="a24a0-188">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-188">.</span></span> <span data-ttu-id="a24a0-189">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-189">.</span></span>  
 <span data-ttu-id="a24a0-190">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (сконструированного универсального типа) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-190">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="a24a0-191">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-191">.</span></span> <span data-ttu-id="a24a0-192">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-192">.</span></span> <span data-ttu-id="a24a0-193">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-193">.</span></span>  
 <span data-ttu-id="a24a0-194">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-194">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-195">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-195">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-196">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-196">.</span></span> <span data-ttu-id="a24a0-197">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-197">.</span></span> <span data-ttu-id="a24a0-198">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-198">.</span></span>  
 <span data-ttu-id="a24a0-199">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-199">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-200">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-200">.</span></span> <span data-ttu-id="a24a0-201">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-201">.</span></span> <span data-ttu-id="a24a0-202">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-202">.</span></span>  
 <span data-ttu-id="a24a0-203">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (сконструированного универсального типа) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-203">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="a24a0-204">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-204">.</span></span> <span data-ttu-id="a24a0-205">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-205">.</span></span> <span data-ttu-id="a24a0-206">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-206">.</span></span>  
 <span data-ttu-id="a24a0-207">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-207">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-208">[Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md) (подклассы содержащего типа) [O:1]</span><span class="sxs-lookup"><span data-stu-id="a24a0-208">[Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md) (subclasses of the containing type) [O:1]</span></span>  
 <span data-ttu-id="a24a0-209">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-209">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-210">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-210">.</span></span> <span data-ttu-id="a24a0-211">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-211">.</span></span> <span data-ttu-id="a24a0-212">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-212">.</span></span>  
 <span data-ttu-id="a24a0-213">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (сконструированного универсального типа) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-213">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="a24a0-214">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-214">.</span></span> <span data-ttu-id="a24a0-215">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-215">.</span></span> <span data-ttu-id="a24a0-216">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-216">.</span></span>  
 <span data-ttu-id="a24a0-217">[AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md) (содержащий тип является атрибутом) [O:1]</span><span class="sxs-lookup"><span data-stu-id="a24a0-217">[AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md) (containing type is an attribute) [O:1]</span></span>  
 <span data-ttu-id="a24a0-218">[GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-218">[GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-219">[Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-219">[Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-220">[MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md) (сконструированного универсального типа) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-220">[MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>  
 <span data-ttu-id="a24a0-221">[Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-221">[Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-222">[Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-222">[Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-223">[Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-223">[Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-224">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (сконструированного универсального типа) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-224">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="a24a0-225">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-225">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-226">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-226">.</span></span> <span data-ttu-id="a24a0-227">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-227">.</span></span> <span data-ttu-id="a24a0-228">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-228">.</span></span>  
 <span data-ttu-id="a24a0-229">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (сконструированного универсального типа) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-229">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="a24a0-230">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-230">.</span></span> <span data-ttu-id="a24a0-231">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-231">.</span></span> <span data-ttu-id="a24a0-232">.</span><span class="sxs-lookup"><span data-stu-id="a24a0-232">.</span></span>  
 <span data-ttu-id="a24a0-233">[Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-233">[Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-234">[MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md) (сконструированного универсального типа) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-234">[MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>  
 <span data-ttu-id="a24a0-235">[Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-235">[Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-236">[Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-236">[Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="a24a0-237">[Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="a24a0-237">[Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M]</span></span>  
  
 <span data-ttu-id="a24a0-238">Элемент [Application](../../../docs/framework/net-native/application-element-net-native.md) может не иметь атрибутов или иметь атрибуты политики, рассмотренные в разделе [Директивы и политика среды выполнения](#Directives).</span><span class="sxs-lookup"><span data-stu-id="a24a0-238">The [Application](../../../docs/framework/net-native/application-element-net-native.md) element can have no attributes, or it can have the policy attributes discussed in the [Runtime directive and policy section](#Directives).</span></span>  
  
 <span data-ttu-id="a24a0-239">Элемент [Library](../../../docs/framework/net-native/library-element-net-native.md) имеет один атрибут `Name`, который определяет имя библиотеки или сборки без расширения файла.</span><span class="sxs-lookup"><span data-stu-id="a24a0-239">A [Library](../../../docs/framework/net-native/library-element-net-native.md) element has a single attribute, `Name`, that specifies the name of a library or assembly, without its file extension.</span></span> <span data-ttu-id="a24a0-240">Например, следующий элемент [Library](../../../docs/framework/net-native/library-element-net-native.md) применяется к сборке с именем Extensions.dll.</span><span class="sxs-lookup"><span data-stu-id="a24a0-240">For example, the following [Library](../../../docs/framework/net-native/library-element-net-native.md) element applies to an assembly named Extensions.dll.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
     <!-- Child elements go here -->    
  </Application>  
  <Library Name="Extensions">  
     <!-- Child elements go here -->    
  </Library>  
</Directives>  
```  
  
<a name="Directives"></a>   
## <a name="runtime-directives-and-policy"></a><span data-ttu-id="a24a0-241">Директивы и политики среды выполнения</span><span class="sxs-lookup"><span data-stu-id="a24a0-241">Runtime directives and policy</span></span>  
 <span data-ttu-id="a24a0-242">Сам элемент [Application](../../../docs/framework/net-native/application-element-net-native.md), а также дочерние элементы элементов [Library](../../../docs/framework/net-native/library-element-net-native.md) и [Application](../../../docs/framework/net-native/application-element-net-native.md) определяют политику, то есть способ, с помощью которого приложение может применять отражение к программному элементу.</span><span class="sxs-lookup"><span data-stu-id="a24a0-242">The [Application](../../../docs/framework/net-native/application-element-net-native.md) element itself and the child elements of the [Library](../../../docs/framework/net-native/library-element-net-native.md) and [Application](../../../docs/framework/net-native/application-element-net-native.md) elements express policy; that is, they define the way in which an app can apply reflection to a program element.</span></span> <span data-ttu-id="a24a0-243">Тип политики определяется с помощью атрибута элемента (например, `Serialize`).</span><span class="sxs-lookup"><span data-stu-id="a24a0-243">The policy type is defined by an attribute of the element (for example, `Serialize`).</span></span> <span data-ttu-id="a24a0-244">Значение политики определяется значением атрибута (например, `Serialize="Required"`).</span><span class="sxs-lookup"><span data-stu-id="a24a0-244">The policy value is defined by the attribute’s value (for example, `Serialize="Required"`).</span></span>  
  
 <span data-ttu-id="a24a0-245">Любая политика, заданная с помощью атрибута элемента применяется ко всем дочерним элементам, которые не определяют значение этой политики.</span><span class="sxs-lookup"><span data-stu-id="a24a0-245">Any policy specified by an attribute of an element applies to all child elements that don’t specify a value for that policy.</span></span> <span data-ttu-id="a24a0-246">Например, если политика определяется элементом [Type](../../../docs/framework/net-native/type-element-net-native.md), эта политика применяется для всех вложенных типов и членов, для которых политика не указана явно.</span><span class="sxs-lookup"><span data-stu-id="a24a0-246">For example, if a policy is specified by a [Type](../../../docs/framework/net-native/type-element-net-native.md) element, that policy applies to all contained types and members for which a policy is not explicitly specified.</span></span>  
  
 <span data-ttu-id="a24a0-247">Политика, которая может быть определена элементами [Application](../../../docs/framework/net-native/application-element-net-native.md), [Assembly](../../../docs/framework/net-native/assembly-element-net-native.md), [AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md), [Namespace](../../../docs/framework/net-native/namespace-element-net-native.md), [Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md) и [Type](../../../docs/framework/net-native/type-element-net-native.md), отличается от политики, которая может быть определена для отдельных членов (элементами [Method](../../../docs/framework/net-native/method-element-net-native.md), [Property](../../../docs/framework/net-native/property-element-net-native.md), [Field](../../../docs/framework/net-native/field-element-net-native.md) и [Event](../../../docs/framework/net-native/event-element-net-native.md)).</span><span class="sxs-lookup"><span data-stu-id="a24a0-247">The policy that can be expressed by the [Application](../../../docs/framework/net-native/application-element-net-native.md), [Assembly](../../../docs/framework/net-native/assembly-element-net-native.md), [AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md), [Namespace](../../../docs/framework/net-native/namespace-element-net-native.md), [Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md), and [Type](../../../docs/framework/net-native/type-element-net-native.md) elements differs from the policy that can be expressed for individual members (by the [Method](../../../docs/framework/net-native/method-element-net-native.md), [Property](../../../docs/framework/net-native/property-element-net-native.md), [Field](../../../docs/framework/net-native/field-element-net-native.md), and [Event](../../../docs/framework/net-native/event-element-net-native.md) elements).</span></span>  
  
### <a name="specifying-policy-for-assemblies-namespaces-and-types"></a><span data-ttu-id="a24a0-248">Задание политики для сборок, пространств имен и типов</span><span class="sxs-lookup"><span data-stu-id="a24a0-248">Specifying policy for assemblies, namespaces, and types</span></span>  
 <span data-ttu-id="a24a0-249">Элементы [Application](../../../docs/framework/net-native/application-element-net-native.md), [Assembly](../../../docs/framework/net-native/assembly-element-net-native.md), [AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md), [Namespace](../../../docs/framework/net-native/namespace-element-net-native.md), [Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md) и [Type](../../../docs/framework/net-native/type-element-net-native.md) поддерживают следующие типы политик:</span><span class="sxs-lookup"><span data-stu-id="a24a0-249">The [Application](../../../docs/framework/net-native/application-element-net-native.md), [Assembly](../../../docs/framework/net-native/assembly-element-net-native.md), [AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md), [Namespace](../../../docs/framework/net-native/namespace-element-net-native.md), [Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md), and [Type](../../../docs/framework/net-native/type-element-net-native.md) elements support the following policy types:</span></span>  
  
-   <span data-ttu-id="a24a0-250">`Activate`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-250">`Activate`.</span></span> <span data-ttu-id="a24a0-251">Управляет доступом среды выполнения к конструкторам для включения активации экземпляров.</span><span class="sxs-lookup"><span data-stu-id="a24a0-251">Controls runtime access to constructors, to enable activation of instances.</span></span>  
  
-   <span data-ttu-id="a24a0-252">`Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-252">`Browse`.</span></span> <span data-ttu-id="a24a0-253">Управляет запросами для получения сведений об элементах программы, но не включает доступ среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="a24a0-253">Controls querying for information about program elements but does not enable any runtime access.</span></span>  
  
-   <span data-ttu-id="a24a0-254">`Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-254">`Dynamic`.</span></span> <span data-ttu-id="a24a0-255">Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.</span><span class="sxs-lookup"><span data-stu-id="a24a0-255">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>  
  
-   <span data-ttu-id="a24a0-256">`Serialize`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-256">`Serialize`.</span></span> <span data-ttu-id="a24a0-257">Управляет доступом среды выполнения к конструкторам, полям и свойствам, позволяющим сериализовать и десериализовать экземпляры типа с помощью таких библиотек сторонних поставщиков, как сериализатор Newtonsoft JSON.</span><span class="sxs-lookup"><span data-stu-id="a24a0-257">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and serialized by third-party libraries such as the Newtonsoft JSON serializer.</span></span>  
  
-   <span data-ttu-id="a24a0-258">`DataContractSerializer`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-258">`DataContractSerializer`.</span></span> <span data-ttu-id="a24a0-259">Определяет политику для сериализации, в которой используется класс <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a24a0-259">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>  
  
-   <span data-ttu-id="a24a0-260">`DataContractJsonSerializer`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-260">`DataContractJsonSerializer`.</span></span> <span data-ttu-id="a24a0-261">Определяет политику для сериализации JSON, в которой используется класс <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a24a0-261">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>  
  
-   <span data-ttu-id="a24a0-262">`XmlSerializer`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-262">`XmlSerializer`.</span></span> <span data-ttu-id="a24a0-263">Определяет политику для сериализации XML, в которой используется класс <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a24a0-263">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>  
  
-   <span data-ttu-id="a24a0-264">`MarshalObject`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-264">`MarshalObject`.</span></span> <span data-ttu-id="a24a0-265">Определяет политику для маршалинга ссылочных типов в WinRT и COM.</span><span class="sxs-lookup"><span data-stu-id="a24a0-265">Controls policy for marshaling reference types to WinRT and COM.</span></span>  
  
-   <span data-ttu-id="a24a0-266">`MarshalDelegate`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-266">`MarshalDelegate`.</span></span> <span data-ttu-id="a24a0-267">Определяет политики для маршалинга типов делегатов как указателей функции на машинный код.</span><span class="sxs-lookup"><span data-stu-id="a24a0-267">Controls policy for marshaling delegate types as function pointers to native code.</span></span>  
  
-   <span data-ttu-id="a24a0-268">`MarshalStructure` .</span><span class="sxs-lookup"><span data-stu-id="a24a0-268">`MarshalStructure` .</span></span> <span data-ttu-id="a24a0-269">Определяет политику для маршалинга структуры в машинный код.</span><span class="sxs-lookup"><span data-stu-id="a24a0-269">Controls policy for marshaling structures to native code.</span></span>  
  
 <span data-ttu-id="a24a0-270">Параметры, связанные с этими типами политики:</span><span class="sxs-lookup"><span data-stu-id="a24a0-270">The settings associated with these policy types are:</span></span>  
  
-   <span data-ttu-id="a24a0-271">`All`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-271">`All`.</span></span> <span data-ttu-id="a24a0-272">Включить политику для всех типов и членов, которые не удаляет цепочка инструментов.</span><span class="sxs-lookup"><span data-stu-id="a24a0-272">Enable the policy for all types and members that the tool chain does not remove.</span></span>  
  
-   <span data-ttu-id="a24a0-273">`Auto`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-273">`Auto`.</span></span> <span data-ttu-id="a24a0-274">Использовать поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a24a0-274">Use the default behavior.</span></span> <span data-ttu-id="a24a0-275">(Отсутствие назначения политики эквивалентно установке политики `Auto`, если только эта политика не переопределяется, например, родительским элементом.)</span><span class="sxs-lookup"><span data-stu-id="a24a0-275">(Not specifying a policy is equivalent to setting that policy to `Auto` unless that policy is overridden, for example by a parent element.)</span></span>  
  
-   <span data-ttu-id="a24a0-276">`Excluded`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-276">`Excluded`.</span></span> <span data-ttu-id="a24a0-277">Выключить политику для программного элемента.</span><span class="sxs-lookup"><span data-stu-id="a24a0-277">Disable the policy for the program element.</span></span>  
  
-   <span data-ttu-id="a24a0-278">`Public`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-278">`Public`.</span></span> <span data-ttu-id="a24a0-279">Включить политику для открытых типов и членов, если только цепочка средство не определяет, что элемент является необязательным и поэтому удаляет его.</span><span class="sxs-lookup"><span data-stu-id="a24a0-279">Enable the policy for public types or members unless the tool chain determines that the member is unnecessary and therefore removes it.</span></span> <span data-ttu-id="a24a0-280">(В последнем случае необходимо использовать `Required Public` чтобы обеспечить сохранение элемента с возможностями отражения.)</span><span class="sxs-lookup"><span data-stu-id="a24a0-280">(In the latter case, you must use `Required Public` to ensure that the member is kept and has reflection capabilities.)</span></span>  
  
-   <span data-ttu-id="a24a0-281">`PublicAndInternal`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-281">`PublicAndInternal`.</span></span> <span data-ttu-id="a24a0-282">Включить политику для открытых и внутренних типов и членов, если цепочка инструментов не удаляет их.</span><span class="sxs-lookup"><span data-stu-id="a24a0-282">Enable the policy for public and internal types or members if the tool chain doesn't remove them.</span></span>  
  
-   <span data-ttu-id="a24a0-283">`Required Public`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-283">`Required Public`.</span></span> <span data-ttu-id="a24a0-284">Требует, чтобы цепочка инструментов поддерживала открытые типы и члены, независимо то того, используются они или нет, и включала для них политику.</span><span class="sxs-lookup"><span data-stu-id="a24a0-284">Require the tool chain to keep public types and members whether or not they are used, and enable the policy for them.</span></span>  
  
-   <span data-ttu-id="a24a0-285">`Required PublicAndInternal`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-285">`Required PublicAndInternal`.</span></span> <span data-ttu-id="a24a0-286">Требует, чтобы цепочка инструментов поддерживала открытые и закрытые типы и члены, независимо то того, используются они или нет, и включала для них политику.</span><span class="sxs-lookup"><span data-stu-id="a24a0-286">Require the tool chain to keep both public and internal types and members whether or not they are used, and enable the policy for them.</span></span>  
  
-   <span data-ttu-id="a24a0-287">`Required All`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-287">`Required All`.</span></span> <span data-ttu-id="a24a0-288">Требует, чтобы цепочка инструментов поддерживала все типы и члены, независимо то того, используются они или нет, и включала для них политику.</span><span class="sxs-lookup"><span data-stu-id="a24a0-288">Require the tool chain to keep all types and members whether or not they are used, and enable the policy for them.</span></span>  
  
 <span data-ttu-id="a24a0-289">Например, следующий файл директив среды выполнения определяет политику для всех типов и членов в сборке DataClasses.dll.</span><span class="sxs-lookup"><span data-stu-id="a24a0-289">For example, the following runtime directives file defines policy for all types and members in the assembly DataClasses.dll.</span></span> <span data-ttu-id="a24a0-290">Он включает отражение для сериализации все открытых свойств, обзор для всех типов и членов типа, активацию для всех типов (из-за атрибута `Dynamic` атрибут), а также отражение для всех открытых типов и членов.</span><span class="sxs-lookup"><span data-stu-id="a24a0-290">It enables reflection for serialization of all public properties, enables browsing for all types and type members, enables activation for all types (because of the `Dynamic` attribute), and enables reflection for all public types and members.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Assembly Name="DataClasses" Serialize="Required Public"   
                Browse="All" Activate="PublicAndInternal"   
                Dynamic="Public"  />  
   </Application>  
   <Library Name="UtilityLibrary">  
     <!-- Child elements go here -->    
   </Library>  
</Directives>  
```  
  
### <a name="specifying-policy-for-members"></a><span data-ttu-id="a24a0-291">Задание политики для членов</span><span class="sxs-lookup"><span data-stu-id="a24a0-291">Specifying policy for members</span></span>  
 <span data-ttu-id="a24a0-292">Элементы [Property](../../../docs/framework/net-native/property-element-net-native.md) и [Field](../../../docs/framework/net-native/field-element-net-native.md) поддерживают следующие типы политик:</span><span class="sxs-lookup"><span data-stu-id="a24a0-292">The [Property](../../../docs/framework/net-native/property-element-net-native.md) and [Field](../../../docs/framework/net-native/field-element-net-native.md) elements support the following policy types:</span></span>  
  
-   <span data-ttu-id="a24a0-293">`Browse` — Управляет запросами для получения сведений о члене, но не включает доступ среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="a24a0-293">`Browse` - Controls querying for information about this member but does not enable any runtime access.</span></span>  
  
-   <span data-ttu-id="a24a0-294">`Dynamic` — Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.</span><span class="sxs-lookup"><span data-stu-id="a24a0-294">`Dynamic` - Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span> <span data-ttu-id="a24a0-295">Также управляет запросами сведений о содержащем типе.</span><span class="sxs-lookup"><span data-stu-id="a24a0-295">Also controls querying for information about the containing type.</span></span>  
  
-   <span data-ttu-id="a24a0-296">`Serialize` — Управляет доступом среды выполнения к членам, позволяющим сериализовать и десериализовать экземпляры типа с помощью таких библиотек, как, например, сериализатор Newtonsoft JSON.</span><span class="sxs-lookup"><span data-stu-id="a24a0-296">`Serialize` - Controls runtime access to the member to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span> <span data-ttu-id="a24a0-297">Эта политика может применяться для конструкторов, полей и свойств.</span><span class="sxs-lookup"><span data-stu-id="a24a0-297">This policy can be applied to constructors, fields, and properties.</span></span>  
  
 <span data-ttu-id="a24a0-298">Элементы [Method](../../../docs/framework/net-native/method-element-net-native.md) и [Event](../../../docs/framework/net-native/event-element-net-native.md) поддерживают следующие типы политик:</span><span class="sxs-lookup"><span data-stu-id="a24a0-298">The [Method](../../../docs/framework/net-native/method-element-net-native.md) and [Event](../../../docs/framework/net-native/event-element-net-native.md) elements support the following policy types:</span></span>  
  
-   <span data-ttu-id="a24a0-299">`Browse` — Управляет запросами для получения сведений о члене, но не включает доступ среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="a24a0-299">`Browse` - Controls querying for information about this member but doesn’t enable any runtime access.</span></span>  
  
-   <span data-ttu-id="a24a0-300">`Dynamic` — Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.</span><span class="sxs-lookup"><span data-stu-id="a24a0-300">`Dynamic` - Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span> <span data-ttu-id="a24a0-301">Также управляет запросами сведений о содержащем типе.</span><span class="sxs-lookup"><span data-stu-id="a24a0-301">Also controls querying for information about the containing type.</span></span>  
  
 <span data-ttu-id="a24a0-302">Параметры, связанные с этими типами политики:</span><span class="sxs-lookup"><span data-stu-id="a24a0-302">The settings associated with these policy types are:</span></span>  
  
-   <span data-ttu-id="a24a0-303">`Auto` — Использовать поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a24a0-303">`Auto` - Use the default behavior.</span></span> <span data-ttu-id="a24a0-304">(Отсутствие назначения политики эквивалентно установке политики `Auto`, если только что-то ее не переопределяет.)</span><span class="sxs-lookup"><span data-stu-id="a24a0-304">(Not specifying a policy is equivalent to setting that policy to `Auto` unless something overrides it.)</span></span>  
  
-   <span data-ttu-id="a24a0-305">`Excluded` — никогда не включать метаданные для члена.</span><span class="sxs-lookup"><span data-stu-id="a24a0-305">`Excluded` - Never include metadata for the member.</span></span>  
  
-   <span data-ttu-id="a24a0-306">`Included`- включить политику, если родительский тип присутствует в выходных данных.</span><span class="sxs-lookup"><span data-stu-id="a24a0-306">`Included` - Enable the policy if the parent type is present in the output.</span></span>  
  
-   <span data-ttu-id="a24a0-307">`Required` — Требует, чтобы цепочка инструментов поддерживала этот член, даже если он не используется, и включала для него политику.</span><span class="sxs-lookup"><span data-stu-id="a24a0-307">`Required` - Require the tool chain to keep this member even if appears to be unused, and enable policy for it.</span></span>  
  
## <a name="runtime-directives-file-semantics"></a><span data-ttu-id="a24a0-308">Семантика файла директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="a24a0-308">Runtime directives file semantics</span></span>  
 <span data-ttu-id="a24a0-309">Политики могут быть определены одновременно для элементов более высокого уровня и более низкого уровня.</span><span class="sxs-lookup"><span data-stu-id="a24a0-309">Policy can be defined simultaneously for both higher-level and lower-level elements.</span></span> <span data-ttu-id="a24a0-310">Например, можно определить политики для сборки, а также для некоторых типов, содержащегося в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="a24a0-310">For example, policy can be defined for an assembly, and for some of the types contained in that assembly.</span></span> <span data-ttu-id="a24a0-311">Если конкретный элемент нижнего уровня не представлен, он наследует политику родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="a24a0-311">If a particular lower-level element is not represented, it inherits the policy of its parent.</span></span> <span data-ttu-id="a24a0-312">Например, если элемент `Assembly` присутствует, а элементы `Type` нет, то политика, указанная в элементе `Assembly`, применяется для каждого типа в сборке.</span><span class="sxs-lookup"><span data-stu-id="a24a0-312">For example, if an `Assembly` element is present but `Type` elements are not, the policy specified in the `Assembly` element applies to each type in the assembly.</span></span> <span data-ttu-id="a24a0-313">Несколько элементов могут также применить политику к одному и тому же программному элементу.</span><span class="sxs-lookup"><span data-stu-id="a24a0-313">Multiple elements can also apply policy to the same program element.</span></span> <span data-ttu-id="a24a0-314">Например, отдельные элементы [Assembly](../../../docs/framework/net-native/assembly-element-net-native.md) могут определять один и тот же элемент политики для одной сборки по-разному.</span><span class="sxs-lookup"><span data-stu-id="a24a0-314">For example, separate [Assembly](../../../docs/framework/net-native/assembly-element-net-native.md) elements might define the same policy element for the same assembly differently.</span></span> <span data-ttu-id="a24a0-315">В следующих разделах объясняется, как политики для конкретного типа разрешается в таких случаях.</span><span class="sxs-lookup"><span data-stu-id="a24a0-315">The following sections explain how the policy for a particular type is resolved in those cases.</span></span>  
  
 <span data-ttu-id="a24a0-316">Элемент [Type](../../../docs/framework/net-native/type-element-net-native.md) или [Method](../../../docs/framework/net-native/method-element-net-native.md) универсального типа или метода применяет свою политику для всех экземпляров, которые не имеют собственной политики.</span><span class="sxs-lookup"><span data-stu-id="a24a0-316">A [Type](../../../docs/framework/net-native/type-element-net-native.md) or [Method](../../../docs/framework/net-native/method-element-net-native.md) element of a generic type or method applies its policy to all instantiations that do not have their own policy.</span></span> <span data-ttu-id="a24a0-317">Например, элемент `Type`, который определяет политику для <xref:System.Collections.Generic.List%601>, применяется для всех сконструированных экземпляров универсального типа, если только он переопределяется для определенного сконструированного универсального типа (например, `List<Int32>`) элементом `TypeInstantiation` .</span><span class="sxs-lookup"><span data-stu-id="a24a0-317">For example, a `Type` element that specifies policy for <xref:System.Collections.Generic.List%601> applies to all constructed instances of that generic type, unless it's overridden for a particular constructed generic type (such as a `List<Int32>`) by a `TypeInstantiation` element.</span></span> <span data-ttu-id="a24a0-318">В противном случае, элементы определяют политику для именованного программного элемента.</span><span class="sxs-lookup"><span data-stu-id="a24a0-318">Otherwise, elements define policy for the program element named.</span></span>  
  
 <span data-ttu-id="a24a0-319">Если элемент является неоднозначным, ядро ищет совпадения и при обнаружении точного совпадения, будет ее использовать.</span><span class="sxs-lookup"><span data-stu-id="a24a0-319">When an element is ambiguous, the engine looks for matches, and if it finds an exact match, it will use it.</span></span> <span data-ttu-id="a24a0-320">При обнаружении нескольких совпадений будет предупреждение или ошибка.</span><span class="sxs-lookup"><span data-stu-id="a24a0-320">If it finds multiple matches, there will be a warning or error.</span></span>  
  
### <a name="if-two-directives-apply-policy-to-the-same-program-element"></a><span data-ttu-id="a24a0-321">Если две директивы применяют политику к одному и тому же программному элементу</span><span class="sxs-lookup"><span data-stu-id="a24a0-321">If two directives apply policy to the same program element</span></span>  
 <span data-ttu-id="a24a0-322">Если два элемента в разных файлах директив среды выполнения пытаются установить один и тот же тип политики для одного программного элемента (например, сборки или типа) в разные значения, конфликт разрешается следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a24a0-322">If two elements in different runtime directives files try to set the same policy type for the same program element (such as an assembly or type) to different values, the conflict is resolved as follows:</span></span>  
  
1.  <span data-ttu-id="a24a0-323">Если элемент `Excluded` присутствует, он имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="a24a0-323">If the `Excluded` element is present, it has precedence.</span></span>  
  
2.  <span data-ttu-id="a24a0-324">`Required`имеет приоритет над не `Required`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-324">`Required` has precedence over not `Required`.</span></span>  
  
3.  <span data-ttu-id="a24a0-325">`All`имеет приоритет перед `PublicAndInternal`, который имеет приоритет над `Public`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-325">`All` has precedence over `PublicAndInternal`, which has precedence over `Public`.</span></span>  
  
4.  <span data-ttu-id="a24a0-326">Любой явный параметр имеет приоритет над `Auto`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-326">Any explicit setting has precedence over `Auto`.</span></span>  
  
 <span data-ttu-id="a24a0-327">Например, если один проект включает следующие два файла директив среды выполнения, устанавливается политика сериализации для DataClasses.dll на `Required Public` и `All`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-327">For example, if a single project includes the following two runtime directives files, the serialization policy for DataClasses.dll is set to both `Required Public` and `All`.</span></span> <span data-ttu-id="a24a0-328">В этом случае политика сериализации будет разрешаться как `Required All`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-328">In this case, the serialization policy would be resolved as `Required All`.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Assembly Name="DataClasses" Serialize="Required Public"/>  
   </Application>  
   <Library Name="DataClasses">  
      <!-- any other elements -->  
   </Library>  
</Directives>  
```  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Assembly Name="DataClasses" Serialize="All" />  
   </Application>  
   <Library Name="DataClasses">  
      <!-- any other elements -->  
   </Library>  
</Directives>  
```  
  
 <span data-ttu-id="a24a0-329">Однако, если две директивы в файле директив среды выполнения пытаются задать один и тот же тип политики одному программному элементу, то инструмент определения схемы XML отображает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="a24a0-329">However, if two directives in a single runtime directives file try to set the same policy type for the same program element, the XML Scheme Definition tool displays an error message.</span></span>  
  
### <a name="if-child-and-parent-elements-apply-the-same-policy-type"></a><span data-ttu-id="a24a0-330">Если один и тот же тип политики применяется дочерними и родительскими элементами</span><span class="sxs-lookup"><span data-stu-id="a24a0-330">If child and parent elements apply the same policy type</span></span>  
 <span data-ttu-id="a24a0-331">Дочерние элементы переопределяют свои родительские элементы, в том числе параметр `Excluded`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-331">Child elements override their parent elements, including the `Excluded` setting.</span></span> <span data-ttu-id="a24a0-332">Переопределение — основная причина, по которой требуется указать `Auto`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-332">Overriding is the main reason you would want to specify `Auto`.</span></span>  
  
 <span data-ttu-id="a24a0-333">В следующем примере параметр политики сериализации для значения everything в `DataClasses`, который не находится в`DataClasses.ViewModels`, был бы `Required Public`, а значение everything в `DataClasses` и `DataClasses.ViewModels` было бы `All`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-333">In the following example, the serialization policy setting for everything in `DataClasses` that’s not in `DataClasses.ViewModels` would be `Required Public`, and everything that's in both `DataClasses` and `DataClasses.ViewModels` would be `All`.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Assembly Name="DataClasses" Serialize="Required Public" >  
         <Namespace Name="DataClasses.ViewModels" Seralize="All" />  
      </Assembly>  
   </Appliction>  
   <Library Name="DataClasses">  
      <!-- any other elements -->  
   </Library>  
</Directives>  
```  
  
### <a name="if-open-generics-and-instantiated-elements-apply-the-same-policy-type"></a><span data-ttu-id="a24a0-334">Если открытые универсальные типы и элементы экземпляра применяют один и тот же тип политики</span><span class="sxs-lookup"><span data-stu-id="a24a0-334">If open generics and instantiated elements apply the same policy type</span></span>  
 <span data-ttu-id="a24a0-335">В следующем примере `Dictionary<int,int>` назначается как политика  `Browse`, только если ядро имеет еще одну причину присвоить политику `Browse` (что было бы в противном случае поведением по умолчанию); В каждом экземпляре <xref:System.Collections.Generic.Dictionary%602> все члены будут доступны для просмотра.</span><span class="sxs-lookup"><span data-stu-id="a24a0-335">In the following example, `Dictionary<int,int>` is assigned the `Browse` policy only if the engine has another reason to give it the `Browse` policy (which would otherwise be the default behavior); every other instantiation of <xref:System.Collections.Generic.Dictionary%602> will have all of its members browsable.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Assembly Name="DataClasses" Serialize="Required Public" >  
         <Namespace Name="DataClasses.ViewModels" Seralize="All" />  
      </Assembly>  
      <Namespace Name="DataClasses.Generics" />  
      <Type Name="Dictionary" Browse="All" />  
      <TypeInstantiation Name="Dictionary"   
                         Arguments="System.Int32,System.Int32" Browse="Auto" />  
   </Application>  
   <Library Name="DataClasses">  
      <!-- any other elements -->  
   </Library>  
</Directives>  
```  
  
### <a name="how-policy-is-inferred"></a><span data-ttu-id="a24a0-336">Как определяется политика</span><span class="sxs-lookup"><span data-stu-id="a24a0-336">How policy is inferred</span></span>  
 <span data-ttu-id="a24a0-337">Каждый тип политики имеет разный набор правил, определяющих, как присутствие этого типа политики влияет на другие конструкции.</span><span class="sxs-lookup"><span data-stu-id="a24a0-337">Each policy type has a different set of rules that determine how the presence of that policy type affects other constructs.</span></span>  
  
#### <a name="the-effect-of-browse-policy"></a><span data-ttu-id="a24a0-338">Эффект политики Browse (Просмотр)</span><span class="sxs-lookup"><span data-stu-id="a24a0-338">The effect of Browse policy</span></span>  
 <span data-ttu-id="a24a0-339">Применение политики `Browse` для типа включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="a24a0-339">Applying the `Browse` policy to a type involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="a24a0-340">Базовый тип типа помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-340">The base type of the type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-341">Если экземпляр универсального типа, версия типа без создания экземпляра помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-341">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-342">Если тип является делегатом, метод `Invoke` типа помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-342">If the type is a delegate, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-343">Каждый интерфейс типа помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-343">Each interface of the type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-344">Тип каждого атрибута примененного к типу помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-344">The type of each attribute applied to the type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-345">Если тип является универсальным, каждое ограничение типа помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-345">If the type is generic, each constraint type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-346">Если тип универсален, типы, по которым создается экземпляр типа, помечаются политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-346">If the type is generic, the types over which the type is instantiated are marked with the `Browse` policy.</span></span>  
  
 <span data-ttu-id="a24a0-347">Применение политики `Browse` для метода включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="a24a0-347">Applying the `Browse` policy to a method involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="a24a0-348">Каждый тип параметра метода помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-348">Each parameter type of the method is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-349">Возвращаемый тип метода помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-349">The return type of the method is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-350">Содержащий тип метода помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-350">The containing type of the method is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-351">Если метод является экземпляром универсального метода, универсальный метод без экземпляра помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-351">If the method is an instantiated generic method, the uninstantiated generic method is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-352">Тип каждого атрибута, примененного к методу, помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-352">The type of each attribute applied to the method is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-353">Если метод является универсальным, каждое ограничение типа помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-353">If the method is generic, each constraint type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-354">Если метод универсален, типы, по которым создается экземпляр метода, помечаются политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-354">If the method is generic, the types over which the method is instantiated are marked with the `Browse` policy.</span></span>  
  
 <span data-ttu-id="a24a0-355">Применение политики `Browse` для поля включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="a24a0-355">Applying the `Browse` policy to a field involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="a24a0-356">Тип каждого атрибута, примененного к полю, помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-356">The type of each attribute applied to the field is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-357">Тип поля помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-357">The type of the field is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-358">Тип, к которому принадлежит поле помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-358">The type to which the field belongs is marked with the `Browse` policy.</span></span>  
  
#### <a name="the-effect-of-dynamic-policy"></a><span data-ttu-id="a24a0-359">Эффект политики Dynamic (Динамическая)</span><span class="sxs-lookup"><span data-stu-id="a24a0-359">The effect of Dynamic policy</span></span>  
 <span data-ttu-id="a24a0-360">Применение политики `Dynamic` для типа включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="a24a0-360">Applying the `Dynamic` policy to a type involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="a24a0-361">Базовый тип типа помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-361">The base type of the type is marked with the `Dynamic` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-362">Если экземпляр универсального типа, версия типа без создания экземпляра помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-362">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Dynamic` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-363">Если тип является делегатом, метод `Invoke` типа помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-363">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-364">Каждый интерфейс типа помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-364">Each interface of the type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-365">Тип каждого атрибута примененного к типу помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-365">The type of each attribute applied to the type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-366">Если тип является универсальным, каждое ограничение типа помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-366">If the type is generic, each constraint type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-367">Если тип универсален, типы, по которым создается экземпляр типа, помечаются политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-367">If the type is generic, the types over which the type is instantiated are marked with the `Browse` policy.</span></span>  
  
 <span data-ttu-id="a24a0-368">Применение политики `Dynamic` для метода включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="a24a0-368">Applying the `Dynamic` policy to a method involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="a24a0-369">Каждый тип параметра метода помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-369">Each parameter type of the method is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-370">Возвращаемый тип метода помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-370">The return type of the method is marked with the `Dynamic` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-371">Содержащий тип метода помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-371">The containing type of the method is marked with the `Dynamic` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-372">Если метод является экземпляром универсального метода, универсальный метод без экземпляра помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-372">If the method is an instantiated generic method, the uninstantiated generic method is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-373">Тип каждого атрибута, примененного к методу, помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-373">The type of each attribute applied to the method is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-374">Если метод является универсальным, каждое ограничение типа помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-374">If the method is generic, each constraint type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-375">Если метод универсален, типы, по которым создается экземпляр метода, помечаются политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-375">If the method is generic, the types over which the method is instantiated are marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-376">Этот метод может вызываться `MethodInfo.Invoke`, а создание делегата становится возможным с помощью <xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a24a0-376">The method can be invoked by `MethodInfo.Invoke`, and delegate creation becomes possible by <xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="a24a0-377">Применение политики `Dynamic` для поля включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="a24a0-377">Applying the `Dynamic` policy to a field involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="a24a0-378">Тип каждого атрибута, примененного к полю, помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-378">The type of each attribute applied to the field is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-379">Тип поля помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-379">The type of the field is marked with the `Dynamic` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-380">Тип, к которому принадлежит поле помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-380">The type to which the field belongs is marked with the `Dynamic` policy.</span></span>  
  
#### <a name="the-effect-of-activation-policy"></a><span data-ttu-id="a24a0-381">Эффект от политики Activation (активация)</span><span class="sxs-lookup"><span data-stu-id="a24a0-381">The effect of Activation policy</span></span>  
 <span data-ttu-id="a24a0-382">Применение политики Activation для типа включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="a24a0-382">Applying the Activation policy to a type involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="a24a0-383">Если экземпляр универсального типа, версия типа без создания экземпляра помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-383">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-384">Если тип является делегатом, метод `Invoke` типа помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-384">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-385">Конструкторы типа помечаются политикой `Activation`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-385">Constructors of the type are marked with the `Activation` policy.</span></span>  
  
 <span data-ttu-id="a24a0-386">Применение политики `Activation` для метода включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="a24a0-386">Applying the `Activation` policy to a method involves the following policy change:</span></span>  
  
-   <span data-ttu-id="a24a0-387">Конструктор может вызываться методами <xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> и <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a24a0-387">The constructor can be invoked by the <xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> and <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="a24a0-388">Для методов политика `Activation` оказывает действие только на конструкторы.</span><span class="sxs-lookup"><span data-stu-id="a24a0-388">For methods, the `Activation` policy affects constructors only.</span></span>  
  
 <span data-ttu-id="a24a0-389">Применение политики `Activation` к полю не оказывает влияния.</span><span class="sxs-lookup"><span data-stu-id="a24a0-389">Applying the `Activation` policy to a field has no effect.</span></span>  
  
#### <a name="the-effect-of-serialize-policy"></a><span data-ttu-id="a24a0-390">Эффект политики Serialize (сериализация)</span><span class="sxs-lookup"><span data-stu-id="a24a0-390">The effect of Serialize policy</span></span>  
 <span data-ttu-id="a24a0-391">Политика `Serialize` позволяет использовать общие сериализаторы, основанные на отражении.</span><span class="sxs-lookup"><span data-stu-id="a24a0-391">The `Serialize` policy enables the use of common reflection-based serializers.</span></span> <span data-ttu-id="a24a0-392">Тем не менее, поскольку точные шаблоны доступа к отражению сериализаторов сторонних разработчиков неизвестны Microsoft, эта политика может оказаться не совсем эффективной.</span><span class="sxs-lookup"><span data-stu-id="a24a0-392">However, because the exact reflection access patterns of non-Microsoft serializers are not known to Microsoft, this policy may not be entirely effective.</span></span>  
  
 <span data-ttu-id="a24a0-393">Применение политики `Serialize` для типа включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="a24a0-393">Applying the `Serialize` policy to a type involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="a24a0-394">Базовый тип типа помечается политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-394">The base type of the type is marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-395">Если экземпляр универсального типа, версия типа без создания экземпляра помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-395">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-396">Если тип является делегатом, метод `Invoke` типа помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-396">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-397">Если тип является перечислением, массив типа помечается политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-397">If the type is an enumeration, an array of the type is marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-398">Если тип реализует <xref:System.Collections.Generic.IEnumerable%601>, `T` помечается политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-398">If the type implements <xref:System.Collections.Generic.IEnumerable%601>, `T` is marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-399">Если тип является типом <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.Generic.IList%601>, <xref:System.Collections.Generic.ICollection%601>, <xref:System.Collections.Generic.IReadOnlyCollection%601> или <xref:System.Collections.Generic.IReadOnlyList%601>, тогда `T[]` и <xref:System.Collections.Generic.List%601> помечаются политикой `Serialize`, однако ни один из членов типа интерфейса не помечаются политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-399">If the type is <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.Generic.IList%601>, <xref:System.Collections.Generic.ICollection%601>, <xref:System.Collections.Generic.IReadOnlyCollection%601>, or <xref:System.Collections.Generic.IReadOnlyList%601>, then `T[]` and <xref:System.Collections.Generic.List%601> marked with the `Serialize` policy., but no members of the interface type are marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-400">Если тип является типом <xref:System.Collections.Generic.List%601>, то его члены не помечаются политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-400">If the type is <xref:System.Collections.Generic.List%601>, no members of the type are marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-401">Если тип является типом <xref:System.Collections.Generic.IDictionary%602>, <xref:System.Collections.Generic.Dictionary%602> помечается политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-401">If the type is <xref:System.Collections.Generic.IDictionary%602>, <xref:System.Collections.Generic.Dictionary%602> is marked with the `Serialize` policy.</span></span> <span data-ttu-id="a24a0-402">Но члены типа не помечаются политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-402">but no members of the type are marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-403">Если тип является типом <xref:System.Collections.Generic.Dictionary%602>, то его члены не помечаются политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-403">If the type is <xref:System.Collections.Generic.Dictionary%602>, no members of the type are marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-404">Если тип реализует <xref:System.Collections.Generic.IDictionary%602>, `TKey` и `TValue` помечаются политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-404">If the type implements <xref:System.Collections.Generic.IDictionary%602>, `TKey` and `TValue` are marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-405">Каждый конструктор, каждый метод доступа к свойству и каждое поле помечается политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-405">Each constructor, each property accessor, and each field is marked with the `Serialize` policy.</span></span>  
  
 <span data-ttu-id="a24a0-406">Применение политики `Serialize` для метода включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="a24a0-406">Applying the `Serialize` policy to a method involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="a24a0-407">Содержащий тип помечается политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-407">The containing type is marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-408">Возвращаемый тип метода помечается политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-408">The return type of the method is marked with the `Serialize` policy.</span></span>  
  
 <span data-ttu-id="a24a0-409">Применение политики `Serialize` для поля включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="a24a0-409">Applying the `Serialize` policy to a field involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="a24a0-410">Содержащий тип помечается политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-410">The containing type is marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="a24a0-411">Тип поля помечается политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="a24a0-411">The type of the field is marked with the `Serialize` policy.</span></span>  
  
#### <a name="the-effect-of-xmlserializer-datacontractserializer-and-datacontractjsonserialier-policies"></a><span data-ttu-id="a24a0-412">Эффект политик XmlSerializer, DataContractSerializer и DataContractJsonSerialier</span><span class="sxs-lookup"><span data-stu-id="a24a0-412">The effect of XmlSerializer, DataContractSerializer, and DataContractJsonSerialier policies</span></span>  
 <span data-ttu-id="a24a0-413">В отличие от политики `Serialize`, которая предназначена для сериализаторов на основе отражения, политики `XmlSerializer`, `DataContractSerializer` и `DataContractJsonSerializer` используются для включения набора сериализаторов, известных цепочке инструментов [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a24a0-413">Unlike the `Serialize` policy, which is intended for reflection-based serializers, the `XmlSerializer`, `DataContractSerializer`, and `DataContractJsonSerializer` policies are used to enable a set of serializers that are known to the [!INCLUDE[net_native](../../../includes/net-native-md.md)] tool chain.</span></span> <span data-ttu-id="a24a0-414">Эти сериализаторы не реализуются с помощью отражения, но наборы типов, которые могут быть сериализованы во время выполнения определяются так же, как типы, которые могут отражаться.</span><span class="sxs-lookup"><span data-stu-id="a24a0-414">These serializers are not implemented by using reflection, but the set of types that can be serialized at run time is determined in a similar manner as types that are reflectable.</span></span>  
  
 <span data-ttu-id="a24a0-415">Применение одной из этих политик для типа позволяет сериализовать тип с помощью соответствующего сериализатора.</span><span class="sxs-lookup"><span data-stu-id="a24a0-415">Applying one of these policies to a type enables the type to be serialized with the matching serializer.</span></span> <span data-ttu-id="a24a0-416">Все типы, которые обработчик сериализации может статически определить, как нуждающиеся в сериализации, будут также сериализуемыми.</span><span class="sxs-lookup"><span data-stu-id="a24a0-416">Also, any types that the serialization engine can statically determine as needing serialization will also be serializable.</span></span>  
  
 <span data-ttu-id="a24a0-417">Эти политики не оказывают влияния на методы или поля.</span><span class="sxs-lookup"><span data-stu-id="a24a0-417">These policies have no effect on methods or fields.</span></span>  
  
 <span data-ttu-id="a24a0-418">Подробнее см. в подразделе "Различия в сериализаторах" раздела [Миграция приложения для Магазина Windows в .NET Native](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="a24a0-418">For more information, see the "Differences in Serializers" section in [Migrating Your Windows Store App to .NET Native](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a24a0-419">См. также</span><span class="sxs-lookup"><span data-stu-id="a24a0-419">See Also</span></span>  
 [<span data-ttu-id="a24a0-420">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="a24a0-420">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [<span data-ttu-id="a24a0-421">Отражение и .NET Native</span><span class="sxs-lookup"><span data-stu-id="a24a0-421">Reflection and .NET Native</span></span>](../../../docs/framework/net-native/reflection-and-net-native.md)
