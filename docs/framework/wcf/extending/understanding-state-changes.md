---
title: Основные сведения об изменении состояния
ms.date: 03/30/2017
ms.assetid: a79ed2aa-e49a-47a8-845a-c9f436ec9987
ms.openlocfilehash: f6ce9875a4ebecf11f1f8d08d681841773d9f841
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447459"
---
# <a name="understanding-state-changes"></a>Основные сведения об изменении состояния
В данном разделе рассматриваются состояния и переходы каналов, а также типы, используемые для структуризации каналов, и способы их реализации.  
  
## <a name="state-machines-and-channels"></a>Конечные автоматы и каналы  
 Объекты, задействованные для связи, например сокеты, обычно представляют собой конечный автомат, переходы состояния которого связаны с выделением сетевых ресурсов, установлением и принятием соединений, а также закрытием соединений и завершением сеансов связи. Конечный автомат каналов обеспечивает единую модель состояний коммуникационного объекта, в которой приводится краткое описание базовой реализации данного объекта. Интерфейс <xref:System.ServiceModel.ICommunicationObject> обеспечивает набор состояний, а также методы и события перехода состояний. Все каналы, а также их фабрики и прослушиватели реализуют конечный автомат каналов.  
  
 События Closed, Closing, Faulted, Opened и Opening уведомляют внешнего наблюдателя после перехода состояния.  
  
 Методы Abort, Close и Open (а также их асинхронные эквиваленты) вызывают переходы состояния.  
  
 Свойство состояния возвращает текущее состояние, определенное классом <xref:System.ServiceModel.CommunicationState>.  
  
## <a name="icommunicationobject-communicationobject-and-states-and-state-transition"></a>ICommunicationObject, CommunicationObject, а также состояния и переход состояния  
 Объект <xref:System.ServiceModel.ICommunicationObject> запускается в состоянии Created, где можно настроить его различные свойства. В состоянии Opened объект используется для отправки и получения сообщений, но его свойства считаются неизменяемыми. В состоянии Closing объект больше не может обрабатывать новые запросы отправки и получения, но существующие запросы могут быть завершены, пока не истечет время ожидания закрытия.  В случае неустранимой ошибки объект переходит в состояние Faulted, где можно проверить сведения об ошибке и в конечном счете закрыть объект. В состоянии Closed объект по сути завершает конечный автомат. После того как объект переходит из одного состояния в другое, он не возвращается в предыдущее состояние.  
  
 На следующей схеме показаны состояния и переходы состояния объекта <xref:System.ServiceModel.ICommunicationObject>. Переходы состояния можно вызвать одним из трех методов: Abort, Open или Close. Их также можно вызвать другими методами, которые зависят от реализации. Переход в состояние Faulted может произойти в результате ошибки во время или после открытия коммуникационного объекта.  
  
 Каждый объект <xref:System.ServiceModel.ICommunicationObject> запускается в состоянии Created. В этом состоянии приложение может настраивать объект с помощью изменения его свойств. После того как объект находится в состоянии, отличном от Created, он считается неизменяемым.  
  
 ![Dataflow diagram of the channel state transition.](./media/understanding-state-changes/channel-state-transitions.gif)  
Figure 1. Конечный автомат ICommunicationObject.  
  
 Windows Communication Foundation (WCF) provides an abstract base class named <xref:System.ServiceModel.Channels.CommunicationObject> that implements <xref:System.ServiceModel.ICommunicationObject> and the channel state machine. Ниже приведена схема изменившегося состояния, относящаяся к <xref:System.ServiceModel.Channels.CommunicationObject>. Кроме конечного автомата <xref:System.ServiceModel.ICommunicationObject>, на схеме также показано время, когда вызываются дополнительные методы <xref:System.ServiceModel.Channels.CommunicationObject>.  
  
 ![Dataflow diagram of CommunicationObject implementation state changes.](./media/understanding-state-changes/communicationobject-implementation-state-machine.gif)
Рис. 2. Реализация CommunicationObject конечного автомата ICommunicationObject, включая вызовы событий и защищенных методов.  
  
### <a name="icommunicationobject-events"></a>События ICommunicationObject  
 Класс <xref:System.ServiceModel.Channels.CommunicationObject> предоставляет пять событий, определяемых <xref:System.ServiceModel.ICommunicationObject>. Эти события предназначены, чтобы уведомить код, использующий коммуникационный объект, о переходах состояния. Как показано выше на рисунке 2, каждое событие выполняется после того как состояние объекта переходит в состояние с именем этого события. Все пять событий относятся к типу `EventHandler`, который определяется следующим образом.  
  
 `public delegate void EventHandler(object sender, EventArgs e);`  
  
 В реализации <xref:System.ServiceModel.Channels.CommunicationObject> отправитель либо сам является объектом <xref:System.ServiceModel.Channels.CommunicationObject> либо тем, что было передано в качестве отправителя конструктору <xref:System.ServiceModel.Channels.CommunicationObject> (если используется эта перегрузка конструктора). Значение параметра EventArgs (`e`) всегда равно `EventArgs.Empty`.  
  
