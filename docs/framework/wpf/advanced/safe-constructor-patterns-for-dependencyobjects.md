---
title: Шаблоны безопасного конструктора для DependencyObjects
ms.date: 03/30/2017
helpviewer_keywords:
- constructor patterns for dependency objects [WPF]
- dependency objects [WPF], constructor patterns
- FXCop tool [WPF]
ms.assetid: f704b81c-449a-47a4-ace1-9332e3cc6d60
ms.openlocfilehash: 66e380a9428395c772d0dcfe45a995374774aec6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283831"
---
# <a name="safe-constructor-patterns-for-dependencyobjects"></a><span data-ttu-id="79029-102">Шаблоны безопасного конструктора для DependencyObjects</span><span class="sxs-lookup"><span data-stu-id="79029-102">Safe Constructor Patterns for DependencyObjects</span></span>
<span data-ttu-id="79029-103">Как правило, конструкторы классов не должны выполнять обратные вызовы, такие как виртуальные методы или делегаты, поскольку конструкторы могут вызываться в качестве базовой инициализации конструкторов для производного класса.</span><span class="sxs-lookup"><span data-stu-id="79029-103">Generally, class constructors should not call callbacks such as virtual methods or delegates, because constructors can be called as base initialization of constructors for a derived class.</span></span> <span data-ttu-id="79029-104">Ввод виртуального объекта может выполняться в состоянии незавершенной инициализации любого заданного объекта.</span><span class="sxs-lookup"><span data-stu-id="79029-104">Entering the virtual might be done at an incomplete initialization state of any given object.</span></span> <span data-ttu-id="79029-105">Однако сама система свойств внутренне вызывает и предоставляет обратные вызовы как часть системы свойств зависимостей.</span><span class="sxs-lookup"><span data-stu-id="79029-105">However, the property system itself calls and exposes callbacks internally, as part of the dependency property system.</span></span> <span data-ttu-id="79029-106">Как простая операция, аналогичная установке значения свойства зависимостей с помощью <xref:System.Windows.DependencyObject.SetValue%2A> Call, потенциально включает обратный вызов в процессе определения.</span><span class="sxs-lookup"><span data-stu-id="79029-106">As simple an operation as setting a dependency property value with <xref:System.Windows.DependencyObject.SetValue%2A> call potentially includes a callback somewhere in the determination.</span></span> <span data-ttu-id="79029-107">По этой причине следует соблюдать осторожность при установке значений свойств зависимостей в теле конструктора, что может стать проблемой, если тип используется в качестве базового класса.</span><span class="sxs-lookup"><span data-stu-id="79029-107">For this reason, you should be careful when setting dependency property values within the body of a constructor, which can become problematic if your type is used as a base class.</span></span> <span data-ttu-id="79029-108">Существует определенный шаблон для реализации <xref:System.Windows.DependencyObject> конструкторов, которые избегают определенных проблем с состояниями свойств зависимости и встроенными обратными вызовами, которые описаны здесь.</span><span class="sxs-lookup"><span data-stu-id="79029-108">There is a particular pattern for implementing <xref:System.Windows.DependencyObject> constructors that avoids specific problems with dependency property states and the inherent callbacks, which is documented here.</span></span>  

