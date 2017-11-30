---
title: "Директива x:Arguments"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
caps.latest.revision: "12"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 00f605bba709f0ce5f3238ccc3c6ac6cd962f0a4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="xarguments-directive"></a><span data-ttu-id="2d6de-102">Директива x:Arguments</span><span class="sxs-lookup"><span data-stu-id="2d6de-102">x:Arguments Directive</span></span>
<span data-ttu-id="2d6de-103">Упаковывает аргументы создания для объявления объекта элемент конструктора не по умолчанию в языке XAML или объявления метода объекта фабрики.</span><span class="sxs-lookup"><span data-stu-id="2d6de-103">Packages construction arguments for a non-default constructor object element declaration in XAML, or for a factory method object declaration.</span></span>  
  
## <a name="xaml-element-usage-nondefault-constructor"></a><span data-ttu-id="2d6de-104">Использование элемента XAML (нестандартного конструктора)</span><span class="sxs-lookup"><span data-stu-id="2d6de-104">XAML Element Usage (Nondefault constructor)</span></span>  
  
```  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-element-usage-factory-method"></a><span data-ttu-id="2d6de-105">Использование элемента XAML (фабричный метод)</span><span class="sxs-lookup"><span data-stu-id="2d6de-105">XAML Element Usage (factory method)</span></span>  
  
```  
<object x:FactoryMethod="methodName"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="2d6de-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="2d6de-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`oneOrMoreObjectElements`|<span data-ttu-id="2d6de-107">Один или несколько элементов объекта, указывающих аргументы должны быть переданы резервное копирование не по умолчанию конструктор или метод фабрики.</span><span class="sxs-lookup"><span data-stu-id="2d6de-107">One or more object elements that specify arguments to be passed to the backing non-default constructor or factory method.</span></span><br /><br /> <span data-ttu-id="2d6de-108">Типичным использованием является используйте текст инициализации в элементах объекта, чтобы указать значения фактических аргументов.</span><span class="sxs-lookup"><span data-stu-id="2d6de-108">Typical usage is to use initialization text within the object elements to specify the actual argument values.</span></span> <span data-ttu-id="2d6de-109">Примеры см. раздел.</span><span class="sxs-lookup"><span data-stu-id="2d6de-109">See Examples section.</span></span><br /><br /> <span data-ttu-id="2d6de-110">Важен порядок элементов.</span><span class="sxs-lookup"><span data-stu-id="2d6de-110">The order of the elements is significant.</span></span> <span data-ttu-id="2d6de-111">Типов XAML в порядке необходимо соответствуют типам и введите порядок перегрузка метода резервного конструктора или фабрики.</span><span class="sxs-lookup"><span data-stu-id="2d6de-111">The XAML types in order must match the types and type order of the backing constructor or factory method overload.</span></span>|  
|`methodName`|<span data-ttu-id="2d6de-112">Имя фабричный метод, который обрабатывает любые `x:Arguments` аргументы.</span><span class="sxs-lookup"><span data-stu-id="2d6de-112">The name of the factory method that should process any `x:Arguments` arguments.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="2d6de-113">Зависимости</span><span class="sxs-lookup"><span data-stu-id="2d6de-113">Dependencies</span></span>  
 <span data-ttu-id="2d6de-114">`x:FactoryMethod`можно изменить область и поведение где `x:Arguments` применяется.</span><span class="sxs-lookup"><span data-stu-id="2d6de-114">`x:FactoryMethod` can modify the scope and behavior where `x:Arguments` applies.</span></span>  
  
 <span data-ttu-id="2d6de-115">Если не `x:FactoryMethod` указано, `x:Arguments` применяется к альтернативные подписи (не по умолчанию) резервных конструкторов.</span><span class="sxs-lookup"><span data-stu-id="2d6de-115">If no `x:FactoryMethod` is specified, `x:Arguments` applies to alternate (non-default) signatures of the backing constructors.</span></span>  
  
 <span data-ttu-id="2d6de-116">Если `x:FactoryMethod` указано, `x:Arguments` применяется перегрузка именованного метода.</span><span class="sxs-lookup"><span data-stu-id="2d6de-116">If `x:FactoryMethod` is specified, `x:Arguments` applies to an overload of the named method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d6de-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="2d6de-117">Remarks</span></span>  
 <span data-ttu-id="2d6de-118">XAML 2006 может поддерживать инициализации не по умолчанию через текст инициализации.</span><span class="sxs-lookup"><span data-stu-id="2d6de-118">XAML 2006 can support non-default initialization through initialization text.</span></span> <span data-ttu-id="2d6de-119">Однако Практическое применение методики построения текста инициализации ограничено.</span><span class="sxs-lookup"><span data-stu-id="2d6de-119">However, the practical application of an initialization text construction technique is limited.</span></span> <span data-ttu-id="2d6de-120">Текст инициализации рассматривается как одну текстовую строку; Таким образом он только добавляет возможность инициализации одного параметра не определен преобразователь типов для поведение конструктора, который может выполнять синтаксический анализ элементы пользовательских данных и пользовательских разделителей в строке.</span><span class="sxs-lookup"><span data-stu-id="2d6de-120">Initialization text is treated as a single text string; therefore, it only adds capability for a single parameter initialization unless a type converter is defined for the construction behavior that can parse custom information items and custom delimiters from the string.</span></span> <span data-ttu-id="2d6de-121">Кроме того текстовую строку для логики объекта является потенциально преобразователя типа данного анализатор XAML собственного по умолчанию для обработки примитивов, отличное от true строки.</span><span class="sxs-lookup"><span data-stu-id="2d6de-121">Also, the text string to object logic is potentially a given XAML parser's native default type converter for handling primitives other than a true string.</span></span>  
  
 <span data-ttu-id="2d6de-122">`x:Arguments` Использование XAML не использование элемента свойства в типичных смысле, так как директив разметки не ссылается на объект элемента, содержащего типа.</span><span class="sxs-lookup"><span data-stu-id="2d6de-122">The `x:Arguments` XAML usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="2d6de-123">Это больше похоже на другие директивы, такие как `x:Code` где этот элемент разграничивает диапазон, в котором следует интерпретировать разметку отличное от по умолчанию для дочернего содержимого.</span><span class="sxs-lookup"><span data-stu-id="2d6de-123">It is more akin to other directives such as `x:Code` where the element demarks a range in which the markup should be interpreted as other than the default for child contents.</span></span> <span data-ttu-id="2d6de-124">В этом случае тип каждого элемента объекта XAML передает сведения о типов аргументов, которая используется средства синтаксического анализа XAML, чтобы определить, какая сигнатура метода фабрики определенный конструктор `x:Arguments` использования пытается ссылаться.</span><span class="sxs-lookup"><span data-stu-id="2d6de-124">In this case, the XAML type of each object element communicates information about the argument types, which is used by XAML parsers to determine which specific constructor factory method signature an `x:Arguments` usage is attempting to reference.</span></span>  
  
 <span data-ttu-id="2d6de-125">`x:Arguments`для элемента объекта, создаваемого должны предшествовать любые другие элементы свойств, содержимое, внутренний текст или строки инициализации элемента объекта.</span><span class="sxs-lookup"><span data-stu-id="2d6de-125">`x:Arguments` for an object element being constructed must precede any other property elements, content, inner text, or initialization strings of the object element.</span></span> <span data-ttu-id="2d6de-126">Элементы объекта в `x:Arguments` могут включать атрибуты и строки инициализации с этого типа XAML и его базовым методом фабрики или конструктора.</span><span class="sxs-lookup"><span data-stu-id="2d6de-126">The object elements within `x:Arguments` can include attributes and initialization strings, as permitted by that XAML type and its backing constructor or factory method.</span></span> <span data-ttu-id="2d6de-127">Для объекта или аргументы можно указать пользовательские типы XAML или типов XAML, которые в противном случае за пределами пространства имен XAML по умолчанию, ссылаясь на установленное префикс сопоставления.</span><span class="sxs-lookup"><span data-stu-id="2d6de-127">For either the object or the arguments, you can specify custom XAML types or XAML types that are otherwise outside the default XAML namespace by referencing established prefix mappings.</span></span>  
  
 <span data-ttu-id="2d6de-128">Обработчики XAML следуйте приведенным ниже рекомендациям, чтобы определить, как аргументы заданы в `x:Arguments` следует использовать для создания объекта.</span><span class="sxs-lookup"><span data-stu-id="2d6de-128">XAML processors use the following guidelines to determine how the arguments specified in `x:Arguments` should be used to construct an object.</span></span> <span data-ttu-id="2d6de-129">Если `x:FactoryMethod` указан, сведения сравниваются в указанный `x:FactoryMethod` (Обратите внимание, что значение `x:FactoryMethod` — это имя метода, а именованный метод может иметь перегруженные методы.</span><span class="sxs-lookup"><span data-stu-id="2d6de-129">If `x:FactoryMethod` is specified, information is compared to the specified `x:FactoryMethod` (note that the value of `x:FactoryMethod` is the method name, and the named method can have overloads.</span></span> <span data-ttu-id="2d6de-130">Если `x:FactoryMethod` не указан, сведения сравниваются с набор всех перегруженных версий открытый конструктор объекта.</span><span class="sxs-lookup"><span data-stu-id="2d6de-130">If `x:FactoryMethod` is not specified, information is compared to the set of all public constructor overloads of the object.</span></span> <span data-ttu-id="2d6de-131">Логика обработки XAML затем сравнивает число параметров и выбирает перегрузку с арностью сопоставления.</span><span class="sxs-lookup"><span data-stu-id="2d6de-131">XAML processing logic then compares the number of parameters and selects the overload with matching arity.</span></span> <span data-ttu-id="2d6de-132">Если имеется более одного совпадения, процессор XAML должен сравнивать типы параметров, исходя из предоставленного объекта элементы типов XAML.</span><span class="sxs-lookup"><span data-stu-id="2d6de-132">If there is more than one match, the XAML processor should compare the types of the parameters based on the XAML types of the provided object elements.</span></span> <span data-ttu-id="2d6de-133">Если по-прежнему более одного совпадения, поведение процессора XAML не определено.</span><span class="sxs-lookup"><span data-stu-id="2d6de-133">If there is still more than one match, the XAML processor behavior is undefined.</span></span> <span data-ttu-id="2d6de-134">Если `x:FactoryMethod` указан, но метод не может быть устранена, обработчик XAML должен создать исключение.</span><span class="sxs-lookup"><span data-stu-id="2d6de-134">If a `x:FactoryMethod` is specified but the method cannot be resolved, a XAML processor should throw an exception.</span></span>  
  
 <span data-ttu-id="2d6de-135">Использование атрибута XAML `<x:Arguments>string</x:Arguments>` технически возможно.</span><span class="sxs-lookup"><span data-stu-id="2d6de-135">A XAML attribute usage `<x:Arguments>string</x:Arguments>` is technically possible.</span></span> <span data-ttu-id="2d6de-136">Тем не менее это обеспечивает нет новых возможностей, что можно сделать в противном случае через инициализации текста и преобразователи типов, и с помощью этого синтаксиса не является необходимым в возможности XAML 2009 фабрики метод.</span><span class="sxs-lookup"><span data-stu-id="2d6de-136">However, this provides no capabilities beyond what could be done otherwise through initialization text and type converters, and using this syntax is not the design intention of the XAML 2009 factory method features.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2d6de-137">Примеры</span><span class="sxs-lookup"><span data-stu-id="2d6de-137">Examples</span></span>  
 <span data-ttu-id="2d6de-138">В следующем примере показано конструктора не по умолчанию подпись, а затем использования XAML `x:Arguments` , обращающийся к этой подписи.</span><span class="sxs-lookup"><span data-stu-id="2d6de-138">The following example shows a non-default constructor signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
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
  
 <span data-ttu-id="2d6de-139">В следующем примере показано сигнатура метода целевой фабрики, а затем использования XAML `x:Arguments` , обращающийся к этой подписи.</span><span class="sxs-lookup"><span data-stu-id="2d6de-139">The following example shows a target factory method signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2d6de-140">См. также</span><span class="sxs-lookup"><span data-stu-id="2d6de-140">See Also</span></span>  
 [<span data-ttu-id="2d6de-141">Определение пользовательских типов для использования со службами XAML .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2d6de-141">Defining Custom Types for Use with .NET Framework XAML Services</span></span>](../../../docs/framework/xaml-services/defining-custom-types-for-use-with-net-framework-xaml-services.md)  
 [<span data-ttu-id="2d6de-142">Общие сведения о языке XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="2d6de-142">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