### <a name="derived-object-callbacks"></a>Обратные вызовы производного объекта  
 В дополнение к пяти событиям класс <xref:System.ServiceModel.Channels.CommunicationObject> объявляет восемь защищенных виртуальных методов, позволяющих выполнить обратный вызов объекта до или после переходов состояния.  
  
 Для методов <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A?displayProperty=nameWithType> и <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> имеется три обратных вызова, связанных с каждым из них. Например, методу <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A?displayProperty=nameWithType> соответствуют методы <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A?displayProperty=nameWithType>, <xref:System.ServiceModel.Channels.CommunicationObject.OnOpen%2A?displayProperty=nameWithType> и <xref:System.ServiceModel.Channels.CommunicationObject.OnOpened%2A?displayProperty=nameWithType>. С методом <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> связаны методы <xref:System.ServiceModel.Channels.CommunicationObject.OnClose%2A?displayProperty=nameWithType>, <xref:System.ServiceModel.Channels.CommunicationObject.OnClosing%2A?displayProperty=nameWithType> и <xref:System.ServiceModel.Channels.CommunicationObject.OnClosed%2A?displayProperty=nameWithType>.  
  
 Аналогичным образом, методу <xref:System.ServiceModel.Channels.CommunicationObject.Abort%2A?displayProperty=nameWithType> соответствует метод <xref:System.ServiceModel.Channels.CommunicationObject.OnAbort%2A?displayProperty=nameWithType>.  
  
 Реализация по умолчанию отсутствует в методах <xref:System.ServiceModel.Channels.CommunicationObject.OnOpen%2A?displayProperty=nameWithType>, <xref:System.ServiceModel.Channels.CommunicationObject.OnClose%2A?displayProperty=nameWithType> и <xref:System.ServiceModel.Channels.CommunicationObject.OnAbort%2A?displayProperty=nameWithType>, но она используется в других обратных вызовах, где реализация по умолчанию необходима для правильности конечного автомата. Если эти методы переопределены, необходимо вызвать базовую реализацию или правильно заменить ее.  
  
 <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A?displayProperty=nameWithType>, <xref:System.ServiceModel.Channels.CommunicationObject.OnClosing%2A?displayProperty=nameWithType> и <xref:System.ServiceModel.Channels.CommunicationObject.OnFaulted%2A?displayProperty=nameWithType> вызывают соответствующие события <xref:System.ServiceModel.Channels.CommunicationObject.Opening?displayProperty=nameWithType>, <xref:System.ServiceModel.Channels.CommunicationObject.Closing?displayProperty=nameWithType> и <xref:System.ServiceModel.Channels.CommunicationObject.Faulted?displayProperty=nameWithType>. <xref:System.ServiceModel.Channels.CommunicationObject.OnOpened%2A?displayProperty=nameWithType> и <xref:System.ServiceModel.Channels.CommunicationObject.OnClosed%2A?displayProperty=nameWithType> устанавливают объект в состояние Opened и Closed соответственно, а затем вызывают соответствующие события <xref:System.ServiceModel.Channels.CommunicationObject.Opened?displayProperty=nameWithType><xref:System.ServiceModel.Channels.CommunicationObject.Closed?displayProperty=nameWithType>.  
  
### <a name="state-transition-methods"></a>Методы перехода состояния  
 Класс <xref:System.ServiceModel.Channels.CommunicationObject> обеспечивает реализацию методов Abort, Close и Open. Он также предоставляет метод Fault, вызывающий переход в состояние Faulted. На рисунке 2 показан конечный автомат <xref:System.ServiceModel.ICommunicationObject>, где каждый переход помечен методом, который его вызвал (непомеченные переходы выполняются внутри реализации метода, вызвавшего последний помеченный переход).  
  
