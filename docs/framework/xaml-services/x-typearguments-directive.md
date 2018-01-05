---
title: "Директива x:TypeArguments"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- x:TypeArguments
- xTypeArguments
- TypeArguments
helpviewer_keywords:
- x:TypeArguments attribute [XAML Services]
- TypeArguments attribute in XAML [XAML Services]
- XAML [XAML Services], x:TypeArguments attribute
ms.assetid: 86561058-d393-4a44-b5c3-993a4513ea74
caps.latest.revision: "18"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e601fb5895460e52aa21836c542d0b1367527f09
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="xtypearguments-directive"></a><span data-ttu-id="5a408-102">Директива x:TypeArguments</span><span class="sxs-lookup"><span data-stu-id="5a408-102">x:TypeArguments Directive</span></span>
<span data-ttu-id="5a408-103">Передает аргументы типов ограничений универсального в конструктор универсального типа.</span><span class="sxs-lookup"><span data-stu-id="5a408-103">Passes constraining type arguments of a generic to the constructor of the generic type.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="5a408-104">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="5a408-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:TypeArguments="typeString" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="5a408-105">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="5a408-105">XAML Values</span></span>  
  
|||  
|-|-|  
|`object`|<span data-ttu-id="5a408-106">Объявление элемента объекта типа XAML, который реализуется универсальным типом среды CLR.</span><span class="sxs-lookup"><span data-stu-id="5a408-106">An object element declaration of a XAML type, which is backed by a CLR generic type.</span></span> <span data-ttu-id="5a408-107">Если `object` ссылается на тип XAML не из пространства имен XAML по умолчанию, `object` требует префикса для указания пространства имен XAML где `object` существует.</span><span class="sxs-lookup"><span data-stu-id="5a408-107">If `object` refers to a XAML type that is not from the default XAML namespace, `object` requires a prefix to indicate the XAML namespace where `object` exists.</span></span>|  
|`typeString`|<span data-ttu-id="5a408-108">Строка, которая объявляет один или несколько XAML типа имена в виде строк, которые передают аргументы типа для универсального типа среды CLR.</span><span class="sxs-lookup"><span data-stu-id="5a408-108">A string that declares one or more XAML type names as strings, which supplies the type arguments for the CLR generic type.</span></span> <span data-ttu-id="5a408-109">Заметки о дополнительный синтаксис см. заметки.</span><span class="sxs-lookup"><span data-stu-id="5a408-109">See Remarks for additional syntax notes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a408-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="5a408-110">Remarks</span></span>  
 <span data-ttu-id="5a408-111">В большинстве случаев типов XAML, которые используются как элемент в `typeString` строки имеют префикс.</span><span class="sxs-lookup"><span data-stu-id="5a408-111">In most cases, the XAML types that are used as an information item in a `typeString` string are prefixed.</span></span> <span data-ttu-id="5a408-112">Стандартные типы CLR универсальные ограничения (например, <xref:System.Int32> и <xref:System.String>) из библиотеки базовых классов CLR.</span><span class="sxs-lookup"><span data-stu-id="5a408-112">Typical types of CLR generic constraints (for example, <xref:System.Int32> and <xref:System.String>) come from CLR base class libraries.</span></span> <span data-ttu-id="5a408-113">Эти библиотеки не пространства имен XAML по умолчанию может выполняться с обычной специфичная для платформы и поэтому требуют сопоставления префиксов для использования XAML.</span><span class="sxs-lookup"><span data-stu-id="5a408-113">Those libraries are not mapped to typical framework-specific default XAML namespaces, and therefore, require a prefix mapping for XAML usage.</span></span>  
  
 <span data-ttu-id="5a408-114">Можно указать более одного имени типа XAML, используя запятую в качестве разделителя.</span><span class="sxs-lookup"><span data-stu-id="5a408-114">You can specify more than one XAML type name by using a comma delimiter.</span></span>  
  
 <span data-ttu-id="5a408-115">Если универсальные ограничения сами используют универсальные типы, аргументы типа вложенного ограничения может содержаться в скобки ().</span><span class="sxs-lookup"><span data-stu-id="5a408-115">If the generic constraints themselves use generic types, the nested constraint type arguments can be contained by parentheses ().</span></span>  
  
 <span data-ttu-id="5a408-116">Обратите внимание, что это определение `x:TypeArguments` относится к службами XAML .NET Framework и с помощью резервирования CLR.</span><span class="sxs-lookup"><span data-stu-id="5a408-116">Note that this definition of `x:TypeArguments` is specific to .NET Framework XAML Services and using CLR backing.</span></span> <span data-ttu-id="5a408-117">Определение уровня языка можно найти в [ \[MS-XAML\] раздел 5.3.11](http://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="5a408-117">A language-level definition can be found in [\[MS-XAML\] Section 5.3.11](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
## <a name="usage-examples"></a><span data-ttu-id="5a408-118">Примеры использования</span><span class="sxs-lookup"><span data-stu-id="5a408-118">Usage Examples</span></span>  
 <span data-ttu-id="5a408-119">В этих примерах предполагается, что объявлены следующие определения пространства имен XAML:</span><span class="sxs-lookup"><span data-stu-id="5a408-119">For these examples, assume that the following XAML namespace definitions are declared:</span></span>  
  
```  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### <a name="liststring"></a><span data-ttu-id="5a408-120">Список\<строка ></span><span class="sxs-lookup"><span data-stu-id="5a408-120">List\<String></span></span>  
 <span data-ttu-id="5a408-121">`<scg:List x:TypeArguments="sys:String" ...>`Создает новый <xref:System.Collections.Generic.List%601> с <xref:System.String> аргумент типа.</span><span class="sxs-lookup"><span data-stu-id="5a408-121">`<scg:List x:TypeArguments="sys:String" ...>` instantiates a new <xref:System.Collections.Generic.List%601> with a <xref:System.String> type argument.</span></span>  
  
### <a name="dictionarystringstring"></a><span data-ttu-id="5a408-122">Словарь\<String, String ></span><span class="sxs-lookup"><span data-stu-id="5a408-122">Dictionary\<String,String></span></span>  
 <span data-ttu-id="5a408-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>`Создает новый <xref:System.Collections.Generic.Dictionary%602> с двумя <xref:System.String> аргументы типа.</span><span class="sxs-lookup"><span data-stu-id="5a408-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` instantiates a new <xref:System.Collections.Generic.Dictionary%602> with two <xref:System.String> type arguments.</span></span>  
  
### <a name="queuekeyvaluepairstringstring"></a><span data-ttu-id="5a408-124">Очередь < KeyValuePair\<String, String >></span><span class="sxs-lookup"><span data-stu-id="5a408-124">Queue<KeyValuePair\<String,String>></span></span>  
 <span data-ttu-id="5a408-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>`Создает новый <xref:System.Collections.Generic.Queue%601> , имеет ограничение <xref:System.Collections.Generic.KeyValuePair%602> с аргументами типа внутреннее ограничение <xref:System.String> и <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5a408-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` instantiates a new <xref:System.Collections.Generic.Queue%601> that has a constraint of <xref:System.Collections.Generic.KeyValuePair%602> with the inner constraint type arguments <xref:System.String> and <xref:System.String>.</span></span>  
  
## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a><span data-ttu-id="5a408-126">Использование универсальных XAML XAML 2006 и WPF</span><span class="sxs-lookup"><span data-stu-id="5a408-126">XAML 2006 and WPF Generic XAML Usages</span></span>  
 <span data-ttu-id="5a408-127">Для использования XAML 2006 и XAML, который используется для приложений WPF, действуют следующие ограничения для `x:TypeArguments` и их использование универсального типа из XAML в целом:</span><span class="sxs-lookup"><span data-stu-id="5a408-127">For XAML 2006 usage, and XAML that is used for WPF applications, the following restrictions exist for `x:TypeArguments` and generic type usages from XAML in general:</span></span>  
  
-   <span data-ttu-id="5a408-128">Только корневой элемент файла XAML может поддерживать универсальное использование XAML, который ссылается на универсальный тип.</span><span class="sxs-lookup"><span data-stu-id="5a408-128">Only the root element of a XAML file can support a generic XAML usage that references a generic type.</span></span>  
  
-   <span data-ttu-id="5a408-129">Корневой элемент необходимо сопоставить с по крайней мере один аргумент типа универсального типа.</span><span class="sxs-lookup"><span data-stu-id="5a408-129">The root element must map to a generic type with at least one type argument.</span></span> <span data-ttu-id="5a408-130">Например, <xref:System.Windows.Navigation.PageFunction%601>.</span><span class="sxs-lookup"><span data-stu-id="5a408-130">An example is <xref:System.Windows.Navigation.PageFunction%601>.</span></span> <span data-ttu-id="5a408-131">Функции страницы являются основным сценарием для поддержки универсального использования XAML в WPF.</span><span class="sxs-lookup"><span data-stu-id="5a408-131">The page functions are the primary scenario for XAML generic usage support in WPF.</span></span>  
  
-   <span data-ttu-id="5a408-132">Корневого элемента объекта XAML элемента для универсальных также необходимо объявить разделяемый класс с помощью `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="5a408-132">The root element XAML object element for the generic must also declare a partial class using `x:Class`.</span></span> <span data-ttu-id="5a408-133">Это верно, даже если определение WPF действие построения.</span><span class="sxs-lookup"><span data-stu-id="5a408-133">This is true even if defining a WPF build action.</span></span>  
  
-   <span data-ttu-id="5a408-134">`x:TypeArguments`нельзя ссылаться на вложенные универсальные ограничения.</span><span class="sxs-lookup"><span data-stu-id="5a408-134">`x:TypeArguments` cannot reference nested generic constraints.</span></span>  
  
## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a><span data-ttu-id="5a408-135">XAML 2009 г. или XAML 2006 без WPF 3.0 или WPF 3.5 зависимостей</span><span class="sxs-lookup"><span data-stu-id="5a408-135">XAML 2009 or XAML 2006 with No WPF 3.0 or WPF 3.5 Dependency</span></span>  
 <span data-ttu-id="5a408-136">В службах XAML .NET Framework для XAML 2006 и XAML 2009 связанных с WPF, ограничений для универсального использования XAML освобождаются.</span><span class="sxs-lookup"><span data-stu-id="5a408-136">In .NET Framework XAML Services for either XAML 2006 or XAML 2009, the WPF-related restrictions on generic XAML usage are relaxed.</span></span> <span data-ttu-id="5a408-137">Можно создать экземпляр универсального объектного элемента в любом месте в разметке XAML, поддерживающий резервный тип системы и объектной моделью.</span><span class="sxs-lookup"><span data-stu-id="5a408-137">You can instantiate a generic object element at any position in XAML markup that the backing type system and object model can support.</span></span>  
  
 <span data-ttu-id="5a408-138">При использовании XAML 2009 вместо сопоставления CLR базовые типы для получения типов XAML для общих примитивов языка, можно использовать [встроенные типы общих примитивов языка XAML](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md) сведения в виде элементов `typeString`.</span><span class="sxs-lookup"><span data-stu-id="5a408-138">If you use XAML 2009 instead of mapping the CLR base types to obtain XAML types for common language primitives, you can use [Built-in Types for Common XAML Language Primitives](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md) as information items in a `typeString`.</span></span> <span data-ttu-id="5a408-139">Например, можно объявить следующее (префикс сопоставления не отображаются, но x является имен XAML языка XAML для XAML 2009 г.):</span><span class="sxs-lookup"><span data-stu-id="5a408-139">For example, you could declare the following (prefix mappings not shown, but x is the XAML language XAML namespace for XAML 2009):</span></span>  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 <span data-ttu-id="5a408-140">В WPF и при нацеливании [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], можно использовать возможности XAML 2009 вместе с `x:TypeArguments` , но только для свободного XAML (XAML, который не является компилированной разметки).</span><span class="sxs-lookup"><span data-stu-id="5a408-140">In WPF and when targeting [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use XAML 2009 features together with `x:TypeArguments` but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="5a408-141">Скомпилированный с разметкой XAML и форма BAML кода XAML в настоящее время не поддерживают ключевые слова и компоненты XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="5a408-141">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span> <span data-ttu-id="5a408-142">При необходимости компиляции разметки XAML, нужно следовать ограничениям, указанным в разделе «XAML 2006 и универсального XAML WPF».</span><span class="sxs-lookup"><span data-stu-id="5a408-142">If you need to markup compile the XAML, you must operate under the restrictions noted in the "XAML 2006 and WPF Generic XAML Usages" section.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a408-143">См. также</span><span class="sxs-lookup"><span data-stu-id="5a408-143">See Also</span></span>  
 [<span data-ttu-id="5a408-144">Директива x:Class</span><span class="sxs-lookup"><span data-stu-id="5a408-144">x:Class Directive</span></span>](../../../docs/framework/xaml-services/x-class-directive.md)  
 [<span data-ttu-id="5a408-145">Расширение разметки x:Type</span><span class="sxs-lookup"><span data-stu-id="5a408-145">x:Type Markup Extension</span></span>](../../../docs/framework/xaml-services/x-type-markup-extension.md)  
 [<span data-ttu-id="5a408-146">Встроенные типы для общих примитивов языка XAML</span><span class="sxs-lookup"><span data-stu-id="5a408-146">Built-in Types for Common XAML Language Primitives</span></span>](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)  
 [<span data-ttu-id="5a408-147">Универсальные шаблоны в XAML</span><span class="sxs-lookup"><span data-stu-id="5a408-147">Generics in XAML</span></span>](../../../docs/framework/xaml-services/generics-in-xaml.md)
