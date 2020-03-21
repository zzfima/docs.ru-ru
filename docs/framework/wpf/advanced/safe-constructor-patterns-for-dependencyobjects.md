---
title: Шаблоны безопасного конструктора для DependencyObjects
ms.date: 03/30/2017
helpviewer_keywords:
- constructor patterns for dependency objects [WPF]
- dependency objects [WPF], constructor patterns
- FXCop tool [WPF]
ms.assetid: f704b81c-449a-47a4-ace1-9332e3cc6d60
ms.openlocfilehash: 6d6ff444b99ca893e687731c56a48ea3ac072dd0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187234"
---
# <a name="safe-constructor-patterns-for-dependencyobjects"></a>Шаблоны безопасного конструктора для DependencyObjects
Как правило, конструкторы классов не должны выполнять обратные вызовы, такие как виртуальные методы или делегаты, поскольку конструкторы могут вызываться в качестве базовой инициализации конструкторов для производного класса. Ввод виртуального объекта может выполняться в состоянии незавершенной инициализации любого заданного объекта. Однако сама система свойств внутренне вызывает и предоставляет обратные вызовы как часть системы свойств зависимостей. Такая же простая операция, как <xref:System.Windows.DependencyObject.SetValue%2A> установка значения свойства зависимости с вызовом потенциально включает обратный вызов где-то в определении. По этой причине следует соблюдать осторожность при установке значений свойств зависимостей в теле конструктора, что может стать проблемой, если тип используется в качестве базового класса. Существует особая схема для <xref:System.Windows.DependencyObject> реализации конструкторов, которая позволяет избежать специфических проблем с состояниями свойств зависимости и присущих обратных вызовов, которые описаны здесь.  

<a name="Property_System_Virtual_Methods"></a>
## <a name="property-system-virtual-methods"></a>Виртуальные методы системы свойств  
 Следующие виртуальные методы или обратные вызовы потенциально называются во время <xref:System.Windows.DependencyObject.SetValue%2A> вычислений <xref:System.Windows.ValidateValueCallback>вызова, который устанавливает значение свойства зависимости: , <xref:System.Windows.PropertyChangedCallback>. <xref:System.Windows.CoerceValueCallback> <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> Каждый из этих виртуальных методов или обратных вызовов служит определенной цели в расширении универсальности системы свойств [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] и свойств зависимостей. Дополнительные сведения об использовании этих виртуальных методов для настройки определения значений свойств см. в разделе [Проверка и обратные вызовы свойств зависимостей](dependency-property-callbacks-and-validation.md).  
  
### <a name="fxcop-rule-enforcement-vs-property-system-virtuals"></a>FxCop Соблюдение правил против собственности системы виртуальных  
 Если используется средство FXCop от Майкрософт как часть процесса построения и создаются производные от определенных классов среды [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], вызывающие базовый конструктор, либо реализуются собственные свойства зависимостей в производных классах, можно столкнуться с нарушением правил FXCop. Строка имени для этого нарушения:  
  
 `DoNotCallOverridableMethodsInConstructors`  
  
 Это правило, которое является частью набора общих правил по умолчанию для FXCop. Это правило может сообщать о трассировке по системе свойств зависимостей, которая в конечном итоге вызывает виртуальный метод системы свойств зависимостей. Нарушение этого правила может по-прежнему отображаться даже после применения рекомендуемых шаблонов конструктора, описанных в этом разделе, поэтому может потребоваться отключить или запретить это правило в конфигурации набора правил FXCop.  
  
### <a name="most-issues-come-from-deriving-classes-not-using-existing-classes"></a>Большинство проблем возникает из-за производных классов, а не использования существующих  
 Проблемы, о которых сообщает это правило, происходят при создании производного класса от класса, реализуемого с помощью виртуальных методов в его последовательности создания. Если запечатать класс или любым другим образом запретить создание производных от него классов, рассматриваемые здесь проблемы, связанные с правилом FXCop, для вас не применимы. Тем не менее при создании классов таким образом, чтобы они предназначались для использования в качестве базовых классов, например при создании шаблонов или расширяемого набора библиотек элементов управления, необходимо следовать шаблонам, рекомендуемым здесь для конструкторов.  
  
