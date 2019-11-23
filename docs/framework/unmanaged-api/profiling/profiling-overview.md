---
title: Общие сведения о профилировании
ms.date: 03/30/2017
helpviewer_keywords:
- managed code, profiling API support
- unmanaged code, combining with managed code in profiling
- notification threads [.NET Framework profiling]
- unmanaged code, profiling
- profiling API [.NET Framework], and COM
- profiling API [.NET Framework], unmanaged code profiling
- profilers, writing
- profiling API [.NET Framework], call stacks
- code profilers, writing
- profiling API [.NET Framework], security considerations
- profiling API [.NET Framework], managed code support
- common language runtime, profiling
- profiling API [.NET Framework], notification threads
- call stacks [.NET Framework profiling]
- profiling API [.NET Framework], stack depth
- common language runtime, writing a profiler
- profiling API [.NET Framework], information retrieval interfaces
- shadow stacks [.NET Framework profiling]
- COM, using in the profiling API
- stack snapshots [.NET Framework profiling]
- profiling API [.NET Framework], supported features
- profiling API [.NET Framework], overview
- security, profiling API considerations
- stack depth [.NET Framework profiling]
ms.assetid: 864c2344-71dc-46f9-96b2-ed59fb6427a8
ms.openlocfilehash: 08015e2e5918ca64f601ec912a906cfb6319ed6c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427104"
---
# <a name="profiling-overview"></a>Общие сведения о профилировании

Профилировщик — это инструмент, который наблюдает за выполнением другого приложения. Профилировщик среды CLR — это библиотека DLL, содержащая функции, которые получают сообщения из среды CLR и отправляют сообщения в среду CLR с помощью API профилирования. Библиотека DLL профилировщика загружается средой CLR во время выполнения.

Традиционные средства профилирования основное внимание уделяют измерению выполнения приложения. То есть они измеряют время, затраченное на каждую функцию, или использование памяти приложением за период времени. API профилирования предназначен для более широкого класса диагностических средств, таких как служебные программы с покрытием кода и расширенные средства отладки. Сфера их применения — вся диагностика в природе. API профилирования не только измеряет, но также наблюдает за выполнением приложения. По этой причине API профилирования никогда не должен использоваться самим приложением, и выполнение приложения не должно ни зависеть от профилировщика, ни подвергаться его влиянию.

Для профилирования приложения среды CLR требуется дополнительная поддержка по сравнению с профилированием стандартно скомпилированного машинного кода. Это объясняется тем, что в среде CLR вводятся такие понятия, как домены приложений, сборка мусора, обработка управляемых исключений, JIT-компиляция кода (преобразование кода MSIL в машинный код) и другие аналогичные возможности. Механизмы традиционного профилирования не могут обнаруживать эти возможности или предоставлять полезные сведения о них. API профилирования эффективно предоставляет эти отсутствующие сведения с минимальным влиянием на производительность среды CLR и профилируемого приложения.

JIT-компиляция во время выполнения обеспечивает прекрасные возможности для профилирования. API профилирования позволяет профилировщику вносить изменения потока кода MSIL в памяти для подпрограммы перед ее JIT-компиляцией. Таким образом, профилировщик может динамически добавлять код инструментирования в определенные подпрограммы, требующие более глубокого анализа. Хотя такой подход возможен в обычных сценариях, его гораздо проще реализовать для среды CLR с помощью API профилирования.

## <a name="the-profiling-api"></a>API профилирования

Typically, the profiling API is used to write a *code profiler*, which is a program that monitors the execution of a managed application.

API профилирования используется библиотекой DLL профилировщика, которая загружается в один процесс с профилируемым приложением. The profiler DLL implements a callback interface ([ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) in the .NET Framework version 1.0 and 1.1, [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md) in version 2.0 and later). Среда CLR вызывает методы этого интерфейса для уведомления профилировщика о событиях в процессе профилирования. The profiler can call back into the runtime by using the methods in the [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) and [ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md) interfaces to obtain information about the state of the profiled application.

> [!NOTE]
> В одном процессе с профилируемым приложением должна запускаться только часть решения профилировщика, отвечающая за сбор данных. Весь анализ пользовательского интерфейса и данных должен выполняться в отдельном процессе.

