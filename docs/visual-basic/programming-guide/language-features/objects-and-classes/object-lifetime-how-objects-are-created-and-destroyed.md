---
title: 'Время существования: создание и уничтожение объектов'
ms.date: 07/20/2015
f1_keywords:
- vb.Constructor
helpviewer_keywords:
- destructors, object lifetime
- Sub Finalize destructor
- objects [Visual Basic], destroying
- lifetime [Visual Basic], objects
- Sub New constructor, object lifetime
- Finalize method [Visual Basic], object lifetime
- objects [Visual Basic], creating
- Class_Terminate
- Dispose method [Visual Basic], object lifetime
- Class_Initialize
- object creation [Visual Basic], object lifetime
- parameterized constructors
- objects [Visual Basic], lifetime
- objects [Visual Basic], garbage collection
- constructors [Visual Basic], object lifetime
- Sub Dispose destructor
- garbage collection [Visual Basic], Visual Basic
ms.assetid: f1ee8458-b156-44e0-9a8a-5dd171648cd8
ms.openlocfilehash: 8d9647fa490077f9f6ef82f30eccc4d5ee271985
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346107"
---
# <a name="object-lifetime-how-objects-are-created-and-destroyed-visual-basic"></a>Время существования: создание и уничтожение объектов (Visual Basic)

Экземпляр класса, объект, создается с помощью ключевого слова `New`. Задачи инициализации зачастую необходимо выполнять на новых объектах до их использования. К распространенным задачам инициализации относится открытие файлов, подключение к базам данных и чтение значений параметров реестра. Visual Basic controls the initialization of new objects using procedures called *constructors* (special methods that allow control over initialization).

Когда объект выходит из области, он высвобождается средой CLR. Visual Basic controls the release of system resources using procedures called *destructors*. Вместе конструкторы и деструкторы поддерживают создание надежных и предсказуемых библиотек класса.

## <a name="using-constructors-and-destructors"></a>Использование конструкторов и деструкторов

Конструкторы и деструкторы управляют созданием и уничтожением объектов. The `Sub New` and `Sub Finalize` procedures in Visual Basic initialize and destroy objects; they replace the `Class_Initialize` and `Class_Terminate` methods used in Visual Basic 6.0 and earlier versions.

### <a name="sub-new"></a>Конструктор Sub New

Конструктор `Sub New` может быть запущен только один раз при создании класса. Его нельзя вызвать явным образом нигде, кроме первой строки кода другого конструктора этого же класса или производного класса. Более того, код метода `Sub New` всегда выполняется до любого другого кода в классе. Visual Basic implicitly creates a `Sub New` constructor at run time if you do not explicitly define a `Sub New` procedure for a class.

Чтобы создать конструктор класса, создайте процедуру с именем `Sub New` в любом месте определения класса. Чтобы создать конструктор с параметрами, укажите имена и типы данных аргументов в `Sub New` точно так же, как для любой процедуры. См. следующий код:

