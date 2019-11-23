---
title: Object-oriented programming
ms.date: 07/20/2015
ms.assetid: 49794de4-64c3-473c-b8ed-fe98835df69c
ms.openlocfilehash: 3739919273f4cdd285d519c414c542f1a82a16d2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348161"
---
# <a name="object-oriented-programming-visual-basic"></a>Object-oriented programming (Visual Basic)

Visual Basic provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.

 *Инкапсуляция* означает, что группа связанных свойств, методов и других членов рассматривается как единый элемент или объект.

 *Наследование* описывает возможность создания новых классов на основе существующих классов.

 *Полиморфизм* означает, что можно иметь несколько взаимозаменяемых классов, даже если каждый класс реализует одни и те же свойства или методы разными способами.

 В этом разделе рассматриваются следующие понятия.

- [Классы и объекты](#classes-and-objects)
  - [Члены класса](#class-members)
    - [Properties and fields](#properties-and-fields)
    - [Методы](#methods)
    - [Конструкторы](#constructors)
    - [Деструкторы](#destructors)
    - [События](#events)
    - [Nested classes](#nested-classes)
  - [Access modifiers and access levels](#access-modifiers-and-access-levels)
    - [Instantiating classes](#instantiating-classes)
    - [Shared classes and members](#shared-classes-and-members)
    - [Анонимные типы](#anonymous-types)
- [Наследование](#inheritance)
  - [Overriding members](#overriding-members)
- [Интерфейсы](#interfaces)
- [Универсальные шаблоны](#generics)
- [Делегаты](#delegates)

## <a name="classes-and-objects"></a>Классы и объекты

Термины *класс* и *объект* часто взаимозаменяемы, но в действительности классы описывают *типы* объектов, а объекты — это используемые *экземпляры* классов. Поэтому процесс создания объекта называется *созданием экземпляра*. Если использовать сравнение с чертежом, то класс является чертежом, а объект является зданием, построенным по нему.

Определение класса:

```vb
Class SampleClass
End Class
```

Visual Basic also provides a light version of classes called *structures* that are useful when you need to create large array of objects and do not want to consume too much memory for that.

Определение структуры:

```vb
Structure SampleStructure
End Structure
```

Дополнительные сведения см. на странице

- [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)
- [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)

### <a name="class-members"></a>Члены класса

Каждый класс может состоять из различных *членов класса*, которые содержат свойства, описывающие данные класса, методы, задающие поведение класса, и события, обеспечивающие связь между различными классами и объектами.

#### <a name="properties-and-fields"></a>Properties and fields

Поля и свойства представляют сведения, содержащиеся в объекте. Поля подобны переменным в том, что их можно прочитать или изменить напрямую.

Определение поля:

```vb
Class SampleClass
    Public SampleField As String
End Class
```

Для работы со свойствами используются процедуры "Get" и "Set", которые расширяют возможности управления способом задания и возврата значений.

Visual Basic allows you either to create a private field for storing the property value or use so-called auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.

Определение автоматически реализуемого свойства:

```vb
Class SampleClass
    Public Property SampleProperty as String
End Class
```

Если требуется выполнить дополнительные операции чтения и записи применительно к значению свойства, определите поле для хранения значения свойства и затем реализуйте базовую логику для хранения и извлечения этого значения:

```vb
Class SampleClass
    Private m_Sample As String
    Public Property Sample() As String
        Get
            ' Return the value stored in the field.
            Return m_Sample
        End Get
        Set(ByVal Value As String)
            ' Store the value in the field.
            m_Sample = Value
        End Set
    End Property
End Class
```

У большинства свойств есть методы или процедуры для задания и возврата значения свойства. Однако можно создать свойства, доступные только для чтения или только на запись, чтобы запретить изменение или чтение значений свойств. Для этого в Visual Basic можно использовать ключевые слова `ReadOnly` и `WriteOnly`. Следует отметить, что автоматически реализуемые свойства нельзя сделать доступными только для чтения или только для записи.

Дополнительные сведения см. на странице

- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Оператор Get](../../../visual-basic/language-reference/statements/get-statement.md)
- [Оператор Set](../../../visual-basic/language-reference/statements/set-statement.md)
- [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)
- [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)

#### <a name="methods"></a>Методы

 Действие, которое выполняет объект, называется *методом*.

> [!NOTE]
> В Visual Basic существует два способа создания метода: с помощью оператора `Sub` (если метод не возвращает значение) или с помощью оператора `Function` (если метод возвращает значение).

Определение метода класса:

```vb
Class SampleClass
    Public Function SampleFunc(ByVal SampleParam As String)
        ' Add code here
    End Function
End Class
```

Класс может иметь несколько реализаций или *перегрузок* одного и того же метода, которые отличаются от других числом или типами параметров.

Перегрузка метода:

```vb
Overloads Sub Display(ByVal theChar As Char)
    ' Add code that displays Char data.
End Sub
Overloads Sub Display(ByVal theInteger As Integer)
    ' Add code that displays Integer data.
End Sub
```

Как правило, метод объявляется при определении класса. However, Visual Basic also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.

Дополнительные сведения см. на странице

- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Перегрузки](../../../visual-basic/language-reference/modifiers/overloads.md)
- [Методы расширения](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)

#### <a name="constructors"></a>Конструкторы

Конструкторы — это методы классов, выполняемые автоматически при создании объекта заданного типа. Обычно конструкторы выполняют инициализацию членов данных нового объекта. Конструктор можно запустить только один раз при создании класса. Кроме того, код конструктора всегда выполняется раньше всех остальных частей кода в классе. Следует отметить, что так же, как и для других методов, можно создать несколько перегрузок конструктора.

Определение конструктора для класса:

```vb
Class SampleClass
    Sub New(ByVal s As String)
        // Add code here.
    End Sub
End Class
```

For more information, see: [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).

#### <a name="destructors"></a>Деструкторы

Деструкторы используются для уничтожения экземпляров классов. В платформе .NET Framework сборщик мусора автоматически управляет распределением и освобождением памяти для управляемых объектов приложения. Однако для очистки неуправляемых ресурсов, создаваемых приложением, могут потребоваться деструкторы. На один класс допускается только один деструктор.

Дополнительные сведения о деструкторах и сборке мусора в .NET Framework см. в разделе [Сборка мусора](../../../standard/garbage-collection/index.md).

#### <a name="events"></a>события

События позволяют классу или объекту уведомлять другие классы или объекты о возникновении каких-либо ситуаций. Класс, отправляющий (или порождающий) событие, называется *издателем*, а классы, принимающие (или обрабатывающие) событие, называются *подписчиками*. Дополнительные сведения о том, как порождаются и обрабатываются события, см. в разделе [События](../../../standard/events/index.md).

- To declare events, use the [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).

- To raise events, use the [RaiseEvent Statement](../../../visual-basic/language-reference/statements/raiseevent-statement.md).

- To specify event handlers using a declarative way, use the [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md) statement and the [Handles](../../../visual-basic/language-reference/statements/handles-clause.md) clause.

- To be able to dynamically add, remove, and change the event handler associated with an event, use the [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md) and [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) together with the [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md).

#### <a name="nested-classes"></a>Nested classes

Класс, определенный внутри другого класса, называется *вложенным*. По умолчанию вложенный класс является частным.

```vb
Class Container
    Class Nested
    ' Add code here.
    End Class
End Class
```

Чтобы создать экземпляр вложенного класса, укажите имя класса контейнера и имя вложенного класса, используя в качестве разделителя точку:

```vb
Dim nestedInstance As Container.Nested = New Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a>Access modifiers and access levels

С помощью *модификаторов доступа* все классы и члены классов могут указывать уровни доступа, предоставляемые другим классам.

Имеющиеся модификаторы доступа указаны в следующей таблице.

|Модификатор Visual Basic|Определение|
|---------------------------|----------------|
|[Public](../../../visual-basic/language-reference/modifiers/public.md)|Доступ к типу или члену возможен из любого другого кода в той же сборке или другой сборке, ссылающейся на него.|
|[Закрытые](../../../visual-basic/language-reference/modifiers/private.md)|Доступ к типу или члену можно получить только из кода в том же классе.|
|[Protected](../../../visual-basic/language-reference/modifiers/protected.md)|Доступ к типу или члену можно получить только из кода в том же классе или в производном классе.|
|[Friend](../../../visual-basic/language-reference/modifiers/friend.md)|Доступ к типу или члену возможен из любого кода в той же сборке, но не из другой сборки.|
|`Protected Friend`|Доступ к типу или члену возможен из любого кода в той же сборке, или из производного класса в другой сборке.|

For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

### <a name="instantiating-classes"></a>Instantiating classes

Чтобы создать объект, необходимо создать экземпляр класса.

```vb
Dim sampleObject as New SampleClass()
```

После создания экземпляра класса можно присваивать значения свойствам и полям экземпляра и вызывать методы класса.

```vb
' Set a property value.
sampleObject.SampleProperty = "Sample String"
' Call a method.
sampleObject.SampleMethod()
```

Чтобы назначить значения свойствам в процессе создания экземпляра класса, используйте инициализаторы объектов:

```vb
Dim sampleObject = New SampleClass With
    {.FirstProperty = "A", .SecondProperty = "B"}
```

Дополнительные сведения см. на странице

- [Оператор New](../../../visual-basic/language-reference/operators/new-operator.md)
- [Инициализаторы объектов. Именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)

### <a name="shared-classes-and-members"></a>Shared classes and members

 A shared member of the class is a property, procedure, or field that is shared by all instances of a class.

 To define a shared member:

```vb
Class SampleClass
    Public Shared SampleString As String = "Sample String"
End Class
```

 To access the shared member, use the name of the class without creating an object of this class:

```vb
MsgBox(SampleClass.SampleString)
```

 Shared modules in Visual Basic have shared members only and cannot be instantiated. Shared members also cannot access non-shared properties, fields or methods

 Дополнительные сведения см. на странице

- [Общие](../../../visual-basic/language-reference/modifiers/shared.md)
- [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)

### <a name="anonymous-types"></a>Анонимные типы

Анонимные типы позволяют создавать объекты без написания определения класса для типа данных. Вместо этого компилятор создает класс для вас. Данный класс не имеет имени и содержит свойства, которые указаны при объявлении объекта.

Создание экземпляра анонимного типа:

```vb
' sampleObject is an instance of a simple anonymous type.
Dim sampleObject =
    New With {Key .FirstProperty = "A", .SecondProperty = "B"}
```

Дополнительные сведения см. в разделе [Анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).

## <a name="inheritance"></a>Наследование

Наследование позволяет создавать новые классы, которые повторно используют, расширяют и изменяют поведение, определенное в другом классе. Класс, члены которого наследуются, называется *базовым классом*, а класс, который наследует эти члены, называется *производным классом*. However, all classes in Visual Basic implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.

> [!NOTE]
> Visual Basic doesn't support multiple inheritance. То есть можно указать только один базовый класс для производного класса.

Наследование от базового класса:

```vb
Class DerivedClass
    Inherits BaseClass
End Class
```

По умолчанию унаследовать класс можно от любого класса. Однако можно указать, должен ли класс использоваться в качестве базового класса, или создать класс, который может использоваться только в качестве базового.

Указание, что класс не может использоваться в качестве базового класса:

```vb
NotInheritable Class SampleClass
End Class
```

Указание, что класс может использоваться только в качестве базового класса и нельзя создать экземпляр этого класса:

```vb
MustInherit Class BaseClass
End Class
```

Дополнительные сведения см. на странице

- [Оператор Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)

### <a name="overriding-members"></a>Overriding members

По умолчанию производный класс наследует все члены от своего базового класса. Если необходимо изменить поведение унаследованного члена, необходимо переопределить его. Т. е. в производном классе можно определить новую реализацию метода, свойства или события.

Следующие модификаторы используются для управления переопределением свойств и методов.

|Модификатор Visual Basic|Определение|
|---------------------------|----------------|
|[Переопределяемые](../../../visual-basic/language-reference/modifiers/overridable.md)|Разрешает переопределение члена класса в производном классе.|
|[Переопределения](../../../visual-basic/language-reference/modifiers/overrides.md)|Переопределяет виртуальный (переопределяемый) член в базовом классе.|
|[NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)|Запрещает переопределение члена в наследующем классе.|
|[MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)|Требует, чтобы член класса был переопределен в производном классе.|
|[Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)|Скрывает член, наследуемый от базового класса|

## <a name="interfaces"></a>интерфейсов,

Интерфейсы, как и классы, определяют набор свойств, методов и событий. Но, в отличие от классов, интерфейсы не предоставляют реализацию. Они реализуются классами, но определяются как отдельные от классов сущности. Интерфейс представляет собой контракт, в котором класс, реализующий интерфейс, должен реализовывать каждый аспект этого интерфейса в точном соответствии с его определением.

Определение интерфейса:

```vb
Public Interface ISampleInterface
    Sub DoSomething()
End Interface
```

Реализация интерфейса в классе:

```vb
Class SampleClass
    Implements ISampleInterface
    Sub DoSomething
        ' Method implementation.
    End Sub
End Class
```

Дополнительные сведения см. на странице

- [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md)

## <a name="generics"></a>Универсальные шаблоны

Classes, structures, interfaces and methods in .NET can include *type parameters* that define types of objects that they can store or use. Наиболее распространенным примером универсального шаблона является коллекция, в которой можно указать тип объектов, которые могут в ней храниться.

Определение универсального класса:

```vb
Class SampleGeneric(Of T)
    Public Field As T
End Class
```

Создание экземпляра универсального класса:

```vb
Dim sampleObject As New SampleGeneric(Of String)
sampleObject.Field = "Sample string"
```

Дополнительные сведения см. на странице

- [Универсальные шаблоны](../../../standard/generics/index.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)

## <a name="delegates"></a>Делегаты

 *Делегат* — это тип, который определяет сигнатуру метода и может обеспечивать связь с любым методом с совместимой сигнатурой. Метод можно запустить (или вызвать) с помощью делегата. Делегаты используются для передачи методов в качестве аргументов к другим методам.

> [!NOTE]
> Обработчики событий — это ничто иное, как методы, вызываемые с помощью делегатов. Дополнительные сведения об использовании делегатов при обработке событий см. в разделе [События](../../../standard/events/index.md).

Создание делегата:

```vb
Delegate Sub SampleDelegate(ByVal str As String)
```

Создание ссылки на метод, сигнатура которого соответствует сигнатуре, указанной делегатом:

```vb
Class SampleClass
    ' Method that matches the SampleDelegate signature.
    Sub SampleSub(ByVal str As String)
        ' Add code here.
    End Sub
    ' Method that instantiates the delegate.
    Sub SampleDelegateSub()
        Dim sd As SampleDelegate = AddressOf SampleSub
        sd("Sample string")
    End Sub
End Class
```

Дополнительные сведения см. на странице

- [Делегаты](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Оператор AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)

## <a name="see-also"></a>См. также

- [Руководство по программированию на Visual Basic](../../../visual-basic/programming-guide/index.md)