<a name="Property_System_Virtual_Methods"></a>   
## <a name="property-system-virtual-methods"></a><span data-ttu-id="79029-109">Виртуальные методы системы свойств</span><span class="sxs-lookup"><span data-stu-id="79029-109">Property System Virtual Methods</span></span>  
 <span data-ttu-id="79029-110">Следующие виртуальные методы или обратные вызовы потенциально вызываются во время вычислений <xref:System.Windows.DependencyObject.SetValue%2A> вызове, который устанавливает значение свойства зависимостей: <xref:System.Windows.ValidateValueCallback>, <xref:System.Windows.PropertyChangedCallback>, <xref:System.Windows.CoerceValueCallback>, <xref:System.Windows.DependencyObject.OnPropertyChanged%2A>.</span><span class="sxs-lookup"><span data-stu-id="79029-110">The following virtual methods or callbacks are potentially called during the computations of the <xref:System.Windows.DependencyObject.SetValue%2A> call that sets a dependency property value: <xref:System.Windows.ValidateValueCallback>, <xref:System.Windows.PropertyChangedCallback>, <xref:System.Windows.CoerceValueCallback>, <xref:System.Windows.DependencyObject.OnPropertyChanged%2A>.</span></span> <span data-ttu-id="79029-111">Каждый из этих виртуальных методов или обратных вызовов служит определенной цели в расширении универсальности системы свойств [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] и свойств зависимостей.</span><span class="sxs-lookup"><span data-stu-id="79029-111">Each of these virtual methods or callbacks serves a particular purpose in expanding the versatility of the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] property system and dependency properties.</span></span> <span data-ttu-id="79029-112">Дополнительные сведения об использовании этих виртуальных методов для настройки определения значений свойств см. в разделе [Проверка и обратные вызовы свойств зависимостей](dependency-property-callbacks-and-validation.md).</span><span class="sxs-lookup"><span data-stu-id="79029-112">For more information on how to use these virtuals to customize property value determination, see [Dependency Property Callbacks and Validation](dependency-property-callbacks-and-validation.md).</span></span>  
  
### <a name="fxcop-rule-enforcement-vs-property-system-virtuals"></a><span data-ttu-id="79029-113">Применение правил FXCop и виртуальные системы свойств</span><span class="sxs-lookup"><span data-stu-id="79029-113">FXCop Rule Enforcement vs. Property System Virtuals</span></span>  
 <span data-ttu-id="79029-114">Если используется средство FXCop от Майкрософт как часть процесса построения и создаются производные от определенных классов среды [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], вызывающие базовый конструктор, либо реализуются собственные свойства зависимостей в производных классах, можно столкнуться с нарушением правил FXCop.</span><span class="sxs-lookup"><span data-stu-id="79029-114">If you use the Microsoft tool FXCop as part of your build process, and you either derive from certain [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] framework classes calling the base constructor, or implement your own dependency properties on derived classes, you might encounter a particular FXCop rule violation.</span></span> <span data-ttu-id="79029-115">Строка имени для этого нарушения:</span><span class="sxs-lookup"><span data-stu-id="79029-115">The name string for this violation is:</span></span>  
  
 `DoNotCallOverridableMethodsInConstructors`  
  
 <span data-ttu-id="79029-116">Это правило, которое является частью набора общих правил по умолчанию для FXCop.</span><span class="sxs-lookup"><span data-stu-id="79029-116">This is a rule that is part of the default public rule set for FXCop.</span></span> <span data-ttu-id="79029-117">Это правило может сообщать о трассировке по системе свойств зависимостей, которая в конечном итоге вызывает виртуальный метод системы свойств зависимостей.</span><span class="sxs-lookup"><span data-stu-id="79029-117">What this rule might be reporting is a trace through the dependency property system that eventually calls a dependency property system virtual method.</span></span> <span data-ttu-id="79029-118">Нарушение этого правила может по-прежнему отображаться даже после применения рекомендуемых шаблонов конструктора, описанных в этом разделе, поэтому может потребоваться отключить или запретить это правило в конфигурации набора правил FXCop.</span><span class="sxs-lookup"><span data-stu-id="79029-118">This rule violation might continue to appear even after following the recommended constructor patterns documented in this topic, so you might need to disable or suppress that rule in your FXCop rule set configuration.</span></span>  
  