> [!NOTE]
> Все реализации <xref:System.ServiceModel.Channels.CommunicationObject> для получения или задания состояния связи синхронизированы с потоком.  
  
 Конструктор  
  
 Класс <xref:System.ServiceModel.Channels.CommunicationObject> предоставляет три конструктора, которые оставляют объект в состоянии Created. Конструкторы определяются следующим образом.  
  
 The first constructor is a parameterless constructor that delegates to the constructor overload that takes an object:  
  
 `protected CommunicationObject() : this(new object()) { … }`  
  
 Конструктор, принимающий объект, использует этот параметр в качестве объекта, который будет заблокирован при синхронизации доступа к состоянию коммуникационного объекта:  
  
 `protected CommunicationObject(object mutex) { … }`  
  
 Наконец, третий конструктор принимает дополнительный параметр, используемый в качестве аргумента отправителя при запуске событий <xref:System.ServiceModel.ICommunicationObject>.  
  
 `protected CommunicationObject(object mutex, object eventSender) { … }`  
  
 Предыдущие два конструктора задают для отправителя следующие параметры.  
  
 Метод Open  
  
 Предусловие: состояние Created.  
  
 Постусловие: состояние Opened или Faulted. Может создаваться исключение.  
  
 Метод Open() попытается открыть коммуникационный объект и установить состояние Opened. При возникновении ошибки метод установит состояние Faulted.  
  
 Метод сначала проверяет, что текущим состоянием является Created. Если текущим состоянием является Opening или Opened, метод создает исключение <xref:System.InvalidOperationException>. Если текущим состоянием является Closing или Closed, метод создает исключение <xref:System.ServiceModel.CommunicationObjectAbortedException>, если объект был завершен, в противном случае - <xref:System.ObjectDisposedException>. Если текущим состоянием является Faulted, метод создает исключение <xref:System.ServiceModel.CommunicationObjectFaultedException>.  
  
 Затем устанавливается состояние Opening и вызывается метод OnOpening() (создающий событие Opening), OnOpen() и OnOpened() в указанном порядке. Метод OnOpened() устанавливает состояние Opened и вызывает событие Opened. Если любое из этих событий создает исключение, метод Open() вызывает Fault() и выдает исключение. Следующая схема содержит подробные сведения о процессе Open.  
  
 ![Dataflow diagram of ICommunicationObject.Open state changes.](./media/understanding-state-changes/ico-open-process-override-onopen.gif)  
Переопределите метод OnOpen, чтобы реализовать пользовательскую логику открытия, например, открыть внутренний коммуникационный объект.  
  
 Метод Close  
  
 Предусловие: нет.  
  
 Постусловие: состояние Closed. Может создаваться исключение.  
  
 Метод Close() можно вызвать в любом состоянии. Метод пытается закрыть объект в обычном режиме. Если происходит ошибка, метод завершает выполнение объекта. Метод не выполняет никаких действий, если текущим состоянием является Closing или Closed. В противном случае он устанавливает состояние Closing. Если исходным состоянием является Created, Opening или Faulted, метод вызывает Abort() (см. следующую схему). Если исходным состоянием является Opened, вызывается метод OnClosing() (создающий событие Closing), OnClose() и OnClosed() в указанном порядке. Если любое из этих событий создает исключение, метод Close() вызывает Abort() и выдает исключение. Метод OnClosed() устанавливает состояние Closed и вызывает событие Closed. Следующая схема содержит подробные сведения о процессе Close.  
  
 ![Dataflow diagram of ICommunicationObject.Close state changes.](./media/understanding-state-changes/ico-close-process-override-onclose.gif)  
Переопределите метод OnClose, чтобы реализовать пользовательскую логику закрытия, например, закрыть внутренний коммуникационный объект. Для мягкой логики закрытия, которая может выполнять блокировку на длительное время (например, для ожидания ответа другой стороны), следует реализовать метод OnClose(), поскольку он использует параметр времени ожидания и не вызывается как часть Abort().  
  
 Прервать  
  
 Предусловие: нет.  
Постусловие: состояние Closed. Может создаваться исключение.  
  
 Метод Abort() не выполняет никаких действий, если текущим состоянием является Closed или объект был завершен ранее (например, с помощью выполнения метода Abort() в другом потоке). В противном случае устанавливается состояние Closing и вызывается метод OnClosing() (создающий событие Closing), OnAbort() и OnClosed() в указанном порядке (метод OnClose не вызывается, поскольку объект завершается, а не закрывается). Метод OnClosed() устанавливает состояние Closed и вызывает событие Closed. Если какое-либо из этих событий создает исключение, оно повторно выдается объекту, вызвавшему метод Abort. Реализации методов OnClosing(), OnClosed() и OnAbort() не должны выполнять блокировку (например, ввода-вывода). Следующая схема содержит подробные сведения о процессе Abort.  
  
 ![Dataflow diagram of ICommunicationObject.Abort state changes.](./media/understanding-state-changes/ico-abort-process-override-onabort.gif)  
Переопределите метод OnAbort, чтобы реализовать пользовательскую логику завершения, например, завершить внутренний коммуникационный объект.  
  
 Fault  
  
 Метод Fault относится конкретно к классу <xref:System.ServiceModel.Channels.CommunicationObject> и не является частью интерфейса <xref:System.ServiceModel.ICommunicationObject>. Указан для полноты представления информации.  
  
 Предусловие: нет.  
  
 Постусловие: состояние Faulted. Может создаваться исключение.  
  
 Метод Fault() не выполняет никаких действий, если текущим состоянием является Faulted или Closed. В противном случае устанавливается состояние Faulted и вызывается метод OnFaulted(), который создает событие Faulted. Если метод OnFaulted вызывает исключение, оно вызывается повторно.  
  