На следующем рисунке показано, как библиотека DLL профилировщика взаимодействует с профилируемым приложением и средой CLR.

![Screenshot that shows the profiling architecture.](./media/profiling-overview/profiling-architecture.png)

### <a name="the-notification-interfaces"></a>Интерфейсы уведомлений

[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) and [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md) can be considered notification interfaces. These interfaces consist of methods such as [ClassLoadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md), [ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md), and [JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md). Каждый раз, когда среда CLR загружает или выгружает класс, компилирует функцию и т. д., она вызывает соответствующий метод в интерфейсе `ICorProfilerCallback` или `ICorProfilerCallback2` профилировщика.

For example, a profiler could measure code performance through two notification functions: [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) and [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md). Он просто устанавливает метки времени для каждого уведомления, собирает результаты и выводит список, в котором указывается, на какие функции было затрачено больше ресурсов ЦП или физического времени во время выполнения приложения.

### <a name="the-information-retrieval-interfaces"></a>Интерфейсы для извлечения сведений

The other main interfaces involved in profiling are [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) and [ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md). Профилировщик вызывает эти интерфейсы по мере необходимости для получения дополнительных сведений, помогающих выполнить анализ. For example, whenever the CLR calls the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) function, it supplies a function identifier. The profiler can get more information about that function by calling the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method to discover the function's parent class, its name, and so on.

## <a name="supported-features"></a>Поддерживаемые компоненты

API профилирования предоставляет сведения о различных событиях и действиях, которые происходят в среде CLR. Эти сведения можно использовать для мониторинга внутренней работы процессов и анализа производительности приложения .NET Framework.

API профилирования извлекает сведения о следующих действиях и событиях, происходящих в среде CLR.

- События запуска и завершения работы среды CLR.

- События создания и завершения работы домена приложения.

- События загрузки и выгрузки сборки.

- События загрузки и выгрузки модуля.

- События создания и удаления таблицы VTable COM.

- События JIT-компиляции и пошагового выполнения кода.

- События загрузки и выгрузки класса.

- События создания и удаления потока.

- События входа и выхода функции.

- Исключения.

- Переходы между выполнением управляемого и неуправляемого кода.

- Переходы между различными контекстами среды выполнения.

- Сведения о приостановках среды выполнения.

- Сведения о действиях сборки мусора и кучи в памяти времени выполнения.

API профилирования можно вызывать из любого (неуправляемого) языка, совместимого с COM.

Этот API является эффективным с точки зрения потребления ресурсов ЦП и памяти. Профилирование не влечет за собой изменения профилируемого приложения, которые могут привести к недостоверным результатам.

API профилирования полезен для профилировщиков как с выборкой, так и без выборки. A *sampling profiler* inspects the profile at regular clock ticks, say, at 5 milliseconds apart. A *non-sampling profiler* is informed of an event synchronously with the thread that causes the event.

### <a name="unsupported-functionality"></a>Неподдерживаемые функциональные возможности

API профилирования не поддерживает следующие функциональные возможности.

- Неуправляемый код, который необходимо профилировать с помощью стандартных методов Win32. Однако профилировщик среды CLR включает события переходов для определения границ между управляемым и неуправляемым кодом.

- Самоизменяющиеся приложения, которые изменяют собственный код приложения, которые изменяют собственный код, например в целях аспектно-ориентированного программирования.

- Проверка привязок, поскольку API профилирования не предоставляет эти сведения. Среда CLR предоставляет существенную поддержку для проверки границ всего управляемого кода.

- Удаленное профилирование, которое не поддерживается по следующим причинам.

  - Удаленное профилирование увеличивает время выполнения. При использовании интерфейсов профилирования необходимо минимизировать время выполнения, чтобы оно не слишком сильно сказывалось на результатах профилирования. Это особенно важно при мониторинге производительности. Тем не менее удаленное профилирование не является ограничением при использовании интерфейсов профилирования для мониторинга использования памяти или для получения сведений времени выполнения о кадрах стека, объектах и т. п.

  - Профилировщик кода среды CLR должен зарегистрировать один или несколько интерфейсов обратного вызова в среде выполнения на локальном компьютере, на котором выполняется профилируемое приложение. Это ограничивает возможность создания удаленного профилировщика кода.

