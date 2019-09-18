---
title: Директива x:FactoryMethod
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 586965dd4094e81fd830a09b64604cf33f195630
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053779"
---
# <a name="xfactorymethod-directive"></a><span data-ttu-id="44e82-102">Директива x:FactoryMethod</span><span class="sxs-lookup"><span data-stu-id="44e82-102">x:FactoryMethod Directive</span></span>
<span data-ttu-id="44e82-103">Указывает метод, отличный от конструктора, который обработчик XAML должен использовать для инициализации объекта после разрешения его резервного типа.</span><span class="sxs-lookup"><span data-stu-id="44e82-103">Specifies a method other than a constructor that a XAML processor should use to initialize an object after resolving its backing type.</span></span>  
  
## <a name="xaml-attribute-usage-no-xarguments"></a><span data-ttu-id="44e82-104">Использование атрибута XAML, без x:Arguments</span><span class="sxs-lookup"><span data-stu-id="44e82-104">XAML Attribute Usage, no x:Arguments</span></span>  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a><span data-ttu-id="44e82-105">Использование атрибута XAML, x:Arguments как элемент (ы)</span><span class="sxs-lookup"><span data-stu-id="44e82-105">XAML Attribute Usage, x:Arguments as Element(s)</span></span>  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="44e82-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="44e82-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`methodname`|<span data-ttu-id="44e82-107">Строковое имя метода, вызывающего обработчики XAML для инициализации экземпляра, указанного как `object`.</span><span class="sxs-lookup"><span data-stu-id="44e82-107">The string method name of a method that XAML processors call to initialize the instance specified as `object`.</span></span> <span data-ttu-id="44e82-108">См. заметки.</span><span class="sxs-lookup"><span data-stu-id="44e82-108">See Remarks.</span></span>|  
|`oneOrMoreObjectElements`|<span data-ttu-id="44e82-109">Один или несколько объектных элементов для объектов, задающих параметры метода фабрики.</span><span class="sxs-lookup"><span data-stu-id="44e82-109">One or more object elements for objects that specify factory method parameters.</span></span> <span data-ttu-id="44e82-110">Порядок важен; Он указывает порядок, в котором аргументы должны передаваться в фабричный метод.</span><span class="sxs-lookup"><span data-stu-id="44e82-110">Order is significant; it signifies the order in which arguments should be passed to the factory method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44e82-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="44e82-111">Remarks</span></span>  
 <span data-ttu-id="44e82-112">Если `methodname` является методом экземпляра, он не может быть квалифицирован.</span><span class="sxs-lookup"><span data-stu-id="44e82-112">If `methodname` is an instance method, it cannot be qualified.</span></span>  
  
 <span data-ttu-id="44e82-113">Поддерживаются статические методы в качестве фабричных методов.</span><span class="sxs-lookup"><span data-stu-id="44e82-113">Static methods as factory methods are supported.</span></span> <span data-ttu-id="44e82-114">Если `methodname` является статическим методом, `methodname` в качестве имени *типа*предоставляется. *имя_метода* , где *TypeName* присваивает имя классу, определяющему статический метод фабрики.</span><span class="sxs-lookup"><span data-stu-id="44e82-114">If `methodname` is a static method, `methodname` is provided as a *typeName*.*methodName* combination, where *typeName* names the class that defines the static factory method.</span></span> <span data-ttu-id="44e82-115">*имя TypeName* может быть уточнено префиксом, если ссылается на тип в сопоставленном xmlns.</span><span class="sxs-lookup"><span data-stu-id="44e82-115">*typeName* can be prefix-qualified if referring to a type in a mapped xmlns.</span></span> <span data-ttu-id="44e82-116">Тип *TypeName* может отличаться от `typeof(object)`типа.</span><span class="sxs-lookup"><span data-stu-id="44e82-116">*typeName* can be a different type than `typeof(object)`.</span></span>  
  
 <span data-ttu-id="44e82-117">Фабричный метод должен быть объявлен открытым методом типа, который создает соответствующий элемент объекта.</span><span class="sxs-lookup"><span data-stu-id="44e82-117">The factory method must be a declared public method of the type that backs the relevant object element.</span></span>  
  
 <span data-ttu-id="44e82-118">Метод фабрики должен возвращать экземпляр, который может быть назначен соответствующему объекту.</span><span class="sxs-lookup"><span data-stu-id="44e82-118">The factory method must return an instance that is assignable to the relevant object.</span></span> <span data-ttu-id="44e82-119">Фабричные методы никогда не должны возвращать значение null.</span><span class="sxs-lookup"><span data-stu-id="44e82-119">Factory methods should never return null.</span></span>  
  
 <span data-ttu-id="44e82-120">`x:Arguments`работает с принципом наилучшего соответствия для сигнатур методов фабрики.</span><span class="sxs-lookup"><span data-stu-id="44e82-120">`x:Arguments` operates on a principle of best match for signatures of factory methods.</span></span> <span data-ttu-id="44e82-121">При сопоставлении сначала вычисляется число параметров.</span><span class="sxs-lookup"><span data-stu-id="44e82-121">Matching evaluates the parameter count first.</span></span> <span data-ttu-id="44e82-122">Если для числа параметров существует несколько возможных совпадений, тип параметра вычисляется, и определяется наилучшее соответствие.</span><span class="sxs-lookup"><span data-stu-id="44e82-122">If there is more than one possible match for a parameter count, parameter type is then evaluated and best match is determined.</span></span> <span data-ttu-id="44e82-123">Если после этого этапа ознакомления по-прежнему возникает неоднозначность, поведение обработчика XAML не определено.</span><span class="sxs-lookup"><span data-stu-id="44e82-123">If there is still ambiguity after this phase of evaluation, XAML processor behavior is undefined.</span></span>  
  
 <span data-ttu-id="44e82-124">Использование `x:FactoryMethod` элемента не является элементом свойства в типичном смысле, поскольку разметка директивы не ссылается на тип содержащего его элемента.</span><span class="sxs-lookup"><span data-stu-id="44e82-124">The `x:FactoryMethod` element usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="44e82-125">Предполагается, что использование элементов менее распространено, чем использование атрибута.</span><span class="sxs-lookup"><span data-stu-id="44e82-125">It is expected that element usage is less common than attribute usage.</span></span> <span data-ttu-id="44e82-126">`x:Arguments`(использование атрибута или элемента) можно использовать вместе с `x:FactoryMethod` использованием элемента, но это не показано в разделе Использование.</span><span class="sxs-lookup"><span data-stu-id="44e82-126">`x:Arguments` (either attribute or element usage) can be used along with `x:FactoryMethod` element usage, but this is not specifically shown in the Usage sections.</span></span>  
  
 <span data-ttu-id="44e82-127">`x:FactoryMethod`Поскольку элемент должен предшествовать любым другим элементам свойств, должен предшествовать `x:Arguments` любому из них, кроме элементов, и должен предшествовать любому содержимому, внутреннему тексту или тексту инициализации.</span><span class="sxs-lookup"><span data-stu-id="44e82-127">`x:FactoryMethod` as an element must precede any other property elements, must precede any `x:Arguments` also provided as elements, and must precede any content/inner text/initialization text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44e82-128">См. также</span><span class="sxs-lookup"><span data-stu-id="44e82-128">See also</span></span>

- [<span data-ttu-id="44e82-129">x:Arguments - директива</span><span class="sxs-lookup"><span data-stu-id="44e82-129">x:Arguments Directive</span></span>](x-arguments-directive.md)
