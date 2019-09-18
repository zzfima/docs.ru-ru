---
title: Ссылка на файл конфигурации директив среды выполнения (rd.xml)
ms.date: 03/30/2017
ms.assetid: 8241523f-d8e1-4fb6-bf6a-b29bfe07b38a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: adfc0ae6d9bdae333daacee525c7775acd5a8029
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049141"
---
# <a name="runtime-directives-rdxml-configuration-file-reference"></a><span data-ttu-id="ec59c-102">Ссылка на файл конфигурации директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="ec59c-102">Runtime Directives (rd.xml) Configuration File Reference</span></span>

<span data-ttu-id="ec59c-103">Файл директив среды выполнения (. rd.xml) — это файл конфигурации XML, который определяет, доступны ли элементы в указанной программе для отражения.</span><span class="sxs-lookup"><span data-stu-id="ec59c-103">A runtime directives (.rd.xml) file is an XML configuration file that specifies whether designated program elements are available for reflection.</span></span> <span data-ttu-id="ec59c-104">Ниже приведен пример файла директив среды выполнения:</span><span class="sxs-lookup"><span data-stu-id="ec59c-104">Here’s an example of a runtime directives file:</span></span>

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

## <a name="the-structure-of-a-runtime-directives-file"></a><span data-ttu-id="ec59c-105">Структура файла директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="ec59c-105">The structure of a runtime directives file</span></span>

<span data-ttu-id="ec59c-106">Файл директив среды выполнения использует пространство имен `http://schemas.microsoft.com/netfx/2013/01/metadata`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-106">The runtime directives file uses the `http://schemas.microsoft.com/netfx/2013/01/metadata` namespace.</span></span>