### <a name="default-constructors-must-initialize-all-values-requested-by-callbacks"></a>Конструкторы по умолчанию должны инициализировать все значения, запрашиваемые обратными вызовами  
 Любые экземпляры, которые используются вашим классом переопределения или обратные вызовы (обратные вызовы из списка в разделе Недвижимость системы Виртуальные) должны быть инициализированы в вашем классе без парапараметров конструктора, даже если некоторые из этих значений заполнены "реальные" значения через параметров безпаратиров конструкторов.  
  
 Следующий пример кода (и последующие примеры) представляет собой пример псевдокода C#, который нарушает это правило и объясняет проблему.  
  
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
  
 При вызове `new MyClass(objectvalue)`кода приложения это вызывает беспараметрыный конструктор и конструкторы базового класса. Затем он `Property1 = object1`устанавливает, который `OnPropertyChanged` вызывает виртуальный `MyClass` <xref:System.Windows.DependencyObject>метод на владение .  Переопределение ссылается на `_myList`, который еще не был инициализирован.  
  
 Один из способов избежать этих проблем — убедиться в том, что обратные вызовы используют только другие свойства зависимостей, а каждое такое свойство зависимости имеет установленное по умолчанию значение в составе его зарегистрированных метаданных.  
  
<a name="Safe_Constructor_Patterns"></a>
## <a name="safe-constructor-patterns"></a>Шаблоны безопасных конструкторов  
 Во избежание риска неполной инициализации, если класс используется как базовый, используйте эти шаблоны.  
  
#### <a name="parameterless-constructors-calling-base-initialization"></a>Беспарализаторы, вызывающие инициализацию базы  
 Реализуйте эти конструкторы, вызывающие базовое значение по умолчанию.  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass() : base() {  
        // ALL class initialization, including initial defaults for
        // possible values that other ctors specify or that callbacks need.  
    }  
}  
```  
  
#### <a name="non-default-convenience-constructors-not-matching-any-base-signatures"></a>Нестандартные (удобные) конструкторы, не соответствующие базовым сигнатурам  
 Если эти конструкторы используют параметры для установки свойств зависимости в инициализации, сначала позвоните в свой собственный класс без параметров конструктора для инициализации, а затем использовать параметры для установки свойств зависимости. Это могут быть либо свойства зависимостей, определенные вашим классом, либо свойства зависимостей, унаследованные от базовых классов, но в любом случае используйте следующий шаблон:  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### <a name="non-default-convenience-constructors-which-do-match-base-signatures"></a>Нестандартные (удобные) конструкторы, которые соответствуют базовым сигнатурам  
 Вместо того, чтобы вызывать базовый конструктор с той же параметризацией, снова позвоните в непараметрочную конструкцию собственного класса. Не следует вызывать базовый инициализатор. Вместо этого нужно вызвать `this()`. Затем воспроизведите исходное поведение конструктора, используя переданные параметры в качестве значений для установки соответствующих свойств. Используйте оригинальную документацию по базовому конструктору в качестве руководства по определению свойств, которые задаются определенными параметрами.  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### <a name="must-match-all-signatures"></a>Должен соответствовать всем сигнатурам  
 В тех случаях, когда базовый тип имеет несколько подписей, необходимо намеренно сопоставить все возможные подписи с реализацией конструктора, который использует рекомендуемый шаблон вызова непараметроа конструктора класса, прежде чем установить далее Вариантов размещения.  
  
#### <a name="setting-dependency-properties-with-setvalue"></a>Установка свойств зависимостей с помощью SetValue  
 Эти же шаблоны применяются, если вы устанавливаете свойство, которое не имеет <xref:System.Windows.DependencyObject.SetValue%2A>обертку для удобства настройки свойства, и устанавливают значения с . Ваши вызовы, <xref:System.Windows.DependencyObject.SetValue%2A> которые проходят через параметры конструктора, также должны вызывать безпараметризатор класса для инициализации.  
  
## <a name="see-also"></a>См. также раздел

- [Пользовательские свойства зависимостей](custom-dependency-properties.md)
- [Общие сведения о свойствах зависимости](dependency-properties-overview.md)
- [Безопасность свойства зависимости](dependency-property-security.md)