- Профилирование в производственных средах с требованиями высокой доступности. API профилирования создавался для поддержки диагностики во время разработки. Он не проходил строгие испытания, необходимые для поддержки производственных сред.

## <a name="notification-threads"></a>Потоки уведомлений

В большинстве случаев поток, который создает событие, также выполняет уведомления. Such notifications (for example, [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) and [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md)) do not need to supply the explicit `ThreadID`. Кроме того, профилировщик может использовать локальное хранилище потока для хранения и обновления своих блоков анализа вместо индексирования этих блоков в глобальном хранилище на основе `ThreadID` затронутого потока.

Обратите внимание, что эти обратные вызовы не сериализуются. Пользователи должны защищать свой код, путем создания потокобезопасных структур данных и путем блокировки кода профилировщика в тех случаях, когда необходимо предотвратить параллельный доступ из нескольких потоков. Таким образом, в некоторых случаях можно получить необычную последовательность обратных вызовов. Например, предположим, что управляемое приложение порождает два потока, выполняющие идентичный код. In this case, it is possible to receive a [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) event for some function from one thread and a `FunctionEnter` callback from the other thread before receiving the [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) callback. В этом случае пользователь получит обратный вызов `FunctionEnter` для функции, которая могла быть не полностью JIT-скомпилирована.

## <a name="security"></a>Безопасность

Библиотека DLL профилировщика — это неуправляемая библиотека DLL, которая выполняется в рамках подсистемы выполнения среды CLR. В результате на код в библиотеке DLL профилировщика DLL не налагаются ограничения управления доступом для управляемого кода. Для библиотеки DLL профилировщика действуют только ограничения, накладываемые операционной системой на пользователя, запускающего профилируемое приложение.

Разработчики профилировщика должны принять соответствующие меры предосторожности, чтобы избежать проблем, связанных с безопасностью. Например, во время установки библиотека DLL профилировщика должна добавляться в список управления доступом (ACL), чтобы злоумышленник не мог изменить ее.

## <a name="combining-managed-and-unmanaged-code-in-a-code-profiler"></a>Объединение управляемого и неуправляемого кода в коде профилировщика

Неправильно написанный профилировщик может вызвать циклические ссылки на себя, что приводит к непредсказуемому поведению.

Обзор API профилирования среды CLR может создать впечатление, что можно написать профилировщик, содержащий управляемые и неуправляемые компоненты, которые вызывают друг друга посредством COM-взаимодействия или непрямых вызовов.

Хотя это возможно с точки зрения проектирования, API профилирования не поддерживает управляемые компоненты. Профилировщик среды CLR должен быть полностью неуправляемым. Попытки объединить управляемый и неуправляемый код в профилировщике среды CLR могут привести к нарушениям прав доступа, сбоям программы или взаимоблокировкам. Управляемые компоненты профилировщика будут возвращать события обратно их неуправляемым компонентам, что будет затем вызывать управляемые компоненты снова, и таким образом будут создаваться циклические ссылки.

Единственное место, где профилировщик CLR может безопасно вызывать управляемый код, это текст MSIL в теле метода. The recommended practice for modifying the MSIL body is to use the  JIT recompilation methods in the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interface.

Кроме того, для изменения MSIL можно использовать старые методы инструментирования. Before the just-in-time (JIT) compilation of a function is completed, the profiler can insert managed calls in the MSIL body of a method and then JIT-compile it (see the [ICorProfilerInfo::GetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbody-method.md) method). Этот способ можно успешно использовать для выборочного инструментирования управляемого кода или для сбора статистики и данных производительности касательно JIT.

Кроме того, профилировщик кода может вставлять собственные обработчики в текст MSIL любой управляемой функции, которая вызывает неуправляемый код. Этот способ можно использовать для инструментирования и покрытия. Например, профилировщик кода может вставить обработчики инструментирования после каждого блока MSIL для обеспечения выполнения блока. Изменение текста MSIL метода следует выполнять очень аккуратно и принимать во внимание множество факторов.