### <a name="throwifxxx-methods"></a>Методы ThrowIfXxx  
 В классе CommunicationObject имеется три защищенных метода, которые можно использовать для вызова исключений, если объект находится в определенном состоянии.  
  
 <xref:System.ServiceModel.Channels.CommunicationObject.ThrowIfDisposed%2A> вызывает исключение в состоянии Closing, Closed или Faulted.  
  
 <xref:System.ServiceModel.Channels.CommunicationObject.ThrowIfDisposedOrImmutable%2A> вызывает исключение, если состояние отлично от Created.  
  
 <xref:System.ServiceModel.Channels.CommunicationObject.ThrowIfDisposedOrNotOpen%2A> вызывает исключение, если состояние отлично от Opened.  
  
 Вызываемые исключения зависят от состояния. В следующей таблице показаны различные состояния и соответствующие типы исключений, которые метод ThrowIfXxx вызывает для них.  
  
|Область|Вызван метод Abort?|Исключение|  
|-----------|----------------------------|---------------|  
|Создано|Н/Д|<xref:System.InvalidOperationException?displayProperty=nameWithType>|  
|Открытие|Н/Д|<xref:System.InvalidOperationException?displayProperty=nameWithType>|  
|Открыто|Н/Д|<xref:System.InvalidOperationException?displayProperty=nameWithType>|  
|закрытие|Да|<xref:System.ServiceModel.CommunicationObjectAbortedException?displayProperty=nameWithType>|  
|закрытие|Нет|<xref:System.ObjectDisposedException?displayProperty=nameWithType>|  
|Закрыто|Да|Исключение <xref:System.ServiceModel.CommunicationObjectAbortedException?displayProperty=nameWithType>, если объект был закрыт предыдущим и явным вызовом метода Abort. При вызове метода Close для объекта выдается исключение <xref:System.ObjectDisposedException?displayProperty=nameWithType>.|  
|Закрыто|Нет|<xref:System.ObjectDisposedException?displayProperty=nameWithType>|  
|Faulted|Н/Д|<xref:System.ServiceModel.CommunicationObjectFaultedException?displayProperty=nameWithType>|  
  
### <a name="timeouts"></a>Время ожидания  
 Некоторые из рассмотренных методов используют параметры времени ожидания. Это методы Close, Open (некоторые перегрузки и асинхронные версии), OnClose и OnOpen. Эти методы позволяют использовать длительные операции (например, блокирование при вводе-выводе во время мягкого закрытия соединения), поэтому параметр времени ожидания указывает, как долго могут продолжаться такие операции до прерывания. В реализациях любых методов необходимо использовать предоставленное значение времени ожидания, чтобы оно возвращалось к вызывающей стороне в течение этого времени ожидания. Реализации других методов, которые не используют время ожидания, не предназначены для длительных операций и не должны блокироваться при вводе-выводе.  
  
 Исключениями являются перегрузки Open() и Close(), которые не используют параметр времени ожидания. Они используют значение времени ожидания по умолчанию, предоставленное производным классом. <xref:System.ServiceModel.Channels.CommunicationObject> обеспечивает доступ к двум абстрактным свойствам с именами <xref:System.ServiceModel.Channels.CommunicationObject.DefaultCloseTimeout%2A> и <xref:System.ServiceModel.Channels.CommunicationObject.DefaultOpenTimeout%2A>, которые определены как:  
  
 `protected abstract TimeSpan DefaultCloseTimeout { get; }`  
  
 `protected abstract TimeSpan DefaultOpenTimeout { get; }`  
  
 Производный класс реализует эти свойства, чтобы предоставить время ожидания по умолчанию для перегрузок Open() и Close(), не использующих значение по умолчанию. Затем в реализациях Open() и Close() выполняется делегирование в перегрузку, которая передает время ожидания в значение времени ожидания по умолчанию, например:  
  
 `public void Open()`  
  
 `{`  
  
 `this.Open(this.DefaultOpenTimeout);`  
  
 `}`  
  
#### <a name="idefaultcommunicationtimeouts"></a>IDefaultCommunicationTimeouts  
 В этом интерфейсе имеется четыре свойства только для чтения, которые предоставляют значения времени по умолчанию для открытия, отправки, получения и закрытия. Каждая реализация отвечает за получение значений по умолчанию соответствующим образом. Для удобства в классах <xref:System.ServiceModel.Channels.ChannelFactoryBase> и <xref:System.ServiceModel.Channels.ChannelListenerBase> по умолчанию используется значение 1 минута.