### <a name="most-issues-come-from-deriving-classes-not-using-existing-classes"></a><span data-ttu-id="79029-119">Большинство проблем возникает из-за производных классов, а не использования существующих</span><span class="sxs-lookup"><span data-stu-id="79029-119">Most Issues Come From Deriving Classes, Not Using Existing Classes</span></span>  
 <span data-ttu-id="79029-120">Проблемы, о которых сообщает это правило, происходят при создании производного класса от класса, реализуемого с помощью виртуальных методов в его последовательности создания.</span><span class="sxs-lookup"><span data-stu-id="79029-120">The issues reported by this rule occur when a class that you implement with virtual methods in its construction sequence is then derived from.</span></span> <span data-ttu-id="79029-121">Если запечатать класс или любым другим образом запретить создание производных от него классов, рассматриваемые здесь проблемы, связанные с правилом FXCop, для вас не применимы.</span><span class="sxs-lookup"><span data-stu-id="79029-121">If you seal your class, or otherwise know or enforce that your class will not be derived from, the considerations explained here and the issues that motivated the FXCop rule do not apply to you.</span></span> <span data-ttu-id="79029-122">Тем не менее при создании классов таким образом, чтобы они предназначались для использования в качестве базовых классов, например при создании шаблонов или расширяемого набора библиотек элементов управления, необходимо следовать шаблонам, рекомендуемым здесь для конструкторов.</span><span class="sxs-lookup"><span data-stu-id="79029-122">However, if you are authoring classes in such a way that they are intended to be used as base classes, for instance if you are creating templates, or an expandable control library set, you should follow the patterns recommended here for constructors.</span></span>  
  
### <a name="default-constructors-must-initialize-all-values-requested-by-callbacks"></a><span data-ttu-id="79029-123">Конструкторы по умолчанию должны инициализировать все значения, запрашиваемые обратными вызовами</span><span class="sxs-lookup"><span data-stu-id="79029-123">Default Constructors Must Initialize All Values Requested By Callbacks</span></span>  
 <span data-ttu-id="79029-124">Все члены экземпляра, используемые переопределениями класса или обратными вызовами (обратные вызовы из списка в разделе "виртуальные свойства системы свойств"), должны быть инициализированы в конструкторе без параметров класса, даже если некоторые из этих значений заполняются "реальными" значениями через параметры конструкторов без параметров.</span><span class="sxs-lookup"><span data-stu-id="79029-124">Any instance members that are used by your class overrides or callbacks (the callbacks from the list in the Property System Virtuals section) must be initialized in your class parameterless constructor, even if some of those values are filled by "real" values through parameters of the nonparameterless constructors.</span></span>  
  
 <span data-ttu-id="79029-125">Следующий пример кода (и последующие примеры) представляет собой пример псевдокода C#, который нарушает это правило и объясняет проблему.</span><span class="sxs-lookup"><span data-stu-id="79029-125">The following example code (and subsequent examples) is a pseudo-C# example that violates this rule and explains the problem:</span></span>  
  