<span data-ttu-id="ec59c-107">Корневой элемент — элемент [Directives](directives-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="ec59c-107">The root element is the [Directives](directives-element-net-native.md) element.</span></span> <span data-ttu-id="ec59c-108">Он может содержать ноль или больше элементов [Library](library-element-net-native.md) и ноль или один элемент [Application](application-element-net-native.md), как показано в следующей структуре.</span><span class="sxs-lookup"><span data-stu-id="ec59c-108">It can contain zero or more [Library](library-element-net-native.md) elements, and zero or one [Application](application-element-net-native.md) element, as shown in the following structure.</span></span> <span data-ttu-id="ec59c-109">Атрибуты элемента [Application](application-element-net-native.md) могут определять политику отражения среды выполнения для приложения или служить контейнером для дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="ec59c-109">The attributes of the [Application](application-element-net-native.md) element can define application-wide runtime reflection policy, or it can serve as a container for child elements.</span></span> <span data-ttu-id="ec59c-110">Элемент [Library](library-element-net-native.md), с другой стороны, это просто контейнер.</span><span class="sxs-lookup"><span data-stu-id="ec59c-110">The [Library](library-element-net-native.md) element, on the other hand, is simply a container.</span></span> <span data-ttu-id="ec59c-111">Дочерние элементы элементов [Application](application-element-net-native.md) и [Library](library-element-net-native.md) определяют типы, методы, поля, свойства и события, доступные для отражения.</span><span class="sxs-lookup"><span data-stu-id="ec59c-111">The children of the [Application](application-element-net-native.md) and [Library](library-element-net-native.md) elements define the types, methods, fields, properties, and events that are available for reflection.</span></span>

<span data-ttu-id="ec59c-112">Для получения справочной информации выберите элементы из приведенной ниже структуры или см. раздел [Элементы директив среды выполнения](runtime-directive-elements.md).</span><span class="sxs-lookup"><span data-stu-id="ec59c-112">For reference information, choose elements from the following structure or see [Runtime Directive Elements](runtime-directive-elements.md).</span></span> <span data-ttu-id="ec59c-113">В следующей иерархии многоточие отмечает рекурсивную структуру.</span><span class="sxs-lookup"><span data-stu-id="ec59c-113">In the following hierarchy, the ellipsis marks a recursive structure.</span></span> <span data-ttu-id="ec59c-114">Информация в скобках указывает, является этот элемент необязательным или обязательным, и если он используется, сколько экземпляров (один или несколько) разрешено.</span><span class="sxs-lookup"><span data-stu-id="ec59c-114">The information in brackets indicates whether that element is optional or required, and if it is used, how many instances (one or many) are allowed.</span></span>

<span data-ttu-id="ec59c-115">[Директивы](directives-element-net-native.md) [1:1] [приложение](application-element-net-native.md) [0:1] [Сборка](assembly-element-net-native.md) [0: m] [пространство имен](namespace-element-net-native.md) [0: m].</span><span class="sxs-lookup"><span data-stu-id="ec59c-115">[Directives](directives-element-net-native.md) [1:1] [Application](application-element-net-native.md) [0:1] [Assembly](assembly-element-net-native.md) [0:M] [Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="ec59c-116">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-116">.</span></span> <span data-ttu-id="ec59c-117">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-117">.</span></span>
<span data-ttu-id="ec59c-118">[Тип](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="ec59c-118">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="ec59c-119">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-119">.</span></span> <span data-ttu-id="ec59c-120">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-120">.</span></span>
<span data-ttu-id="ec59c-121">[TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: M].</span><span class="sxs-lookup"><span data-stu-id="ec59c-121">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="ec59c-122">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-122">.</span></span> <span data-ttu-id="ec59c-123">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-123">.</span></span>
<span data-ttu-id="ec59c-124">[Пространство имен](namespace-element-net-native.md) [0: M] [Пространство имен](namespace-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="ec59c-124">[Namespace](namespace-element-net-native.md) [0:M] [Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="ec59c-125">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-125">.</span></span> <span data-ttu-id="ec59c-126">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-126">.</span></span>
<span data-ttu-id="ec59c-127">[Тип](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="ec59c-127">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="ec59c-128">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-128">.</span></span> <span data-ttu-id="ec59c-129">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-129">.</span></span>
<span data-ttu-id="ec59c-130">[TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: M].</span><span class="sxs-lookup"><span data-stu-id="ec59c-130">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="ec59c-131">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-131">.</span></span> <span data-ttu-id="ec59c-132">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-132">.</span></span>
<span data-ttu-id="ec59c-133">[Тип](type-element-net-native.md) [0: M] [Подтипы](subtypes-element-net-native.md) (подклассов содержащего типа) O:1 [Тип](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="ec59c-133">[Type](type-element-net-native.md) [0:M] [Subtypes](subtypes-element-net-native.md) (subclasses of the containing type) [O:1] [Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="ec59c-134">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-134">.</span></span> <span data-ttu-id="ec59c-135">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-135">.</span></span>
<span data-ttu-id="ec59c-136">[TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: M].</span><span class="sxs-lookup"><span data-stu-id="ec59c-136">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="ec59c-137">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-137">.</span></span> <span data-ttu-id="ec59c-138">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-138">.</span></span>
<span data-ttu-id="ec59c-139">[AttributeImplies](attributeimplies-element-net-native.md) (содержащий тип является атрибутом) O:1 [GenericParameter](genericparameter-element-net-native.md) [0: M] [Метод](method-element-net-native.md) [0: M] [Параметр](parameter-element-net-native.md) [0: M] [Typeparameter находится вне](typeparameter-element-net-native.md) [0: M] [GenericParameter](genericparameter-element-net-native.md) [0: M] [MethodInstantiation](methodinstantiation-element-net-native.md) (сконструированный универсальный метод) [0: M] [Свойство](property-element-net-native.md) [0: M] [Поле](field-element-net-native.md) [0: M] [Событие](event-element-net-native.md) [0: M] [TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: M] [Тип](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="ec59c-139">[AttributeImplies](attributeimplies-element-net-native.md) (containing type is an attribute) [O:1] [GenericParameter](genericparameter-element-net-native.md) [0:M] [Method](method-element-net-native.md) [0:M] [Parameter](parameter-element-net-native.md) [0:M] [TypeParameter](typeparameter-element-net-native.md) [0:M] [GenericParameter](genericparameter-element-net-native.md) [0:M] [MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M] [Property](property-element-net-native.md) [0:M] [Field](field-element-net-native.md) [0:M] [Event](event-element-net-native.md) [0:M] [TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] [Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="ec59c-140">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-140">.</span></span> <span data-ttu-id="ec59c-141">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-141">.</span></span>
<span data-ttu-id="ec59c-142">[TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: M].</span><span class="sxs-lookup"><span data-stu-id="ec59c-142">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="ec59c-143">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-143">.</span></span> <span data-ttu-id="ec59c-144">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-144">.</span></span>
<span data-ttu-id="ec59c-145">[Метод](method-element-net-native.md) [0: M] [Параметр](parameter-element-net-native.md) [0: M] [Typeparameter находится вне](typeparameter-element-net-native.md) [0: M] [GenericParameter](genericparameter-element-net-native.md) [0: M] [MethodInstantiation](methodinstantiation-element-net-native.md) (сконструированный универсальный метод) [0: M] [Свойство](property-element-net-native.md) [0: M] [Поле](field-element-net-native.md) [0: M] [Событие](event-element-net-native.md) [0: M] [Библиотека](library-element-net-native.md) [0: M] [Сборка](assembly-element-net-native.md) [0: M] [Пространство имен](namespace-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="ec59c-145">[Method](method-element-net-native.md) [0:M] [Parameter](parameter-element-net-native.md) [0:M] [TypeParameter](typeparameter-element-net-native.md) [0:M] [GenericParameter](genericparameter-element-net-native.md) [0:M] [MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M] [Property](property-element-net-native.md) [0:M] [Field](field-element-net-native.md) [0:M] [Event](event-element-net-native.md) [0:M] [Library](library-element-net-native.md) [0:M] [Assembly](assembly-element-net-native.md) [0:M] [Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="ec59c-146">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-146">.</span></span> <span data-ttu-id="ec59c-147">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-147">.</span></span>
<span data-ttu-id="ec59c-148">[Тип](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="ec59c-148">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="ec59c-149">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-149">.</span></span> <span data-ttu-id="ec59c-150">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-150">.</span></span>
<span data-ttu-id="ec59c-151">[TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: M].</span><span class="sxs-lookup"><span data-stu-id="ec59c-151">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="ec59c-152">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-152">.</span></span> <span data-ttu-id="ec59c-153">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-153">.</span></span>
<span data-ttu-id="ec59c-154">[Пространство имен](namespace-element-net-native.md) [0: M] [Пространство имен](namespace-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="ec59c-154">[Namespace](namespace-element-net-native.md) [0:M] [Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="ec59c-155">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-155">.</span></span> <span data-ttu-id="ec59c-156">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-156">.</span></span>
<span data-ttu-id="ec59c-157">[Тип](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="ec59c-157">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="ec59c-158">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-158">.</span></span> <span data-ttu-id="ec59c-159">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-159">.</span></span>
<span data-ttu-id="ec59c-160">[TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: M].</span><span class="sxs-lookup"><span data-stu-id="ec59c-160">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="ec59c-161">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-161">.</span></span> <span data-ttu-id="ec59c-162">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-162">.</span></span>
<span data-ttu-id="ec59c-163">[Тип](type-element-net-native.md) [0: M] [Подтипы](subtypes-element-net-native.md) (подклассов содержащего типа) O:1 [Тип](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="ec59c-163">[Type](type-element-net-native.md) [0:M] [Subtypes](subtypes-element-net-native.md) (subclasses of the containing type) [O:1] [Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="ec59c-164">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-164">.</span></span> <span data-ttu-id="ec59c-165">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-165">.</span></span>
<span data-ttu-id="ec59c-166">[TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: M].</span><span class="sxs-lookup"><span data-stu-id="ec59c-166">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="ec59c-167">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-167">.</span></span> <span data-ttu-id="ec59c-168">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-168">.</span></span>
<span data-ttu-id="ec59c-169">[AttributeImplies](attributeimplies-element-net-native.md) (содержащий тип является атрибутом) O:1 [GenericParameter](genericparameter-element-net-native.md) [0: M] [Метод](method-element-net-native.md) [0: M] [MethodInstantiation](methodinstantiation-element-net-native.md) (сконструированный универсальный метод) [0: M] [Свойство](property-element-net-native.md) [0: M] [Поле](field-element-net-native.md) [0: M] [Событие](event-element-net-native.md) [0: M] [TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: M] [Тип](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="ec59c-169">[AttributeImplies](attributeimplies-element-net-native.md) (containing type is an attribute) [O:1] [GenericParameter](genericparameter-element-net-native.md) [0:M] [Method](method-element-net-native.md) [0:M] [MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M] [Property](property-element-net-native.md) [0:M] [Field](field-element-net-native.md) [0:M] [Event](event-element-net-native.md) [0:M] [TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] [Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="ec59c-170">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-170">.</span></span> <span data-ttu-id="ec59c-171">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-171">.</span></span>
<span data-ttu-id="ec59c-172">[TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: M].</span><span class="sxs-lookup"><span data-stu-id="ec59c-172">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="ec59c-173">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-173">.</span></span> <span data-ttu-id="ec59c-174">.</span><span class="sxs-lookup"><span data-stu-id="ec59c-174">.</span></span>
<span data-ttu-id="ec59c-175">[Метод](method-element-net-native.md) [0: M] [MethodInstantiation](methodinstantiation-element-net-native.md) (сконструированный универсальный метод) [0: M] [Свойство](property-element-net-native.md) [0: M] [Поле](field-element-net-native.md) [0: M] [Событие](event-element-net-native.md) [0: M]</span><span class="sxs-lookup"><span data-stu-id="ec59c-175">[Method](method-element-net-native.md) [0:M] [MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M] [Property](property-element-net-native.md) [0:M] [Field](field-element-net-native.md) [0:M] [Event](event-element-net-native.md) [0:M]</span></span>

<span data-ttu-id="ec59c-176">Элемент [Application](application-element-net-native.md) может не иметь атрибутов или иметь атрибуты политики, рассмотренные в разделе [Директивы и политика среды выполнения](#Directives).</span><span class="sxs-lookup"><span data-stu-id="ec59c-176">The [Application](application-element-net-native.md) element can have no attributes, or it can have the policy attributes discussed in the [Runtime directive and policy section](#Directives).</span></span>

<span data-ttu-id="ec59c-177">Элемент [Library](library-element-net-native.md) имеет один атрибут `Name`, который определяет имя библиотеки или сборки без расширения файла.</span><span class="sxs-lookup"><span data-stu-id="ec59c-177">A [Library](library-element-net-native.md) element has a single attribute, `Name`, that specifies the name of a library or assembly, without its file extension.</span></span> <span data-ttu-id="ec59c-178">Например, следующий элемент [Library](library-element-net-native.md) применяется к сборке с именем Extensions.dll.</span><span class="sxs-lookup"><span data-stu-id="ec59c-178">For example, the following [Library](library-element-net-native.md) element applies to an assembly named Extensions.dll.</span></span>

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

## <a name="runtime-directives-and-policy"></a><span data-ttu-id="ec59c-179">Директивы и политики среды выполнения</span><span class="sxs-lookup"><span data-stu-id="ec59c-179">Runtime directives and policy</span></span>

<span data-ttu-id="ec59c-180">Сам элемент [Application](application-element-net-native.md), а также дочерние элементы элементов [Library](library-element-net-native.md) и [Application](application-element-net-native.md) определяют политику, то есть способ, с помощью которого приложение может применять отражение к программному элементу.</span><span class="sxs-lookup"><span data-stu-id="ec59c-180">The [Application](application-element-net-native.md) element itself and the child elements of the [Library](library-element-net-native.md) and [Application](application-element-net-native.md) elements express policy; that is, they define the way in which an app can apply reflection to a program element.</span></span> <span data-ttu-id="ec59c-181">Тип политики определяется с помощью атрибута элемента (например, `Serialize`).</span><span class="sxs-lookup"><span data-stu-id="ec59c-181">The policy type is defined by an attribute of the element (for example, `Serialize`).</span></span> <span data-ttu-id="ec59c-182">Значение политики определяется значением атрибута (например, `Serialize="Required"`).</span><span class="sxs-lookup"><span data-stu-id="ec59c-182">The policy value is defined by the attribute’s value (for example, `Serialize="Required"`).</span></span>

<span data-ttu-id="ec59c-183">Любая политика, заданная с помощью атрибута элемента применяется ко всем дочерним элементам, которые не определяют значение этой политики.</span><span class="sxs-lookup"><span data-stu-id="ec59c-183">Any policy specified by an attribute of an element applies to all child elements that don’t specify a value for that policy.</span></span> <span data-ttu-id="ec59c-184">Например, если политика определяется элементом [Type](type-element-net-native.md), эта политика применяется для всех вложенных типов и членов, для которых политика не указана явно.</span><span class="sxs-lookup"><span data-stu-id="ec59c-184">For example, if a policy is specified by a [Type](type-element-net-native.md) element, that policy applies to all contained types and members for which a policy is not explicitly specified.</span></span>

<span data-ttu-id="ec59c-185">Политика, которая может быть определена элементами [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md) и [Type](type-element-net-native.md), отличается от политики, которая может быть определена для отдельных членов (элементами [Method](method-element-net-native.md), [Property](property-element-net-native.md), [Field](field-element-net-native.md) и [Event](event-element-net-native.md)).</span><span class="sxs-lookup"><span data-stu-id="ec59c-185">The policy that can be expressed by the [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md), and [Type](type-element-net-native.md) elements differs from the policy that can be expressed for individual members (by the [Method](method-element-net-native.md), [Property](property-element-net-native.md), [Field](field-element-net-native.md), and [Event](event-element-net-native.md) elements).</span></span>

### <a name="specifying-policy-for-assemblies-namespaces-and-types"></a><span data-ttu-id="ec59c-186">Задание политики для сборок, пространств имен и типов</span><span class="sxs-lookup"><span data-stu-id="ec59c-186">Specifying policy for assemblies, namespaces, and types</span></span>

<span data-ttu-id="ec59c-187">Элементы [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md) и [Type](type-element-net-native.md) поддерживают следующие типы политик:</span><span class="sxs-lookup"><span data-stu-id="ec59c-187">The [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md), and [Type](type-element-net-native.md) elements support the following policy types:</span></span>

- <span data-ttu-id="ec59c-188">`Activate`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-188">`Activate`.</span></span> <span data-ttu-id="ec59c-189">Управляет доступом среды выполнения к конструкторам для включения активации экземпляров.</span><span class="sxs-lookup"><span data-stu-id="ec59c-189">Controls runtime access to constructors, to enable activation of instances.</span></span>

- <span data-ttu-id="ec59c-190">`Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-190">`Browse`.</span></span> <span data-ttu-id="ec59c-191">Управляет запросами для получения сведений об элементах программы, но не включает доступ среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="ec59c-191">Controls querying for information about program elements but does not enable any runtime access.</span></span>

- <span data-ttu-id="ec59c-192">`Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-192">`Dynamic`.</span></span> <span data-ttu-id="ec59c-193">Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.</span><span class="sxs-lookup"><span data-stu-id="ec59c-193">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>

- <span data-ttu-id="ec59c-194">`Serialize`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-194">`Serialize`.</span></span> <span data-ttu-id="ec59c-195">Управляет доступом среды выполнения к конструкторам, полям и свойствам, позволяющим сериализовать и десериализовать экземпляры типа с помощью таких библиотек сторонних поставщиков, как сериализатор Newtonsoft JSON.</span><span class="sxs-lookup"><span data-stu-id="ec59c-195">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and serialized by third-party libraries such as the Newtonsoft JSON serializer.</span></span>

- <span data-ttu-id="ec59c-196">`DataContractSerializer`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-196">`DataContractSerializer`.</span></span> <span data-ttu-id="ec59c-197">Определяет политику для сериализации, в которой используется класс <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ec59c-197">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>

- <span data-ttu-id="ec59c-198">`DataContractJsonSerializer`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-198">`DataContractJsonSerializer`.</span></span> <span data-ttu-id="ec59c-199">Определяет политику для сериализации JSON, в которой используется класс <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ec59c-199">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>

- <span data-ttu-id="ec59c-200">`XmlSerializer`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-200">`XmlSerializer`.</span></span> <span data-ttu-id="ec59c-201">Определяет политику для сериализации XML, в которой используется класс <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ec59c-201">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>

- <span data-ttu-id="ec59c-202">`MarshalObject`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-202">`MarshalObject`.</span></span> <span data-ttu-id="ec59c-203">Определяет политику для маршалинга ссылочных типов в WinRT и COM.</span><span class="sxs-lookup"><span data-stu-id="ec59c-203">Controls policy for marshaling reference types to WinRT and COM.</span></span>

- <span data-ttu-id="ec59c-204">`MarshalDelegate`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-204">`MarshalDelegate`.</span></span> <span data-ttu-id="ec59c-205">Определяет политики для маршалинга типов делегатов как указателей функции на машинный код.</span><span class="sxs-lookup"><span data-stu-id="ec59c-205">Controls policy for marshaling delegate types as function pointers to native code.</span></span>

- <span data-ttu-id="ec59c-206">`MarshalStructure` .</span><span class="sxs-lookup"><span data-stu-id="ec59c-206">`MarshalStructure` .</span></span> <span data-ttu-id="ec59c-207">Определяет политику для маршалинга структуры в машинный код.</span><span class="sxs-lookup"><span data-stu-id="ec59c-207">Controls policy for marshaling structures to native code.</span></span>

<span data-ttu-id="ec59c-208">Параметры, связанные с этими типами политики:</span><span class="sxs-lookup"><span data-stu-id="ec59c-208">The settings associated with these policy types are:</span></span>

- <span data-ttu-id="ec59c-209">`All`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-209">`All`.</span></span> <span data-ttu-id="ec59c-210">Включить политику для всех типов и членов, которые не удаляет цепочка инструментов.</span><span class="sxs-lookup"><span data-stu-id="ec59c-210">Enable the policy for all types and members that the tool chain does not remove.</span></span>

- <span data-ttu-id="ec59c-211">`Auto`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-211">`Auto`.</span></span> <span data-ttu-id="ec59c-212">Использовать поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ec59c-212">Use the default behavior.</span></span> <span data-ttu-id="ec59c-213">(Отсутствие назначения политики эквивалентно установке политики `Auto`, если только эта политика не переопределяется, например, родительским элементом.)</span><span class="sxs-lookup"><span data-stu-id="ec59c-213">(Not specifying a policy is equivalent to setting that policy to `Auto` unless that policy is overridden, for example by a parent element.)</span></span>

- <span data-ttu-id="ec59c-214">`Excluded`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-214">`Excluded`.</span></span> <span data-ttu-id="ec59c-215">Выключить политику для программного элемента.</span><span class="sxs-lookup"><span data-stu-id="ec59c-215">Disable the policy for the program element.</span></span>

- <span data-ttu-id="ec59c-216">`Public`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-216">`Public`.</span></span> <span data-ttu-id="ec59c-217">Включить политику для открытых типов и членов, если только цепочка средство не определяет, что элемент является необязательным и поэтому удаляет его.</span><span class="sxs-lookup"><span data-stu-id="ec59c-217">Enable the policy for public types or members unless the tool chain determines that the member is unnecessary and therefore removes it.</span></span> <span data-ttu-id="ec59c-218">(В последнем случае необходимо использовать `Required Public` чтобы обеспечить сохранение элемента с возможностями отражения.)</span><span class="sxs-lookup"><span data-stu-id="ec59c-218">(In the latter case, you must use `Required Public` to ensure that the member is kept and has reflection capabilities.)</span></span>

- <span data-ttu-id="ec59c-219">`PublicAndInternal`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-219">`PublicAndInternal`.</span></span> <span data-ttu-id="ec59c-220">Включить политику для открытых и внутренних типов и членов, если цепочка инструментов не удаляет их.</span><span class="sxs-lookup"><span data-stu-id="ec59c-220">Enable the policy for public and internal types or members if the tool chain doesn't remove them.</span></span>

- <span data-ttu-id="ec59c-221">`Required Public`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-221">`Required Public`.</span></span> <span data-ttu-id="ec59c-222">Требует, чтобы цепочка инструментов поддерживала открытые типы и члены, независимо то того, используются они или нет, и включала для них политику.</span><span class="sxs-lookup"><span data-stu-id="ec59c-222">Require the tool chain to keep public types and members whether or not they are used, and enable the policy for them.</span></span>

- <span data-ttu-id="ec59c-223">`Required PublicAndInternal`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-223">`Required PublicAndInternal`.</span></span> <span data-ttu-id="ec59c-224">Требует, чтобы цепочка инструментов поддерживала открытые и закрытые типы и члены, независимо то того, используются они или нет, и включала для них политику.</span><span class="sxs-lookup"><span data-stu-id="ec59c-224">Require the tool chain to keep both public and internal types and members whether or not they are used, and enable the policy for them.</span></span>

- <span data-ttu-id="ec59c-225">`Required All`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-225">`Required All`.</span></span> <span data-ttu-id="ec59c-226">Требует, чтобы цепочка инструментов поддерживала все типы и члены, независимо то того, используются они или нет, и включала для них политику.</span><span class="sxs-lookup"><span data-stu-id="ec59c-226">Require the tool chain to keep all types and members whether or not they are used, and enable the policy for them.</span></span>

<span data-ttu-id="ec59c-227">Например, следующий файл директив среды выполнения определяет политику для всех типов и членов в сборке DataClasses.dll.</span><span class="sxs-lookup"><span data-stu-id="ec59c-227">For example, the following runtime directives file defines policy for all types and members in the assembly DataClasses.dll.</span></span> <span data-ttu-id="ec59c-228">Он включает отражение для сериализации все открытых свойств, обзор для всех типов и членов типа, активацию для всех типов (из-за атрибута `Dynamic` атрибут), а также отражение для всех открытых типов и членов.</span><span class="sxs-lookup"><span data-stu-id="ec59c-228">It enables reflection for serialization of all public properties, enables browsing for all types and type members, enables activation for all types (because of the `Dynamic` attribute), and enables reflection for all public types and members.</span></span>

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

### <a name="specifying-policy-for-members"></a><span data-ttu-id="ec59c-229">Задание политики для членов</span><span class="sxs-lookup"><span data-stu-id="ec59c-229">Specifying policy for members</span></span>

<span data-ttu-id="ec59c-230">Элементы [Property](property-element-net-native.md) и [Field](field-element-net-native.md) поддерживают следующие типы политик:</span><span class="sxs-lookup"><span data-stu-id="ec59c-230">The [Property](property-element-net-native.md) and [Field](field-element-net-native.md) elements support the following policy types:</span></span>

- <span data-ttu-id="ec59c-231">`Browse` — Управляет запросами для получения сведений о члене, но не включает доступ среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="ec59c-231">`Browse` - Controls querying for information about this member but does not enable any runtime access.</span></span>

- <span data-ttu-id="ec59c-232">`Dynamic` — Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.</span><span class="sxs-lookup"><span data-stu-id="ec59c-232">`Dynamic` - Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span> <span data-ttu-id="ec59c-233">Также управляет запросами сведений о содержащем типе.</span><span class="sxs-lookup"><span data-stu-id="ec59c-233">Also controls querying for information about the containing type.</span></span>

- <span data-ttu-id="ec59c-234">`Serialize` — Управляет доступом среды выполнения к членам, позволяющим сериализовать и десериализовать экземпляры типа с помощью таких библиотек, как, например, сериализатор Newtonsoft JSON.</span><span class="sxs-lookup"><span data-stu-id="ec59c-234">`Serialize` - Controls runtime access to the member to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span> <span data-ttu-id="ec59c-235">Эта политика может применяться для конструкторов, полей и свойств.</span><span class="sxs-lookup"><span data-stu-id="ec59c-235">This policy can be applied to constructors, fields, and properties.</span></span>

<span data-ttu-id="ec59c-236">Элементы [Method](method-element-net-native.md) и [Event](event-element-net-native.md) поддерживают следующие типы политик:</span><span class="sxs-lookup"><span data-stu-id="ec59c-236">The [Method](method-element-net-native.md) and [Event](event-element-net-native.md) elements support the following policy types:</span></span>

- <span data-ttu-id="ec59c-237">`Browse` — Управляет запросами для получения сведений о члене, но не включает доступ среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="ec59c-237">`Browse` - Controls querying for information about this member but doesn’t enable any runtime access.</span></span>

- <span data-ttu-id="ec59c-238">`Dynamic` — Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.</span><span class="sxs-lookup"><span data-stu-id="ec59c-238">`Dynamic` - Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span> <span data-ttu-id="ec59c-239">Также управляет запросами сведений о содержащем типе.</span><span class="sxs-lookup"><span data-stu-id="ec59c-239">Also controls querying for information about the containing type.</span></span>

 <span data-ttu-id="ec59c-240">Параметры, связанные с этими типами политики:</span><span class="sxs-lookup"><span data-stu-id="ec59c-240">The settings associated with these policy types are:</span></span>

- <span data-ttu-id="ec59c-241">`Auto` — Использовать поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ec59c-241">`Auto` - Use the default behavior.</span></span> <span data-ttu-id="ec59c-242">(Отсутствие назначения политики эквивалентно установке политики `Auto`, если только что-то ее не переопределяет.)</span><span class="sxs-lookup"><span data-stu-id="ec59c-242">(Not specifying a policy is equivalent to setting that policy to `Auto` unless something overrides it.)</span></span>

- <span data-ttu-id="ec59c-243">`Excluded` — никогда не включать метаданные для члена.</span><span class="sxs-lookup"><span data-stu-id="ec59c-243">`Excluded` - Never include metadata for the member.</span></span>

- <span data-ttu-id="ec59c-244">`Included`- включить политику, если родительский тип присутствует в выходных данных.</span><span class="sxs-lookup"><span data-stu-id="ec59c-244">`Included` - Enable the policy if the parent type is present in the output.</span></span>

- <span data-ttu-id="ec59c-245">`Required` — Требует, чтобы цепочка инструментов поддерживала этот член, даже если он не используется, и включала для него политику.</span><span class="sxs-lookup"><span data-stu-id="ec59c-245">`Required` - Require the tool chain to keep this member even if appears to be unused, and enable policy for it.</span></span>

## <a name="runtime-directives-file-semantics"></a><span data-ttu-id="ec59c-246">Семантика файла директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="ec59c-246">Runtime directives file semantics</span></span>

<span data-ttu-id="ec59c-247">Политики могут быть определены одновременно для элементов более высокого уровня и более низкого уровня.</span><span class="sxs-lookup"><span data-stu-id="ec59c-247">Policy can be defined simultaneously for both higher-level and lower-level elements.</span></span> <span data-ttu-id="ec59c-248">Например, можно определить политики для сборки, а также для некоторых типов, содержащегося в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="ec59c-248">For example, policy can be defined for an assembly, and for some of the types contained in that assembly.</span></span> <span data-ttu-id="ec59c-249">Если конкретный элемент нижнего уровня не представлен, он наследует политику родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="ec59c-249">If a particular lower-level element is not represented, it inherits the policy of its parent.</span></span> <span data-ttu-id="ec59c-250">Например, если элемент `Assembly` присутствует, а элементы `Type` нет, то политика, указанная в элементе `Assembly`, применяется для каждого типа в сборке.</span><span class="sxs-lookup"><span data-stu-id="ec59c-250">For example, if an `Assembly` element is present but `Type` elements are not, the policy specified in the `Assembly` element applies to each type in the assembly.</span></span> <span data-ttu-id="ec59c-251">Несколько элементов могут также применить политику к одному и тому же программному элементу.</span><span class="sxs-lookup"><span data-stu-id="ec59c-251">Multiple elements can also apply policy to the same program element.</span></span> <span data-ttu-id="ec59c-252">Например, отдельные элементы [Assembly](assembly-element-net-native.md) могут определять один и тот же элемент политики для одной сборки по-разному.</span><span class="sxs-lookup"><span data-stu-id="ec59c-252">For example, separate [Assembly](assembly-element-net-native.md) elements might define the same policy element for the same assembly differently.</span></span> <span data-ttu-id="ec59c-253">В следующих разделах объясняется, как политики для конкретного типа разрешается в таких случаях.</span><span class="sxs-lookup"><span data-stu-id="ec59c-253">The following sections explain how the policy for a particular type is resolved in those cases.</span></span>

<span data-ttu-id="ec59c-254">Элемент [Type](type-element-net-native.md) или [Method](method-element-net-native.md) универсального типа или метода применяет свою политику для всех экземпляров, которые не имеют собственной политики.</span><span class="sxs-lookup"><span data-stu-id="ec59c-254">A [Type](type-element-net-native.md) or [Method](method-element-net-native.md) element of a generic type or method applies its policy to all instantiations that do not have their own policy.</span></span> <span data-ttu-id="ec59c-255">Например, элемент `Type`, который определяет политику для <xref:System.Collections.Generic.List%601>, применяется для всех сконструированных экземпляров универсального типа, если только он переопределяется для определенного сконструированного универсального типа (например, `List<Int32>`) элементом `TypeInstantiation` .</span><span class="sxs-lookup"><span data-stu-id="ec59c-255">For example, a `Type` element that specifies policy for <xref:System.Collections.Generic.List%601> applies to all constructed instances of that generic type, unless it's overridden for a particular constructed generic type (such as a `List<Int32>`) by a `TypeInstantiation` element.</span></span> <span data-ttu-id="ec59c-256">В противном случае, элементы определяют политику для именованного программного элемента.</span><span class="sxs-lookup"><span data-stu-id="ec59c-256">Otherwise, elements define policy for the program element named.</span></span>

<span data-ttu-id="ec59c-257">Если элемент является неоднозначным, ядро ищет совпадения и при обнаружении точного совпадения, будет ее использовать.</span><span class="sxs-lookup"><span data-stu-id="ec59c-257">When an element is ambiguous, the engine looks for matches, and if it finds an exact match, it will use it.</span></span> <span data-ttu-id="ec59c-258">При обнаружении нескольких совпадений будет предупреждение или ошибка.</span><span class="sxs-lookup"><span data-stu-id="ec59c-258">If it finds multiple matches, there will be a warning or error.</span></span>

### <a name="if-two-directives-apply-policy-to-the-same-program-element"></a><span data-ttu-id="ec59c-259">Если две директивы применяют политику к одному и тому же программному элементу</span><span class="sxs-lookup"><span data-stu-id="ec59c-259">If two directives apply policy to the same program element</span></span>

<span data-ttu-id="ec59c-260">Если два элемента в разных файлах директив среды выполнения пытаются установить один и тот же тип политики для одного программного элемента (например, сборки или типа) в разные значения, конфликт разрешается следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ec59c-260">If two elements in different runtime directives files try to set the same policy type for the same program element (such as an assembly or type) to different values, the conflict is resolved as follows:</span></span>

1. <span data-ttu-id="ec59c-261">Если элемент `Excluded` присутствует, он имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="ec59c-261">If the `Excluded` element is present, it has precedence.</span></span>

2. <span data-ttu-id="ec59c-262">`Required`имеет приоритет над не `Required`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-262">`Required` has precedence over not `Required`.</span></span>

3. <span data-ttu-id="ec59c-263">`All`имеет приоритет перед `PublicAndInternal`, который имеет приоритет над `Public`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-263">`All` has precedence over `PublicAndInternal`, which has precedence over `Public`.</span></span>

4. <span data-ttu-id="ec59c-264">Любой явный параметр имеет приоритет над `Auto`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-264">Any explicit setting has precedence over `Auto`.</span></span>

<span data-ttu-id="ec59c-265">Например, если один проект включает следующие два файла директив среды выполнения, устанавливается политика сериализации для DataClasses.dll на `Required Public` и `All`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-265">For example, if a single project includes the following two runtime directives files, the serialization policy for DataClasses.dll is set to both `Required Public` and `All`.</span></span> <span data-ttu-id="ec59c-266">В этом случае политика сериализации будет разрешаться как `Required All`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-266">In this case, the serialization policy would be resolved as `Required All`.</span></span>

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

<span data-ttu-id="ec59c-267">Однако, если две директивы в файле директив среды выполнения пытаются задать один и тот же тип политики одному программному элементу, то инструмент определения схемы XML отображает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="ec59c-267">However, if two directives in a single runtime directives file try to set the same policy type for the same program element, the XML Scheme Definition tool displays an error message.</span></span>

### <a name="if-child-and-parent-elements-apply-the-same-policy-type"></a><span data-ttu-id="ec59c-268">Если один и тот же тип политики применяется дочерними и родительскими элементами</span><span class="sxs-lookup"><span data-stu-id="ec59c-268">If child and parent elements apply the same policy type</span></span>

<span data-ttu-id="ec59c-269">Дочерние элементы переопределяют свои родительские элементы, в том числе параметр `Excluded`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-269">Child elements override their parent elements, including the `Excluded` setting.</span></span> <span data-ttu-id="ec59c-270">Переопределение — основная причина, по которой требуется указать `Auto`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-270">Overriding is the main reason you would want to specify `Auto`.</span></span>

<span data-ttu-id="ec59c-271">В следующем примере параметр политики сериализации для значения everything в `DataClasses`, который не находится в`DataClasses.ViewModels`, был бы `Required Public`, а значение everything в `DataClasses` и `DataClasses.ViewModels` было бы `All`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-271">In the following example, the serialization policy setting for everything in `DataClasses` that’s not in `DataClasses.ViewModels` would be `Required Public`, and everything that's in both `DataClasses` and `DataClasses.ViewModels` would be `All`.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public" >
         <Namespace Name="DataClasses.ViewModels" Serialize="All" />
      </Assembly>
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

### <a name="if-open-generics-and-instantiated-elements-apply-the-same-policy-type"></a><span data-ttu-id="ec59c-272">Если открытые универсальные типы и элементы экземпляра применяют один и тот же тип политики</span><span class="sxs-lookup"><span data-stu-id="ec59c-272">If open generics and instantiated elements apply the same policy type</span></span>

<span data-ttu-id="ec59c-273">В следующем примере `Dictionary<int,int>` назначается как политика  `Browse`, только если ядро имеет еще одну причину присвоить политику `Browse` (что было бы в противном случае поведением по умолчанию); В каждом экземпляре <xref:System.Collections.Generic.Dictionary%602> все члены будут доступны для просмотра.</span><span class="sxs-lookup"><span data-stu-id="ec59c-273">In the following example, `Dictionary<int,int>` is assigned the `Browse` policy only if the engine has another reason to give it the `Browse` policy (which would otherwise be the default behavior); every other instantiation of <xref:System.Collections.Generic.Dictionary%602> will have all of its members browsable.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public" >
         <Namespace Name="DataClasses.ViewModels" Serialize="All" />
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

### <a name="how-policy-is-inferred"></a><span data-ttu-id="ec59c-274">Как определяется политика</span><span class="sxs-lookup"><span data-stu-id="ec59c-274">How policy is inferred</span></span>

<span data-ttu-id="ec59c-275">Каждый тип политики имеет разный набор правил, определяющих, как присутствие этого типа политики влияет на другие конструкции.</span><span class="sxs-lookup"><span data-stu-id="ec59c-275">Each policy type has a different set of rules that determine how the presence of that policy type affects other constructs.</span></span>

#### <a name="the-effect-of-browse-policy"></a><span data-ttu-id="ec59c-276">Эффект политики Browse (Просмотр)</span><span class="sxs-lookup"><span data-stu-id="ec59c-276">The effect of Browse policy</span></span>

<span data-ttu-id="ec59c-277">Применение политики `Browse` для типа включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="ec59c-277">Applying the `Browse` policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="ec59c-278">Базовый тип типа помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-278">The base type of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="ec59c-279">Если экземпляр универсального типа, версия типа без создания экземпляра помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-279">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="ec59c-280">Если тип является делегатом, метод `Invoke` типа помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-280">If the type is a delegate, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="ec59c-281">Каждый интерфейс типа помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-281">Each interface of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="ec59c-282">Тип каждого атрибута примененного к типу помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-282">The type of each attribute applied to the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="ec59c-283">Если тип является универсальным, каждое ограничение типа помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-283">If the type is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="ec59c-284">Если тип универсален, типы, по которым создается экземпляр типа, помечаются политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-284">If the type is generic, the types over which the type is instantiated are marked with the `Browse` policy.</span></span>

<span data-ttu-id="ec59c-285">Применение политики `Browse` для метода включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="ec59c-285">Applying the `Browse` policy to a method involves the following policy changes:</span></span>

- <span data-ttu-id="ec59c-286">Каждый тип параметра метода помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-286">Each parameter type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="ec59c-287">Возвращаемый тип метода помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-287">The return type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="ec59c-288">Содержащий тип метода помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-288">The containing type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="ec59c-289">Если метод является экземпляром универсального метода, универсальный метод без экземпляра помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-289">If the method is an instantiated generic method, the uninstantiated generic method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="ec59c-290">Тип каждого атрибута, примененного к методу, помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-290">The type of each attribute applied to the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="ec59c-291">Если метод является универсальным, каждое ограничение типа помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-291">If the method is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="ec59c-292">Если метод универсален, типы, по которым создается экземпляр метода, помечаются политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-292">If the method is generic, the types over which the method is instantiated are marked with the `Browse` policy.</span></span>

<span data-ttu-id="ec59c-293">Применение политики `Browse` для поля включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="ec59c-293">Applying the `Browse` policy to a field involves the following policy changes:</span></span>

- <span data-ttu-id="ec59c-294">Тип каждого атрибута, примененного к полю, помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-294">The type of each attribute applied to the field is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="ec59c-295">Тип поля помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-295">The type of the field is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="ec59c-296">Тип, к которому принадлежит поле помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-296">The type to which the field belongs is marked with the `Browse` policy.</span></span>

#### <a name="the-effect-of-dynamic-policy"></a><span data-ttu-id="ec59c-297">Эффект политики Dynamic (Динамическая)</span><span class="sxs-lookup"><span data-stu-id="ec59c-297">The effect of Dynamic policy</span></span>

<span data-ttu-id="ec59c-298">Применение политики `Dynamic` для типа включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="ec59c-298">Applying the `Dynamic` policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="ec59c-299">Базовый тип типа помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-299">The base type of the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="ec59c-300">Если экземпляр универсального типа, версия типа без создания экземпляра помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-300">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="ec59c-301">Если тип является делегатом, метод `Invoke` типа помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-301">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="ec59c-302">Каждый интерфейс типа помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-302">Each interface of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="ec59c-303">Тип каждого атрибута примененного к типу помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-303">The type of each attribute applied to the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="ec59c-304">Если тип является универсальным, каждое ограничение типа помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-304">If the type is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="ec59c-305">Если тип универсален, типы, по которым создается экземпляр типа, помечаются политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-305">If the type is generic, the types over which the type is instantiated are marked with the `Browse` policy.</span></span>

<span data-ttu-id="ec59c-306">Применение политики `Dynamic` для метода включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="ec59c-306">Applying the `Dynamic` policy to a method involves the following policy changes:</span></span>

- <span data-ttu-id="ec59c-307">Каждый тип параметра метода помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-307">Each parameter type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="ec59c-308">Возвращаемый тип метода помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-308">The return type of the method is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="ec59c-309">Содержащий тип метода помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-309">The containing type of the method is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="ec59c-310">Если метод является экземпляром универсального метода, универсальный метод без экземпляра помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-310">If the method is an instantiated generic method, the uninstantiated generic method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="ec59c-311">Тип каждого атрибута, примененного к методу, помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-311">The type of each attribute applied to the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="ec59c-312">Если метод является универсальным, каждое ограничение типа помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-312">If the method is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="ec59c-313">Если метод универсален, типы, по которым создается экземпляр метода, помечаются политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-313">If the method is generic, the types over which the method is instantiated are marked with the `Browse` policy.</span></span>

- <span data-ttu-id="ec59c-314">Этот метод может вызываться `MethodInfo.Invoke`, а создание делегата становится возможным с помощью <xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ec59c-314">The method can be invoked by `MethodInfo.Invoke`, and delegate creation becomes possible by <xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="ec59c-315">Применение политики `Dynamic` для поля включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="ec59c-315">Applying the `Dynamic` policy to a field involves the following policy changes:</span></span>

- <span data-ttu-id="ec59c-316">Тип каждого атрибута, примененного к полю, помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-316">The type of each attribute applied to the field is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="ec59c-317">Тип поля помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-317">The type of the field is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="ec59c-318">Тип, к которому принадлежит поле помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-318">The type to which the field belongs is marked with the `Dynamic` policy.</span></span>

#### <a name="the-effect-of-activation-policy"></a><span data-ttu-id="ec59c-319">Эффект от политики Activation (активация)</span><span class="sxs-lookup"><span data-stu-id="ec59c-319">The effect of Activation policy</span></span>

<span data-ttu-id="ec59c-320">Применение политики Activation для типа включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="ec59c-320">Applying the Activation policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="ec59c-321">Если экземпляр универсального типа, версия типа без создания экземпляра помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-321">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="ec59c-322">Если тип является делегатом, метод `Invoke` типа помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-322">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="ec59c-323">Конструкторы типа помечаются политикой `Activation`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-323">Constructors of the type are marked with the `Activation` policy.</span></span>

<span data-ttu-id="ec59c-324">Применение политики `Activation` для метода включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="ec59c-324">Applying the `Activation` policy to a method involves the following policy change:</span></span>

- <span data-ttu-id="ec59c-325">Конструктор может вызываться методами <xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> и <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ec59c-325">The constructor can be invoked by the <xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> and <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="ec59c-326">Для методов политика `Activation` оказывает действие только на конструкторы.</span><span class="sxs-lookup"><span data-stu-id="ec59c-326">For methods, the `Activation` policy affects constructors only.</span></span>

<span data-ttu-id="ec59c-327">Применение политики `Activation` к полю не оказывает влияния.</span><span class="sxs-lookup"><span data-stu-id="ec59c-327">Applying the `Activation` policy to a field has no effect.</span></span>

#### <a name="the-effect-of-serialize-policy"></a><span data-ttu-id="ec59c-328">Эффект политики Serialize (сериализация)</span><span class="sxs-lookup"><span data-stu-id="ec59c-328">The effect of Serialize policy</span></span>

<span data-ttu-id="ec59c-329">Политика `Serialize` позволяет использовать общие сериализаторы, основанные на отражении.</span><span class="sxs-lookup"><span data-stu-id="ec59c-329">The `Serialize` policy enables the use of common reflection-based serializers.</span></span> <span data-ttu-id="ec59c-330">Тем не менее, поскольку точные шаблоны доступа к отражению сериализаторов сторонних разработчиков неизвестны Microsoft, эта политика может оказаться не совсем эффективной.</span><span class="sxs-lookup"><span data-stu-id="ec59c-330">However, because the exact reflection access patterns of non-Microsoft serializers are not known to Microsoft, this policy may not be entirely effective.</span></span>

<span data-ttu-id="ec59c-331">Применение политики `Serialize` для типа включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="ec59c-331">Applying the `Serialize` policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="ec59c-332">Базовый тип типа помечается политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-332">The base type of the type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="ec59c-333">Если экземпляр универсального типа, версия типа без создания экземпляра помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-333">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="ec59c-334">Если тип является делегатом, метод `Invoke` типа помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-334">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="ec59c-335">Если тип является перечислением, массив типа помечается политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-335">If the type is an enumeration, an array of the type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="ec59c-336">Если тип реализует <xref:System.Collections.Generic.IEnumerable%601>, `T` помечается политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-336">If the type implements <xref:System.Collections.Generic.IEnumerable%601>, `T` is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="ec59c-337">Если тип является типом <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.Generic.IList%601>, <xref:System.Collections.Generic.ICollection%601>, <xref:System.Collections.Generic.IReadOnlyCollection%601> или <xref:System.Collections.Generic.IReadOnlyList%601>, тогда `T[]` и <xref:System.Collections.Generic.List%601> помечаются политикой `Serialize`, однако ни один из членов типа интерфейса не помечаются политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-337">If the type is <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.Generic.IList%601>, <xref:System.Collections.Generic.ICollection%601>, <xref:System.Collections.Generic.IReadOnlyCollection%601>, or <xref:System.Collections.Generic.IReadOnlyList%601>, then `T[]` and <xref:System.Collections.Generic.List%601> marked with the `Serialize` policy., but no members of the interface type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="ec59c-338">Если тип является типом <xref:System.Collections.Generic.List%601>, то его члены не помечаются политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-338">If the type is <xref:System.Collections.Generic.List%601>, no members of the type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="ec59c-339">Если тип является типом <xref:System.Collections.Generic.IDictionary%602>, <xref:System.Collections.Generic.Dictionary%602> помечается политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-339">If the type is <xref:System.Collections.Generic.IDictionary%602>, <xref:System.Collections.Generic.Dictionary%602> is marked with the `Serialize` policy.</span></span> <span data-ttu-id="ec59c-340">Но члены типа не помечаются политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-340">but no members of the type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="ec59c-341">Если тип является типом <xref:System.Collections.Generic.Dictionary%602>, то его члены не помечаются политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-341">If the type is <xref:System.Collections.Generic.Dictionary%602>, no members of the type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="ec59c-342">Если тип реализует <xref:System.Collections.Generic.IDictionary%602>, `TKey` и `TValue` помечаются политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-342">If the type implements <xref:System.Collections.Generic.IDictionary%602>, `TKey` and `TValue` are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="ec59c-343">Каждый конструктор, каждый метод доступа к свойству и каждое поле помечается политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-343">Each constructor, each property accessor, and each field is marked with the `Serialize` policy.</span></span>

<span data-ttu-id="ec59c-344">Применение политики `Serialize` для метода включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="ec59c-344">Applying the `Serialize` policy to a method involves the following policy changes:</span></span>

- <span data-ttu-id="ec59c-345">Содержащий тип помечается политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-345">The containing type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="ec59c-346">Возвращаемый тип метода помечается политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-346">The return type of the method is marked with the `Serialize` policy.</span></span>

<span data-ttu-id="ec59c-347">Применение политики `Serialize` для поля включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="ec59c-347">Applying the `Serialize` policy to a field involves the following policy changes:</span></span>

- <span data-ttu-id="ec59c-348">Содержащий тип помечается политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-348">The containing type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="ec59c-349">Тип поля помечается политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="ec59c-349">The type of the field is marked with the `Serialize` policy.</span></span>

#### <a name="the-effect-of-xmlserializer-datacontractserializer-and-datacontractjsonserializer-policies"></a><span data-ttu-id="ec59c-350">Воздействие политик XmlSerializer, DataContractSerializer и DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="ec59c-350">The effect of XmlSerializer, DataContractSerializer, and DataContractJsonSerializer policies</span></span>

<span data-ttu-id="ec59c-351">В `Serialize` <xref:System.Runtime.Serialization.DataContractSerializer> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> отличие от политики, которая предназначена для сериализаторов на основе отражения, политики, и используются для включения набора сериализаторов, известных цепочке инструментов .NET Native. <xref:System.Xml.Serialization.XmlSerializer></span><span class="sxs-lookup"><span data-stu-id="ec59c-351">Unlike the `Serialize` policy, which is intended for reflection-based serializers, the <xref:System.Xml.Serialization.XmlSerializer>, <xref:System.Runtime.Serialization.DataContractSerializer>, and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> policies are used to enable a set of serializers that are known to the .NET Native tool chain.</span></span> <span data-ttu-id="ec59c-352">Эти сериализаторы не реализуются с помощью отражения, но наборы типов, которые могут быть сериализованы во время выполнения определяются так же, как типы, которые могут отражаться.</span><span class="sxs-lookup"><span data-stu-id="ec59c-352">These serializers are not implemented by using reflection, but the set of types that can be serialized at run time is determined in a similar manner as types that are reflectable.</span></span>

<span data-ttu-id="ec59c-353">Применение одной из этих политик для типа позволяет сериализовать тип с помощью соответствующего сериализатора.</span><span class="sxs-lookup"><span data-stu-id="ec59c-353">Applying one of these policies to a type enables the type to be serialized with the matching serializer.</span></span> <span data-ttu-id="ec59c-354">Все типы, которые обработчик сериализации может статически определить, как нуждающиеся в сериализации, будут также сериализуемыми.</span><span class="sxs-lookup"><span data-stu-id="ec59c-354">Also, any types that the serialization engine can statically determine as needing serialization will also be serializable.</span></span>

<span data-ttu-id="ec59c-355">Эти политики не оказывают влияния на методы или поля.</span><span class="sxs-lookup"><span data-stu-id="ec59c-355">These policies have no effect on methods or fields.</span></span>

<span data-ttu-id="ec59c-356">Подробнее см. в подразделе "Различия в сериализаторах" раздела [Миграция приложения для Магазина Windows в .NET Native](migrating-your-windows-store-app-to-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="ec59c-356">For more information, see the "Differences in Serializers" section in [Migrating Your Windows Store App to .NET Native](migrating-your-windows-store-app-to-net-native.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ec59c-357">См. также</span><span class="sxs-lookup"><span data-stu-id="ec59c-357">See also</span></span>

- [<span data-ttu-id="ec59c-358">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="ec59c-358">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="ec59c-359">Отражение и .NET Native</span><span class="sxs-lookup"><span data-stu-id="ec59c-359">Reflection and .NET Native</span></span>](reflection-and-net-native.md)