## <a name="profiling-unmanaged-code"></a>Профилирование неуправляемого кода

API профилирования среды CLR предоставляет минимальную поддержку профилирования неуправляемого кода. Предоставляются следующие функциональные возможности.

- Перечисление цепочек стека. Эта возможность позволяет профилировщику кода определить границу между управляемым и неуправляемым кодом.

- Определение, соответствует ли цепочка стека управляемому коду или машинному коду.

В .NET Framework версий 1.0 и 1.1 эти методы доступны через внутрипроцессное подмножество API отладки среды CLR. Они определяются в файле CorDebug.idl.

In the .NET Framework 2.0 and later, you can use the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method for this functionality.

## <a name="using-com"></a>Использование модели COM

Хотя интерфейсы профилирования определяются как COM-интерфейсы, среда CLR в действительности не инициализирует модель COM для использования этих интерфейсов. The reason is to avoid having to set the threading model by using the [CoInitialize](/windows/desktop/api/objbase/nf-objbase-coinitialize) function before the managed application has had a chance to specify its desired threading model. Аналогично, сам профилировщик не должен вызывать `CoInitialize`, поскольку он может выбрать потоковую модель, несовместимую с профилируемым приложением, что может привести к сбою приложения.

## <a name="call-stacks"></a>Стеки вызовов

API профилирования предоставляет два способа получения стеков вызова: метод моментальных снимков стека, который позволяет реже выполнять сбор стеков вызовов, и метод теневого стека, который отслеживает стек вызовов в каждый момент времени.

### <a name="stack-snapshot"></a>Моментальный снимок стека

Моментальный снимок стека — это трассировка стека потока в момент времени. API профилирования поддерживает трассировку управляемых функций в стеке, но оставляет трассировку неуправляемых функций собственному обходчику стека профилировщика.

For more information about how to program the profiler to walk managed stacks, see the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method in this documentation set, and [Profiler Stack Walking in the .NET Framework 2.0: Basics and Beyond](https://go.microsoft.com/fwlink/?LinkId=73638).

### <a name="shadow-stack"></a>Теневой стек

Слишком частое использование метода моментального снимка может быстро создавать проблемы производительности. If you want to take stack traces frequently, your profiler should instead build a shadow stack by using the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md), and [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md) exception callbacks. Теневой стек всегда является текущим, и его можно быстро скопировать в хранилище каждый раз, когда требуется моментальный снимок стека.

Теневой стек может получать аргументы функций, возвращать значения и сведения об универсальных экземплярах. Эти сведения доступны только посредством теневого стека и могут быть получены, когда управление передается в функцию. Однако эти сведения могут оказаться недоступны позднее, во время выполнения функции.

## <a name="callbacks-and-stack-depth"></a>Обратные вызовы и глубина стека вызовов

Обратные вызовы профилировщика могут осуществляться в условиях очень ограниченного стека, и переполнение стека в обратном вызове профилировщика приведет к немедленному завершению выполнения процесса. В ответ на обратные вызовы профилировщик должен гарантированно использовать минимально возможный стек. Если профилировщик предназначен для использования в процессах, устойчивых к переполнению стека, сам профилировщик должен также избегать активации переполнения стека.

## <a name="related-topics"></a>См. также

|Заголовок|Описание|
|-----------|-----------------|
|[Настройка среды профилирования](../../../../docs/framework/unmanaged-api/profiling/setting-up-a-profiling-environment.md)|В этом разделе объясняется, как можно инициализировать профилировщик, установить уведомления о событиях и профилировать службу Windows.|
|[Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)|В этом разделе описываются неуправляемые интерфейсы, которые использует API профилирования.|
|[Глобальные статические функции профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)|В этом разделе описываются неуправляемые глобальные статистические функции, которые использует API профилирования.|
|[Перечисления профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)|В этом разделе описываются неуправляемые перечисления, которые использует API профилирования.|
|[Структуры профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)|В этом разделе описываются неуправляемые структуры, которые использует API профилирования.|