```csharp  
public class MyClass : DependencyObject  
{  
    public MyClass() {}  
    public MyClass(object toSetWobble)  
        : this()  
    {  
        Wobble = toSetWobble; //this is backed by a DependencyProperty  
        _myList = new ArrayList();    // this line should be in the default ctor  
    }  
    public static readonly DependencyProperty WobbleProperty =   
        DependencyProperty.Register("Wobble", typeof(object), typeof(MyClass));  
    public object Wobble  
    {  
        get { return GetValue(WobbleProperty); }  
        set { SetValue(WobbleProperty, value); }  
    }  
    protected override void OnPropertyChanged(DependencyPropertyChangedEventArgs e)  
    {  
        int count = _myList.Count;    // null-reference exception  
    }  
    private ArrayList _myList;  
}  
```  
  
 <span data-ttu-id="79029-126">Когда код приложения вызывает `new MyClass(objectvalue)`, вызывает конструктор без параметров и конструкторы базового класса.</span><span class="sxs-lookup"><span data-stu-id="79029-126">When application code calls `new MyClass(objectvalue)`, this calls the parameterless constructor and base class constructors.</span></span> <span data-ttu-id="79029-127">Затем задается `Property1 = object1`, который вызывает виртуальный метод `OnPropertyChanged` на `MyClass`е-владельце <xref:System.Windows.DependencyObject>.</span><span class="sxs-lookup"><span data-stu-id="79029-127">Then it sets `Property1 = object1`, which calls the virtual method `OnPropertyChanged` on the owning `MyClass` <xref:System.Windows.DependencyObject>.</span></span>  <span data-ttu-id="79029-128">Переопределение ссылается на `_myList`, который еще не был инициализирован.</span><span class="sxs-lookup"><span data-stu-id="79029-128">The override refers to `_myList`, which has not been initialized yet.</span></span>  
  
 <span data-ttu-id="79029-129">Один из способов избежать этих проблем — убедиться в том, что обратные вызовы используют только другие свойства зависимостей, а каждое такое свойство зависимости имеет установленное по умолчанию значение в составе его зарегистрированных метаданных.</span><span class="sxs-lookup"><span data-stu-id="79029-129">One way to avoid these issues is to make sure that callbacks use only other dependency properties, and that each such dependency property has an established default value as part of its registered metadata.</span></span>  
  
<a name="Safe_Constructor_Patterns"></a>   
## <a name="safe-constructor-patterns"></a><span data-ttu-id="79029-130">Шаблоны безопасных конструкторов</span><span class="sxs-lookup"><span data-stu-id="79029-130">Safe Constructor Patterns</span></span>  
 <span data-ttu-id="79029-131">Во избежание риска неполной инициализации, если класс используется как базовый, используйте эти шаблоны.</span><span class="sxs-lookup"><span data-stu-id="79029-131">To avoid the risks of incomplete initialization if your class is used as a base class, follow these patterns:</span></span>  
  