[!code-vb[VbVbalrOOP#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/WhidbeyStuff.vb#42)]

Конструкторы часто перегружены, как в следующем коде:

[!code-vb[VbVbalrOOP#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/WhidbeyStuff.vb#116)]

При вызове класса, производного от другого класса, первая строка конструктора должна представлять собой вызов конструктора базового класса (кроме случаев, когда в базовом классе есть доступный конструктор, не принимающий параметры). Вызов базового класса, содержащего указанный выше конструктор, может быть, к примеру, таким `MyBase.New(s)`. Otherwise, `MyBase.New` is optional, and the Visual Basic runtime calls it implicitly.

После написания кода для вызова конструктора родительского объекта можно добавить дополнительный код инициализации к процедуре `Sub New`. `Sub New` может принимать аргументы при вызове в качестве конструктора с параметрами. Эти параметры передаются из процедуры, вызывающей конструктор, например, `Dim AnObject As New ThisClass(X)`.

### <a name="sub-finalize"></a>Sub Finalize

Перед высвобождением объектов среда CLR автоматически вызывает метод `Finalize` для объектов, определяющих процедуру `Sub Finalize`. Метод `Finalize` может содержать код, который необходимо выполнить непосредственно перед уничтожением объекта, например, код для закрытия файлов и сохранения информации о состоянии. Существует небольшой спад производительности при выполнении `Sub Finalize`, поэтому метод `Sub Finalize` нужно определять только в тех случаях, когда требуется явное высвобождение объектов.

> [!NOTE]
> The garbage collector in the CLR does not (and cannot) dispose of *unmanaged objects*, objects that the operating system executes directly, outside the CLR environment. Причина состоит в том, что разные неуправляемые объекты следует уничтожать по-разному. Эта информация не связана напрямую с неуправляемым объектом, ее необходимо найти в документации по объектам. Класс, использующий неуправляемые объекты, должен удалить их в своем методе `Finalize`.

Деструктор `Finalize` является защищенным методом, который можно вызвать только из класса, к которому он принадлежит, или из производного класса. Система автоматически вызывает `Finalize` при уничтожении объекта, поэтому не следует явным образом вызывать `Finalize` извне реализации `Finalize` производного класса.

В отличие от `Class_Terminate`, выполняющегося сразу же при уничтожении объекта, обычно существует пауза между потерей объектом области и вызовом деструктора `Finalize` в Visual Basic. Visual Basic .NET allows for a second kind of destructor, <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>, which can be explicitly called at any time to immediately release resources.

> [!NOTE]
> Деструктор `Finalize` не должен создавать исключений, поскольку они не обрабатываются приложением и могут привести к завершению работы приложения.

### <a name="how-new-and-finalize-methods-work-in-a-class-hierarchy"></a>Как методы New и Finalize работают в иерархии классов

При каждом создании экземпляра класса среда CLR пытается выполнить процедуру `New`, если она существует в этом объекте. `New` — тип процедуры, которая называется `constructor` и используется для инициализации новых объектов до выполнения всего остального кода в объекте. Конструктор `New` можно использовать для открытия файлов, подключения к базам данных, инициализации переменных и для других задач, которые необходимо выполнить перед использованием объекта.

Когда создается экземпляр производного класса, конструктор `Sub New` базового класса выполняется в первую очередь, а затем — конструкторы в производных классах. Это происходит, поскольку первая строка кода в конструкторе `Sub New` использует синтаксис `MyBase.New()` для вызова конструктора класса на один уровень выше себя в иерархии классов. Затем конструктор `Sub New` вызывается для каждого класса в иерархии вплоть до достижения базового класса. На этом этапе выполняется код в конструкторе базового класса, а затем выполняется код в каждом конструкторе всех производных классов; код в производном классе самого дальнего уровня выполняется последним.

![Screenshot showing class hierarchy constructors and inheritance.](./media/object-lifetime-how-objects-are-created-and-destroyed/subnew-constructor-inheritance.gif)

Когда объект больше не нужен, среда CLR вызывает метод <xref:System.Object.Finalize%2A> для этого объекта перед высвобождением памяти. Метод <xref:System.Object.Finalize%2A> называется `destructor`, поскольку он выполняет задачи очистки, такие как сохранение информации о состоянии, закрытие файлов и подключений к базам данных, а также прочие задачи, которые необходимо выполнить перед высвобождением объекта.

![Screenshot showing the Finalize method destructor.](./media/object-lifetime-how-objects-are-created-and-destroyed/finalize-method-destructor.gif)

## <a name="idisposable-interface"></a>Интерфейс IDisposable

Экземпляры классов зачастую управляют ресурсами, которыми не управляет среда CLR, такими как дескрипторы Windows и подключения к базам данных. От этих ресурсов нужно избавляться в методе `Finalize` класса, поэтому они будут высвобождаться при уничтожении объекта сборщиком мусора. Тем не менее, сборщик мусора уничтожает объекты только в тех случаях, когда среде CLR нужно больше свободной памяти. Это означает, что ресурсы могут быть не высвобождены еще в течение долгого времени после того, как объект выйдет из области.

Чтобы дополнить сборку мусора, ваши классы могут предоставлять механизм активного управления системными ресурсами путем реализации интерфейса <xref:System.IDisposable>. В <xref:System.IDisposable> существует метод <xref:System.IDisposable.Dispose%2A>, который клиенты должны вызывать по завершении использования какого-либо объекта. Можно использовать метод <xref:System.IDisposable.Dispose%2A> для немедленного высвобождения ресурсов и выполнения таких задач как закрытие файлов и подключений к базам данных. В отличие от деструктора `Finalize`, метод <xref:System.IDisposable.Dispose%2A> не вызывается автоматически. Клиенты класса должны явным образом вызвать <xref:System.IDisposable.Dispose%2A>, когда нужно немедленно высвободить ресурсы.

### <a name="implementing-idisposable"></a>Использование IDisposable

Класс, реализующий интерфейс <xref:System.IDisposable>, должен включать следующие разделы кода:

- Поле, чтобы отслеживать, уничтожен ли объект:

  ```vb
  Protected disposed As Boolean = False
  ```

- Перегрузка <xref:System.IDisposable.Dispose%2A> для высвобождения ресурсов класса. Этот метод должен вызываться методами <xref:System.IDisposable.Dispose%2A> и `Finalize` базового класса:

  ```vb
  Protected Overridable Sub Dispose(ByVal disposing As Boolean)
      If Not Me.disposed Then
          If disposing Then
              ' Insert code to free managed resources.
          End If
          ' Insert code to free unmanaged resources.
      End If
      Me.disposed = True
  End Sub
  ```

- Реализация <xref:System.IDisposable.Dispose%2A>, содержащая только следующий код:

  ```vb
  Public Sub Dispose() Implements IDisposable.Dispose
      Dispose(True)
      GC.SuppressFinalize(Me)
  End Sub
  ```

- Переопределение метода `Finalize`, содержащее только следующий код:

  ```vb
  Protected Overrides Sub Finalize()
      Dispose(False)
      MyBase.Finalize()
  End Sub
  ```

### <a name="deriving-from-a-class-that-implements-idisposable"></a>Производное создание от класса, реализующего IDisposable

Классу, производному от базового класса, реализующего интерфейс <xref:System.IDisposable>, нет необходимости переопределять какие-либо базовые методы, если только производный класс не использует дополнительные ресурсы, которые следует высвобождать. В этом случае производный класс должен переопределять метод `Dispose(disposing)` базового класса, чтобы удалить ресурсы производного класса. Это переопределение должно вызвать метод `Dispose(disposing)` базового класса.

```vb
Protected Overrides Sub Dispose(ByVal disposing As Boolean)
    If Not Me.disposed Then
        If disposing Then
            ' Insert code to free managed resources.
        End If
        ' Insert code to free unmanaged resources.
    End If
    MyBase.Dispose(disposing)
End Sub
```

Производный класс не должен переопределять методы <xref:System.IDisposable.Dispose%2A> и `Finalize` базового класса. Когда эти методы вызываются из экземпляра производного класса, реализация этих методов в базовом классе вызывает переопределение метода `Dispose(disposing)` производного класса.

## <a name="garbage-collection-and-the-finalize-destructor"></a>Сбор мусора и деструктор Finalize

The .NET Framework uses the *reference-tracing garbage collection* system to periodically release unused resources. Visual Basic 6.0 and earlier versions used a different system called *reference counting* to manage resources. Обе системы автоматически выполняют одну и ту же функцию, но есть несколько важных различий.

CLR периодически уничтожает объекты, если система определяет, что эти объекты больше не нужны. Объекты высвобождаются быстрее при нехватке системных ресурсов и медленнее в других случаях. Задержка между потерей объектом области и высвобождением объекта средой CLR означает, что в отличие от объектов в Visual Basic 6.0 и более ранних версиях, невозможно точно определить, когда объект будет уничтожен. In such a situation, objects are said to have *non-deterministic lifetime*. В большинстве случаев неопределенное время жизни не влияет на написание приложений, если помнить о том, что деструктор `Finalize` может быть выполнен не сразу после потери объектом области.

Еще одно отличие от систем сборки мусора заключается в использовании `Nothing`. Чтобы воспользоваться подсчетом ссылок в Visual Basic 6.0 и более ранних версиях, программисты часто назначали `Nothing` переменным объектов, чтобы высвобождать ссылки, удерживаемые этими переменными. Если переменная содержала последнюю ссылку на объект, ресурсы объекта были немедленно высвобождены. В более поздних версиях Visual Basic, хотя по-прежнему могут быть случаи, когда эта процедура еще применима, ее выполнение больше не приводит к немедленному высвобождению ресурсов объектом. Чтобы немедленно высвободить ресурсы, используйте метод объекта <xref:System.IDisposable.Dispose%2A>, если он доступен. Для переменной следует устанавливать значение `Nothing` лишь в тех случаях, когда ее время жизни достаточно велико по отношению ко времени, за которое сборщик мусора обнаруживает потерянные объекты.

## <a name="see-also"></a>См. также

- <xref:System.IDisposable.Dispose%2A>
- [Initialization and Termination of Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ws9dc6t6(v=vs.120))
- [Оператор New](../../../../visual-basic/language-reference/operators/new-operator.md)
- [Очистка неуправляемых ресурсов](../../../../standard/garbage-collection/unmanaged.md)
- [Nothing](../../../../visual-basic/language-reference/nothing.md)
