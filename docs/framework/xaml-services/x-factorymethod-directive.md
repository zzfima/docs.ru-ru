---
title: "Директива x:FactoryMethod"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 0d53db49961c2a75e4547f6b57240cefd2cc17c3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="xfactorymethod-directive"></a><span data-ttu-id="4c5d3-102">Директива x:FactoryMethod</span><span class="sxs-lookup"><span data-stu-id="4c5d3-102">x:FactoryMethod Directive</span></span>
<span data-ttu-id="4c5d3-103">Указывает метод, отличный от конструктора, который процессор XAML должен использовать для инициализации объекта после разрешения его резервного типа.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-103">Specifies a method other than a constructor that a XAML processor should use to initialize an object after resolving its backing type.</span></span>  
  
## <a name="xaml-attribute-usage-no-xarguments"></a><span data-ttu-id="4c5d3-104">Использование атрибута XAML, не x: Arguments</span><span class="sxs-lookup"><span data-stu-id="4c5d3-104">XAML Attribute Usage, no x:Arguments</span></span>  
  
```  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a><span data-ttu-id="4c5d3-105">Использование атрибута XAML, x: аргументы в виде элементов</span><span class="sxs-lookup"><span data-stu-id="4c5d3-105">XAML Attribute Usage, x:Arguments as Element(s)</span></span>  
  
```  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="4c5d3-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="4c5d3-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`methodname`|<span data-ttu-id="4c5d3-107">Метод строковое имя метода, который вызывают процессоры XAML для инициализации экземпляра, заданного как `object`.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-107">The string method name of a method that XAML processors call to initialize the instance specified as `object`.</span></span> <span data-ttu-id="4c5d3-108">См. заметки.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-108">See Remarks.</span></span>|  
|`oneOrMoreObjectElements`|<span data-ttu-id="4c5d3-109">Один или несколько элементов объекта для объектов, которые задают параметры метода фабрики.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-109">One or more object elements for objects that specify factory method parameters.</span></span> <span data-ttu-id="4c5d3-110">Порядок имеет значение; обозначает порядок, в котором аргументы должны быть переданы в метод фабрики.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-110">Order is significant; it signifies the order in which arguments should be passed to the factory method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c5d3-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="4c5d3-111">Remarks</span></span>  
 <span data-ttu-id="4c5d3-112">Если `methodname` является методом экземпляра не может быть квалифицирован.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-112">If `methodname` is an instance method, it cannot be qualified.</span></span>  
  
 <span data-ttu-id="4c5d3-113">Поддерживаются статические методы как фабричные методы.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-113">Static methods as factory methods are supported.</span></span> <span data-ttu-id="4c5d3-114">Если `methodname` — статический метод `methodname` предоставляется как *typeName*. *имя_метода* сочетания, где *typeName* создается класс, который определяет статический фабричный метод с именем.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-114">If `methodname` is a static method, `methodname` is provided as a *typeName*.*methodName* combination, where *typeName* names the class that defines the static factory method.</span></span> <span data-ttu-id="4c5d3-115">*typeName* может иметь префикс, если ссылается на тип в сопоставленных xmlns.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-115">*typeName* can be prefix-qualified if referring to a type in a mapped xmlns.</span></span> <span data-ttu-id="4c5d3-116">*typeName* может быть отличается от типа `typeof(``object``)`.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-116">*typeName* can be a different type than `typeof(``object``)`.</span></span>  
  
 <span data-ttu-id="4c5d3-117">Фабричный метод должен быть объявлен открытым методом типа, который возвращает соответствующий элемент объекта.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-117">The factory method must be a declared public method of the type that backs the relevant object element.</span></span>  
  
 <span data-ttu-id="4c5d3-118">Фабричный метод должен возвращать экземпляр, который может быть назначен соответствующий объект.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-118">The factory method must return an instance that is assignable to the relevant object.</span></span> <span data-ttu-id="4c5d3-119">Фабричные методы никогда не должен возвращать значение null.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-119">Factory methods should never return null.</span></span>  
  
 <span data-ttu-id="4c5d3-120">`x:Arguments`работает по принципу наилучшего соответствия для сигнатур методов фабрик.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-120">`x:Arguments` operates on a principle of best match for signatures of factory methods.</span></span> <span data-ttu-id="4c5d3-121">Сопоставление оценивает количество параметров.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-121">Matching evaluates the parameter count first.</span></span> <span data-ttu-id="4c5d3-122">Если имеется более одного возможного соответствия для числа параметров, тип параметра является определяется соответствие вычисляется и рекомендации.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-122">If there is more than one possible match for a parameter count, parameter type is then evaluated and best match is determined.</span></span> <span data-ttu-id="4c5d3-123">Если после этого этапа оценки остается неоднозначность, поведение процессора XAML не определено.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-123">If there is still ambiguity after this phase of evaluation, XAML processor behavior is undefined.</span></span>  
  
 <span data-ttu-id="4c5d3-124">`x:FactoryMethod` Использование элемента не использование элемента свойства в типичных смысле, так как директив разметки не ссылается на объект элемента, содержащего типа.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-124">The `x:FactoryMethod` element usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="4c5d3-125">Предполагается, что элементы используются реже, чем использование атрибута.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-125">It is expected that element usage is less common than attribute usage.</span></span> <span data-ttu-id="4c5d3-126">`x:Arguments`(атрибут или элемент) можно использовать вместе с `x:FactoryMethod` использование элемента, но это не отображается в разделах использования.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-126">`x:Arguments` (either attribute or element usage) can be used along with `x:FactoryMethod` element usage, but this is not specifically shown in the Usage sections.</span></span>  
  
 <span data-ttu-id="4c5d3-127">`x:FactoryMethod`как элемент должен предшествовать любых других свойств элементов, должны указываться до любых `x:Arguments` также представлены в виде элементов и должен предшествовать любой текст содержимого или внутренний текст и инициализации.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-127">`x:FactoryMethod` as an element must precede any other property elements, must precede any `x:Arguments` also provided as elements, and must precede any content/inner text/initialization text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c5d3-128">См. также</span><span class="sxs-lookup"><span data-stu-id="4c5d3-128">See Also</span></span>  
 [<span data-ttu-id="4c5d3-129">x:Arguments - директива</span><span class="sxs-lookup"><span data-stu-id="4c5d3-129">x:Arguments Directive</span></span>](../../../docs/framework/xaml-services/x-arguments-directive.md)