#### <a name="parameterless-constructors-calling-base-initialization"></a><span data-ttu-id="79029-132">Конструкторы без параметров, вызывающие базовую инициализацию</span><span class="sxs-lookup"><span data-stu-id="79029-132">Parameterless constructors calling base initialization</span></span>  
 <span data-ttu-id="79029-133">Реализуйте эти конструкторы, вызывающие базовое значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="79029-133">Implement these constructors calling the base default:</span></span>  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass() : base() {  
        // ALL class initialization, including initial defaults for   
        // possible values that other ctors specify or that callbacks need.  
    }  
}  
```  
  
#### <a name="non-default-convenience-constructors-not-matching-any-base-signatures"></a><span data-ttu-id="79029-134">Нестандартные (удобные) конструкторы, не соответствующие базовым сигнатурам</span><span class="sxs-lookup"><span data-stu-id="79029-134">Non-default (convenience) constructors, not matching any base signatures</span></span>  
 <span data-ttu-id="79029-135">Если эти конструкторы используют параметры для установки свойств зависимостей в инициализации, сначала следует вызвать собственный конструктор без параметров класса для инициализации, а затем использовать параметры для установки свойств зависимостей.</span><span class="sxs-lookup"><span data-stu-id="79029-135">If these constructors use the parameters to set dependency properties in the initialization, first call your own class parameterless constructor for initialization, and then use the parameters to set dependency properties.</span></span> <span data-ttu-id="79029-136">Это могут быть либо свойства зависимостей, определенные вашим классом, либо свойства зависимостей, унаследованные от базовых классов, но в любом случае используйте следующий шаблон:</span><span class="sxs-lookup"><span data-stu-id="79029-136">These could either be dependency properties defined by your class, or dependency properties inherited from base classes, but in either case use the following pattern:</span></span>  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### <a name="non-default-convenience-constructors-which-do-match-base-signatures"></a><span data-ttu-id="79029-137">Нестандартные (удобные) конструкторы, которые соответствуют базовым сигнатурам</span><span class="sxs-lookup"><span data-stu-id="79029-137">Non-default (convenience) constructors, which do match base signatures</span></span>  
 <span data-ttu-id="79029-138">Вместо вызова базового конструктора с такой же параметризации снова вызовите собственный конструктор без параметров класса.</span><span class="sxs-lookup"><span data-stu-id="79029-138">Instead of calling the base constructor with the same parameterization, again call your own class' parameterless constructor.</span></span> <span data-ttu-id="79029-139">Не следует вызывать базовый инициализатор. Вместо этого нужно вызвать `this()`.</span><span class="sxs-lookup"><span data-stu-id="79029-139">Do not call the base initializer; instead you should call `this()`.</span></span> <span data-ttu-id="79029-140">Затем воспроизведите исходное поведение конструктора, используя переданные параметры в качестве значений для установки соответствующих свойств.</span><span class="sxs-lookup"><span data-stu-id="79029-140">Then reproduce the original constructor behavior by using the passed parameters as values for setting the relevant properties.</span></span> <span data-ttu-id="79029-141">Используйте оригинальную документацию по базовому конструктору в качестве руководства по определению свойств, которые задаются определенными параметрами.</span><span class="sxs-lookup"><span data-stu-id="79029-141">Use the original base constructor documentation for guidance in determining the properties that the particular parameters are intended to set:</span></span>  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### <a name="must-match-all-signatures"></a><span data-ttu-id="79029-142">Должен соответствовать всем сигнатурам</span><span class="sxs-lookup"><span data-stu-id="79029-142">Must match all signatures</span></span>  
 <span data-ttu-id="79029-143">В случаях, когда базовый тип имеет несколько сигнатур, необходимо намеренно сопоставлять все возможные сигнатуры с реализацией собственного конструктора, которая использует рекомендованный шаблон вызова конструктора без параметров класса перед дальнейшим заданием свойства.</span><span class="sxs-lookup"><span data-stu-id="79029-143">For cases where the base type has multiple signatures, you must deliberately match all possible signatures with a constructor implementation of your own that uses the recommended pattern of calling the class parameterless constructor before setting further properties.</span></span>  
  
#### <a name="setting-dependency-properties-with-setvalue"></a><span data-ttu-id="79029-144">Установка свойств зависимостей с помощью SetValue</span><span class="sxs-lookup"><span data-stu-id="79029-144">Setting dependency properties with SetValue</span></span>  
 <span data-ttu-id="79029-145">Те же шаблоны применяются, если вы устанавливаете свойство, которое не имеет оболочки для удобства настройки свойств, и устанавливает значения с помощью <xref:System.Windows.DependencyObject.SetValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="79029-145">These same patterns apply if you are setting a property that does not have a wrapper for property setting convenience, and set values with <xref:System.Windows.DependencyObject.SetValue%2A>.</span></span> <span data-ttu-id="79029-146">Вызовы <xref:System.Windows.DependencyObject.SetValue%2A>, которые проходят через параметры конструктора, также должны вызывать конструктор класса "без параметров" для инициализации.</span><span class="sxs-lookup"><span data-stu-id="79029-146">Your calls to <xref:System.Windows.DependencyObject.SetValue%2A> that pass through constructor parameters should also call the class' parameterless constructor for initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79029-147">См. также</span><span class="sxs-lookup"><span data-stu-id="79029-147">See also</span></span>

- [<span data-ttu-id="79029-148">Пользовательские свойства зависимостей</span><span class="sxs-lookup"><span data-stu-id="79029-148">Custom Dependency Properties</span></span>](custom-dependency-properties.md)
- [<span data-ttu-id="79029-149">Общие сведения о свойствах зависимости</span><span class="sxs-lookup"><span data-stu-id="79029-149">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="79029-150">Безопасность свойства зависимостей</span><span class="sxs-lookup"><span data-stu-id="79029-150">Dependency Property Security</span></span>](dependency-property-security.md)
