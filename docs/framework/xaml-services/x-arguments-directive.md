---
title: Директива x:Arguments
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: 5bcd629e306169c1f7a61a316d76203827a2d0fe
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364265"
---
# <a name="xarguments-directive"></a><span data-ttu-id="6eb32-102">Директива x:Arguments</span><span class="sxs-lookup"><span data-stu-id="6eb32-102">x:Arguments Directive</span></span>
<span data-ttu-id="6eb32-103">Пакеты законструкции аргументов для объявления элемента объекта конструктора без параметров в XAML или для объявления объекта фабричного метода.</span><span class="sxs-lookup"><span data-stu-id="6eb32-103">Packages construction arguments for a non-parameterless constructor object element declaration in XAML, or for a factory method object declaration.</span></span>  
  
## <a name="xaml-element-usage-nonparameterless-constructor"></a><span data-ttu-id="6eb32-104">Использование элементов XAML (конструктор без параметров)</span><span class="sxs-lookup"><span data-stu-id="6eb32-104">XAML Element Usage (Nonparameterless constructor)</span></span>  
  
```  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-element-usage-factory-method"></a><span data-ttu-id="6eb32-105">Использование элементов XAML (фабричный метод)</span><span class="sxs-lookup"><span data-stu-id="6eb32-105">XAML Element Usage (factory method)</span></span>  
  
```  
<object x:FactoryMethod="methodName"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="6eb32-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="6eb32-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`oneOrMoreObjectElements`|<span data-ttu-id="6eb32-107">Один или несколько объектных элементов, задающих аргументы, передаваемые в резервный конструктор без параметров или фабричный метод.</span><span class="sxs-lookup"><span data-stu-id="6eb32-107">One or more object elements that specify arguments to be passed to the backing non-parameterless constructor or factory method.</span></span><br /><br /> <span data-ttu-id="6eb32-108">Типичное использование — использование текста инициализации в элементах объекта для указания фактических значений аргументов.</span><span class="sxs-lookup"><span data-stu-id="6eb32-108">Typical usage is to use initialization text within the object elements to specify the actual argument values.</span></span> <span data-ttu-id="6eb32-109">См. раздел "примеры".</span><span class="sxs-lookup"><span data-stu-id="6eb32-109">See Examples section.</span></span><br /><br /> <span data-ttu-id="6eb32-110">Порядок элементов важен.</span><span class="sxs-lookup"><span data-stu-id="6eb32-110">The order of the elements is significant.</span></span> <span data-ttu-id="6eb32-111">Типы XAML в порядке должны соответствовать типам и порядковому номеру метода резервного конструктора или фабричной перегрузки.</span><span class="sxs-lookup"><span data-stu-id="6eb32-111">The XAML types in order must match the types and type order of the backing constructor or factory method overload.</span></span>|  
|`methodName`|<span data-ttu-id="6eb32-112">Имя метода фабрики, который должен обрабатывать любые `x:Arguments` аргументы.</span><span class="sxs-lookup"><span data-stu-id="6eb32-112">The name of the factory method that should process any `x:Arguments` arguments.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="6eb32-113">Зависимости</span><span class="sxs-lookup"><span data-stu-id="6eb32-113">Dependencies</span></span>  
 <span data-ttu-id="6eb32-114">`x:FactoryMethod`может изменять область и поведение, когда `x:Arguments` это применимо.</span><span class="sxs-lookup"><span data-stu-id="6eb32-114">`x:FactoryMethod` can modify the scope and behavior where `x:Arguments` applies.</span></span>  
  
 <span data-ttu-id="6eb32-115">Если параметр `x:FactoryMethod` не указан, `x:Arguments` применяется к альтернативным (не по умолчанию) сигнатурам резервных конструкторов.</span><span class="sxs-lookup"><span data-stu-id="6eb32-115">If no `x:FactoryMethod` is specified, `x:Arguments` applies to alternate (non-default) signatures of the backing constructors.</span></span>  
  
 <span data-ttu-id="6eb32-116">Если `x:FactoryMethod` указан аргумент, `x:Arguments` применяется к перегрузке именованного метода.</span><span class="sxs-lookup"><span data-stu-id="6eb32-116">If `x:FactoryMethod` is specified, `x:Arguments` applies to an overload of the named method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6eb32-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="6eb32-117">Remarks</span></span>  
 <span data-ttu-id="6eb32-118">XAML 2006 может поддерживать инициализацию не по умолчанию посредством текста инициализации.</span><span class="sxs-lookup"><span data-stu-id="6eb32-118">XAML 2006 can support non-default initialization through initialization text.</span></span> <span data-ttu-id="6eb32-119">Однако практическое применение метода создания текста инициализации ограничено.</span><span class="sxs-lookup"><span data-stu-id="6eb32-119">However, the practical application of an initialization text construction technique is limited.</span></span> <span data-ttu-id="6eb32-120">Текст инициализации рассматривается как отдельная текстовая строка; Поэтому он добавляет только возможность для инициализации одного параметра, если только преобразователь типов не определен для поведения конструирования, который может анализировать пользовательские элементы данных и пользовательские разделители из строки.</span><span class="sxs-lookup"><span data-stu-id="6eb32-120">Initialization text is treated as a single text string; therefore, it only adds capability for a single parameter initialization unless a type converter is defined for the construction behavior that can parse custom information items and custom delimiters from the string.</span></span> <span data-ttu-id="6eb32-121">Кроме того, Текстовая строка в объектной логике, возможно, является собственным преобразователем собственных типов по умолчанию средства синтаксического анализа XAML для обработки примитивов, отличных от истинной строки.</span><span class="sxs-lookup"><span data-stu-id="6eb32-121">Also, the text string to object logic is potentially a given XAML parser's native default type converter for handling primitives other than a true string.</span></span>  
  
 <span data-ttu-id="6eb32-122">Использование `x:Arguments` XAML не является элементом свойства в типичном смысле, поскольку разметка директивы не ссылается на тип содержащего его элемента.</span><span class="sxs-lookup"><span data-stu-id="6eb32-122">The `x:Arguments` XAML usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="6eb32-123">Это более то же самое, что `x:Code` и другие директивы, например, где элемент отмечает диапазон, в котором разметка должна интерпретироваться как значение, отличное от значения по умолчанию для дочернего содержимого.</span><span class="sxs-lookup"><span data-stu-id="6eb32-123">It is more akin to other directives such as `x:Code` where the element demarks a range in which the markup should be interpreted as other than the default for child contents.</span></span> <span data-ttu-id="6eb32-124">В этом случае тип XAML каждого элемента объекта передает сведения о типах аргументов, которые используются анализаторами XAML для определения конкретной сигнатуры `x:Arguments` метода фабрики конструктора, на которую пытается ссылаться использование.</span><span class="sxs-lookup"><span data-stu-id="6eb32-124">In this case, the XAML type of each object element communicates information about the argument types, which is used by XAML parsers to determine which specific constructor factory method signature an `x:Arguments` usage is attempting to reference.</span></span>  
  
 <span data-ttu-id="6eb32-125">`x:Arguments`для создаваемого объектного элемента должен предшествовать любым другим элементам свойств, содержимому, внутреннему тексту или строкам инициализации объектного элемента.</span><span class="sxs-lookup"><span data-stu-id="6eb32-125">`x:Arguments` for an object element being constructed must precede any other property elements, content, inner text, or initialization strings of the object element.</span></span> <span data-ttu-id="6eb32-126">Элементы объекта в `x:Arguments` могут включать атрибуты и строки инициализации, как это разрешено этим типом XAML и его резервным конструктором или фабричным методом.</span><span class="sxs-lookup"><span data-stu-id="6eb32-126">The object elements within `x:Arguments` can include attributes and initialization strings, as permitted by that XAML type and its backing constructor or factory method.</span></span> <span data-ttu-id="6eb32-127">Для объекта или аргументов можно указать пользовательские типы XAML или типы XAML, которые в противном случае выходят за пределы пространства имен XAML по умолчанию, ссылаясь на установленные сопоставления префиксов.</span><span class="sxs-lookup"><span data-stu-id="6eb32-127">For either the object or the arguments, you can specify custom XAML types or XAML types that are otherwise outside the default XAML namespace by referencing established prefix mappings.</span></span>  
  
 <span data-ttu-id="6eb32-128">Обработчики XAML применяют следующие рекомендации, чтобы определить, как `x:Arguments` аргументы, заданные в, должны использоваться для создания объекта.</span><span class="sxs-lookup"><span data-stu-id="6eb32-128">XAML processors use the following guidelines to determine how the arguments specified in `x:Arguments` should be used to construct an object.</span></span> <span data-ttu-id="6eb32-129">Если `x:FactoryMethod` указан параметр, сведения сравниваются с указанным `x:FactoryMethod` ( `x:FactoryMethod` Обратите внимание, что значение является именем метода, а именованный метод может иметь перегрузки).</span><span class="sxs-lookup"><span data-stu-id="6eb32-129">If `x:FactoryMethod` is specified, information is compared to the specified `x:FactoryMethod` (note that the value of `x:FactoryMethod` is the method name, and the named method can have overloads.</span></span> <span data-ttu-id="6eb32-130">Если `x:FactoryMethod` параметр не указан, сведения сравниваются с набором всех перегрузок открытого конструктора объекта.</span><span class="sxs-lookup"><span data-stu-id="6eb32-130">If `x:FactoryMethod` is not specified, information is compared to the set of all public constructor overloads of the object.</span></span> <span data-ttu-id="6eb32-131">Затем логика обработки XAML сравнивает количество параметров и выбирает перегрузку с соответствующей арностью.</span><span class="sxs-lookup"><span data-stu-id="6eb32-131">XAML processing logic then compares the number of parameters and selects the overload with matching arity.</span></span> <span data-ttu-id="6eb32-132">При наличии нескольких совпадений обработчик XAML должен сравнивать типы параметров на основе типов XAML предоставленных элементов объекта.</span><span class="sxs-lookup"><span data-stu-id="6eb32-132">If there is more than one match, the XAML processor should compare the types of the parameters based on the XAML types of the provided object elements.</span></span> <span data-ttu-id="6eb32-133">Если по-прежнему существует более одного совпадения, поведение обработчика XAML не определено.</span><span class="sxs-lookup"><span data-stu-id="6eb32-133">If there is still more than one match, the XAML processor behavior is undefined.</span></span> <span data-ttu-id="6eb32-134">`x:FactoryMethod` Если указан, но метод не может быть разрешен, обработчик XAML должен вызвать исключение.</span><span class="sxs-lookup"><span data-stu-id="6eb32-134">If a `x:FactoryMethod` is specified but the method cannot be resolved, a XAML processor should throw an exception.</span></span>  
  
 <span data-ttu-id="6eb32-135">Использование `<x:Arguments>string</x:Arguments>` атрибута XAML технически возможно.</span><span class="sxs-lookup"><span data-stu-id="6eb32-135">A XAML attribute usage `<x:Arguments>string</x:Arguments>` is technically possible.</span></span> <span data-ttu-id="6eb32-136">Однако это не дает никаких возможностей, помимо того, что может быть сделано в противном случае посредством инициализации текста и преобразователей типов, и использование этого синтаксиса не является намерением разработки функций метода фабрики XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="6eb32-136">However, this provides no capabilities beyond what could be done otherwise through initialization text and type converters, and using this syntax is not the design intention of the XAML 2009 factory method features.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="6eb32-137">Примеры</span><span class="sxs-lookup"><span data-stu-id="6eb32-137">Examples</span></span>  
 <span data-ttu-id="6eb32-138">В следующем примере показана сигнатура конструктора без параметров, а затем использование XAML для `x:Arguments` доступа к этой сигнатуре.</span><span class="sxs-lookup"><span data-stu-id="6eb32-138">The following example shows a non-parameterless constructor signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
```csharp  
public class Food {  
    private string _name;  
    private Int32 _calories;  
    public Food(string name, Int32 calories) {  
        _name=name;  
        _calories=calories;  
    }  
}  
```  
  
```xaml  
<my:Food>  
    <x:Arguments>  
        <x:String>Apple</x:String>  
        <x:Int32>150</x:Int32>  
    </x:Arguments>  
</my:Food>  
```  
  
 <span data-ttu-id="6eb32-139">В следующем примере показана сигнатура целевого метода фабрики, а затем использование `x:Arguments` XAML для доступа к этой сигнатуре.</span><span class="sxs-lookup"><span data-stu-id="6eb32-139">The following example shows a target factory method signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
```csharp  
public Food TryLookupFood(string name)  
{  
  switch (name) {  
    case "Apple": return new Food("Apple",150);  
    case "Chocolate": return new Food("Chocolate",200);  
    case "Cheese": return new Food("Cheese", 450);  
    default: {return new Food(name,0);  
  }  
}  
```  
  
```xaml  
<my:Food x:FactoryMethod="TryLookupFood">  
    <x:Arguments>  
        <x:String>Apple</x:String>  
    </x:Arguments>  
</my:Food>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6eb32-140">См. также</span><span class="sxs-lookup"><span data-stu-id="6eb32-140">See also</span></span>

- [<span data-ttu-id="6eb32-141">Определение пользовательских типов для использования со службами XAML .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6eb32-141">Defining Custom Types for Use with .NET Framework XAML Services</span></span>](defining-custom-types-for-use-with-net-framework-xaml-services.md)
- [<span data-ttu-id="6eb32-142">Общие сведения о языке XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="6eb32-142">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
