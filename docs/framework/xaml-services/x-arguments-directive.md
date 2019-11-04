---
title: Директива x:Arguments
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: 338286b417c78b7cceeb30188e888928a15607cd
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458652"
---
# <a name="xarguments-directive"></a><span data-ttu-id="6ef40-102">Директива x:Arguments</span><span class="sxs-lookup"><span data-stu-id="6ef40-102">x:Arguments Directive</span></span>
<span data-ttu-id="6ef40-103">Пакеты законструкции аргументов для объявления элемента объекта конструктора без параметров в XAML или для объявления объекта фабричного метода.</span><span class="sxs-lookup"><span data-stu-id="6ef40-103">Packages construction arguments for a non-parameterless constructor object element declaration in XAML, or for a factory method object declaration.</span></span>  
  
## <a name="xaml-element-usage-nonparameterless-constructor"></a><span data-ttu-id="6ef40-104">Использование элементов XAML (конструктор без параметров)</span><span class="sxs-lookup"><span data-stu-id="6ef40-104">XAML Element Usage (Nonparameterless constructor)</span></span>  
  
```xaml  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-element-usage-factory-method"></a><span data-ttu-id="6ef40-105">Использование элементов XAML (фабричный метод)</span><span class="sxs-lookup"><span data-stu-id="6ef40-105">XAML Element Usage (factory method)</span></span>  
  
```xaml  
<object x:FactoryMethod="methodName"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="6ef40-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="6ef40-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`oneOrMoreObjectElements`|<span data-ttu-id="6ef40-107">Один или несколько объектных элементов, задающих аргументы, передаваемые в резервный конструктор без параметров или фабричный метод.</span><span class="sxs-lookup"><span data-stu-id="6ef40-107">One or more object elements that specify arguments to be passed to the backing non-parameterless constructor or factory method.</span></span><br /><br /> <span data-ttu-id="6ef40-108">Типичное использование — использование текста инициализации в элементах объекта для указания фактических значений аргументов.</span><span class="sxs-lookup"><span data-stu-id="6ef40-108">Typical usage is to use initialization text within the object elements to specify the actual argument values.</span></span> <span data-ttu-id="6ef40-109">См. раздел "примеры".</span><span class="sxs-lookup"><span data-stu-id="6ef40-109">See Examples section.</span></span><br /><br /> <span data-ttu-id="6ef40-110">Порядок элементов важен.</span><span class="sxs-lookup"><span data-stu-id="6ef40-110">The order of the elements is significant.</span></span> <span data-ttu-id="6ef40-111">Типы XAML в порядке должны соответствовать типам и порядковому номеру метода резервного конструктора или фабричной перегрузки.</span><span class="sxs-lookup"><span data-stu-id="6ef40-111">The XAML types in order must match the types and type order of the backing constructor or factory method overload.</span></span>|  
|`methodName`|<span data-ttu-id="6ef40-112">Имя метода фабрики, который должен обрабатывать любые `x:Arguments` аргументы.</span><span class="sxs-lookup"><span data-stu-id="6ef40-112">The name of the factory method that should process any `x:Arguments` arguments.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="6ef40-113">Зависимости</span><span class="sxs-lookup"><span data-stu-id="6ef40-113">Dependencies</span></span>  
 <span data-ttu-id="6ef40-114">`x:FactoryMethod` может изменять область и поведение, когда `x:Arguments` применимо.</span><span class="sxs-lookup"><span data-stu-id="6ef40-114">`x:FactoryMethod` can modify the scope and behavior where `x:Arguments` applies.</span></span>  
  
 <span data-ttu-id="6ef40-115">Если `x:FactoryMethod` не указано, `x:Arguments` применяется к альтернативным (не по умолчанию) сигнатурам резервных конструкторов.</span><span class="sxs-lookup"><span data-stu-id="6ef40-115">If no `x:FactoryMethod` is specified, `x:Arguments` applies to alternate (non-default) signatures of the backing constructors.</span></span>  
  
 <span data-ttu-id="6ef40-116">Если указано `x:FactoryMethod`, `x:Arguments` применяется к перегрузке именованного метода.</span><span class="sxs-lookup"><span data-stu-id="6ef40-116">If `x:FactoryMethod` is specified, `x:Arguments` applies to an overload of the named method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ef40-117">Заметки</span><span class="sxs-lookup"><span data-stu-id="6ef40-117">Remarks</span></span>  
 <span data-ttu-id="6ef40-118">XAML 2006 может поддерживать инициализацию не по умолчанию посредством текста инициализации.</span><span class="sxs-lookup"><span data-stu-id="6ef40-118">XAML 2006 can support non-default initialization through initialization text.</span></span> <span data-ttu-id="6ef40-119">Однако практическое применение метода создания текста инициализации ограничено.</span><span class="sxs-lookup"><span data-stu-id="6ef40-119">However, the practical application of an initialization text construction technique is limited.</span></span> <span data-ttu-id="6ef40-120">Текст инициализации рассматривается как отдельная текстовая строка; Поэтому он добавляет только возможность для инициализации одного параметра, если только преобразователь типов не определен для поведения конструирования, который может анализировать пользовательские элементы данных и пользовательские разделители из строки.</span><span class="sxs-lookup"><span data-stu-id="6ef40-120">Initialization text is treated as a single text string; therefore, it only adds capability for a single parameter initialization unless a type converter is defined for the construction behavior that can parse custom information items and custom delimiters from the string.</span></span> <span data-ttu-id="6ef40-121">Кроме того, Текстовая строка в объектной логике, возможно, является собственным преобразователем собственных типов по умолчанию средства синтаксического анализа XAML для обработки примитивов, отличных от истинной строки.</span><span class="sxs-lookup"><span data-stu-id="6ef40-121">Also, the text string to object logic is potentially a given XAML parser's native default type converter for handling primitives other than a true string.</span></span>  
  
 <span data-ttu-id="6ef40-122">`x:Arguments` использование XAML не является использованием элемента свойства в типичном смысле, поскольку разметка директивы не ссылается на тип содержащего его элемента.</span><span class="sxs-lookup"><span data-stu-id="6ef40-122">The `x:Arguments` XAML usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="6ef40-123">Он более аналогичен другим директивам, таким как `x:Code`, где элемент отмечает диапазон, в котором разметка должна интерпретироваться как значение, отличное от значения по умолчанию для дочернего содержимого.</span><span class="sxs-lookup"><span data-stu-id="6ef40-123">It is more akin to other directives such as `x:Code` where the element demarks a range in which the markup should be interpreted as other than the default for child contents.</span></span> <span data-ttu-id="6ef40-124">В этом случае тип XAML каждого элемента объекта передает сведения о типах аргументов, которые используются средствами синтаксического анализа XAML для определения конкретной сигнатуры метода фабрики конструктора, на которую пытается ссылаться `x:Arguments` использования.</span><span class="sxs-lookup"><span data-stu-id="6ef40-124">In this case, the XAML type of each object element communicates information about the argument types, which is used by XAML parsers to determine which specific constructor factory method signature an `x:Arguments` usage is attempting to reference.</span></span>  
  
 <span data-ttu-id="6ef40-125">`x:Arguments` для создаваемого объектного элемента должен предшествовать любым другим элементам свойств, содержимому, внутреннему тексту или строкам инициализации объектного элемента.</span><span class="sxs-lookup"><span data-stu-id="6ef40-125">`x:Arguments` for an object element being constructed must precede any other property elements, content, inner text, or initialization strings of the object element.</span></span> <span data-ttu-id="6ef40-126">Элементы объекта в `x:Arguments` могут содержать атрибуты и строки инициализации, как это разрешено типом XAML и его резервным конструктором или фабричным методом.</span><span class="sxs-lookup"><span data-stu-id="6ef40-126">The object elements within `x:Arguments` can include attributes and initialization strings, as permitted by that XAML type and its backing constructor or factory method.</span></span> <span data-ttu-id="6ef40-127">Для объекта или аргументов можно указать пользовательские типы XAML или типы XAML, которые в противном случае выходят за пределы пространства имен XAML по умолчанию, ссылаясь на установленные сопоставления префиксов.</span><span class="sxs-lookup"><span data-stu-id="6ef40-127">For either the object or the arguments, you can specify custom XAML types or XAML types that are otherwise outside the default XAML namespace by referencing established prefix mappings.</span></span>  
  
 <span data-ttu-id="6ef40-128">Обработчики XAML применяют следующие рекомендации, чтобы определить, как следует использовать аргументы, заданные в `x:Arguments`, для создания объекта.</span><span class="sxs-lookup"><span data-stu-id="6ef40-128">XAML processors use the following guidelines to determine how the arguments specified in `x:Arguments` should be used to construct an object.</span></span> <span data-ttu-id="6ef40-129">Если указано `x:FactoryMethod`, сведения сравниваются с указанным `x:FactoryMethod` (Обратите внимание, что значение `x:FactoryMethod` является именем метода, а именованный метод может иметь перегрузки.</span><span class="sxs-lookup"><span data-stu-id="6ef40-129">If `x:FactoryMethod` is specified, information is compared to the specified `x:FactoryMethod` (note that the value of `x:FactoryMethod` is the method name, and the named method can have overloads.</span></span> <span data-ttu-id="6ef40-130">Если параметр `x:FactoryMethod` не указан, сведения сравниваются с набором всех перегрузок открытого конструктора объекта.</span><span class="sxs-lookup"><span data-stu-id="6ef40-130">If `x:FactoryMethod` is not specified, information is compared to the set of all public constructor overloads of the object.</span></span> <span data-ttu-id="6ef40-131">Затем логика обработки XAML сравнивает количество параметров и выбирает перегрузку с соответствующей арностью.</span><span class="sxs-lookup"><span data-stu-id="6ef40-131">XAML processing logic then compares the number of parameters and selects the overload with matching arity.</span></span> <span data-ttu-id="6ef40-132">При наличии нескольких совпадений обработчик XAML должен сравнивать типы параметров на основе типов XAML предоставленных элементов объекта.</span><span class="sxs-lookup"><span data-stu-id="6ef40-132">If there is more than one match, the XAML processor should compare the types of the parameters based on the XAML types of the provided object elements.</span></span> <span data-ttu-id="6ef40-133">Если по-прежнему существует более одного совпадения, поведение обработчика XAML не определено.</span><span class="sxs-lookup"><span data-stu-id="6ef40-133">If there is still more than one match, the XAML processor behavior is undefined.</span></span> <span data-ttu-id="6ef40-134">Если указан `x:FactoryMethod`, но метод не может быть разрешен, обработчик XAML должен вызвать исключение.</span><span class="sxs-lookup"><span data-stu-id="6ef40-134">If a `x:FactoryMethod` is specified but the method cannot be resolved, a XAML processor should throw an exception.</span></span>  
  
 <span data-ttu-id="6ef40-135">`<x:Arguments>string</x:Arguments>` использования атрибута XAML технически возможно.</span><span class="sxs-lookup"><span data-stu-id="6ef40-135">A XAML attribute usage `<x:Arguments>string</x:Arguments>` is technically possible.</span></span> <span data-ttu-id="6ef40-136">Однако это не дает никаких возможностей, помимо того, что может быть сделано в противном случае посредством инициализации текста и преобразователей типов, и использование этого синтаксиса не является намерением разработки функций метода фабрики XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="6ef40-136">However, this provides no capabilities beyond what could be done otherwise through initialization text and type converters, and using this syntax is not the design intention of the XAML 2009 factory method features.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="6ef40-137">Примеры</span><span class="sxs-lookup"><span data-stu-id="6ef40-137">Examples</span></span>  
 <span data-ttu-id="6ef40-138">В следующем примере показана сигнатура конструктора без параметров, а затем используется `x:Arguments`, который обращается к этой сигнатуре.</span><span class="sxs-lookup"><span data-stu-id="6ef40-138">The following example shows a non-parameterless constructor signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
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
  
 <span data-ttu-id="6ef40-139">В следующем примере показана сигнатура целевого метода фабрики, а затем используется `x:Arguments`, который обращается к этой сигнатуре.</span><span class="sxs-lookup"><span data-stu-id="6ef40-139">The following example shows a target factory method signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6ef40-140">См. также</span><span class="sxs-lookup"><span data-stu-id="6ef40-140">See also</span></span>

- [<span data-ttu-id="6ef40-141">Определение пользовательских типов для использования со службами XAML .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6ef40-141">Defining Custom Types for Use with .NET Framework XAML Services</span></span>](defining-custom-types-for-use-with-net-framework-xaml-services.md)
- [<span data-ttu-id="6ef40-142">Общие сведения о языке XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="6ef40-142">XAML Overview (WPF)</span></span>](../../desktop-wpf/fundamentals/xaml.md)
