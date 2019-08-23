---
title: Сеансы, экземпляры и параллелизм
ms.date: 03/30/2017
ms.assetid: 50797a3b-7678-44ed-8138-49ac1602f35b
ms.openlocfilehash: d780488f7bb0bd46a22ef205b3954b6b4614cae0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969213"
---
# <a name="sessions-instancing-and-concurrency"></a>Сеансы, экземпляры и параллелизм
Под *сеансом* понимается скоррелированный набор всех сообщений, переданных между двумя конечными точками. *Создание экземпляров* означает управление временем жизни определенных пользователем объектов службы и связанных с ними объектов <xref:System.ServiceModel.InstanceContext> . Термин*параллелизм* означает управление количеством потоков, одновременно выполняющихся в некотором контексте <xref:System.ServiceModel.InstanceContext> .  
  
 В этом разделе описаны эти параметры, способы их использования и различные взаимодействия между ними.  
  
## <a name="sessions"></a>Сеансы  
 Если в контракте службы для свойства <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> задано значение <xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType>, такой контракт означает, что все вызовы (т. е. обмен сообщениями, на котором основана поддержка вызовов) должны быть частью одного диалога. Если в контракте указано, что сеансы для него разрешены, но не требуются, клиенты могут подключаться, создавая сеанс или не создавая его. Если сеанс завершен, но по этому же основанному на сеансе каналу отправляется сообщение, выдается исключение.  
  
 Сеансы WCF имеют следующие основные концептуальные функции:  
  
- Они явным образом инициируются и завершаются вызвавшим приложением.  
  
- Сообщения, доставленные в ходе сеанса, обрабатываются в порядке их получения.  
  
- Сеанс коррелирует группу сообщений в диалог. Такая корреляция является абстракцией. Например, один основанный на сеансах канал может коррелировать сообщения, основываясь на общем сетевом подключении, а другой - основываясь на общем теге в тексте сообщения. Функции, получаемые в результате сеанса, зависят от характера корреляции.  
  
- Нет общего хранилища данных, связанного с сеансом WCF.  
  
 Если вы знакомы с <xref:System.Web.SessionState.HttpSessionState?displayProperty=nameWithType> классом в приложениях ASP.NET и предоставляемыми им функциями, вы можете заметить следующие различия между этим видом сеанса и сеансами WCF:  
  
- Сеансы ASP.NET всегда инициируются сервером.  
  
- Сеансы ASP.NET неявно неупорядочены.  
  
- Сеансы ASP.NET предоставляют общий механизм хранения данных для запросов.  
  
 Клиентские приложения и приложения служб взаимодействуют с сеансами разными способами. Клиентское приложение инициирует сеансы, а затем получает и обрабатывает сообщения, передаваемые в рамках этого сеанса. Приложения служб могут использовать сеансы как точки расширяемости для добавления дополнительного поведения. Это можно сделать, работая непосредственно с контекстом <xref:System.ServiceModel.InstanceContext> , или реализовав пользовательский поставщик контекста экземпляров.  
  
## <a name="instancing"></a>Создание экземпляров  
 Поведение при создании экземпляров (задаваемое с помощью свойства <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> ) управляет способом создания контекста <xref:System.ServiceModel.InstanceContext> в ответ на входящие сообщения. По умолчанию каждый контекст <xref:System.ServiceModel.InstanceContext> связан с одним определенным пользователем объектом службы, поэтому (по умолчанию) задание свойства <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> также определяет создание экземпляров определенных пользователем объектов службы. Перечисление <xref:System.ServiceModel.InstanceContextMode> определяет режимы создания экземпляров.  
  
 Доступны следующие режимы создания экземпляров:  
  
- <xref:System.ServiceModel.InstanceContextMode.PerCall>: Для каждого <xref:System.ServiceModel.InstanceContext> клиентского запроса создается новый (и, следовательно, объект службы).  
  
- <xref:System.ServiceModel.InstanceContextMode.PerSession>: Новый <xref:System.ServiceModel.InstanceContext> (и, следовательно, объект службы) создается для каждого нового сеанса клиента и сохраняется в течение времени существования этого сеанса (для этого требуется привязка, поддерживающая сеансы).  
  
- <xref:System.ServiceModel.InstanceContextMode.Single>: Один <xref:System.ServiceModel.InstanceContext> (и, следовательно, объект службы) обрабатывает все клиентские запросы на время существования приложения.  
  
 В следующем примере кода показано явное задание для режима <xref:System.ServiceModel.InstanceContextMode> значения <xref:System.ServiceModel.InstanceContextMode.PerSession> в классе службы.  
  
```  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]   
public class CalculatorService : ICalculatorInstance   
{   
    ...  
}  
```  
  
 Свойство <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> управляет частотой освобождения контекста <xref:System.ServiceModel.InstanceContext> , а свойства <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=nameWithType> и <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A?displayProperty=nameWithType> управляют частотой освобождения объекта службы.  
  
### <a name="well-known-singleton-services"></a>Широко известные одноэлементные службы  
 Иногда бывает полезен один из вариантов объектов службы с одним экземпляром: можно самому создать объект службы, а затем создать основное приложение службы, используя этот объект. Для этого необходимо задать для свойства <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> значение <xref:System.ServiceModel.InstanceContextMode.Single> - в противном случае при открытии основного приложения службы возникает исключение.  
  
 Для создания такой службы используйте конструктор <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Object%2CSystem.Uri%5B%5D%29?displayProperty=nameWithType> . Он обеспечивает альтернативу реализации пользовательского <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer?displayProperty=nameWithType> , если требуется предоставить определенный экземпляр объекта для использования одноэлементной службой. Этот перегружаемый метод можно использовать, когда тип реализации службы не позволяет легко использовать конструктор (например, если он не реализует открытый конструктор по умолчанию без параметров).  
  
 Обратите внимание, что при указании объекта для этого конструктора некоторые функции, связанные с поведением создания экземпляров Windows Communication Foundation (WCF), работают по-разному. Например, вызов <xref:System.ServiceModel.InstanceContext.ReleaseServiceInstance%2A?displayProperty=nameWithType> не выполняет никаких действий, если предоставлен экземпляр одноэлементного объекта. Аналогичным образом пропускаются все другие механизмы освобождения экземпляров. Приложение <xref:System.ServiceModel.ServiceHost> всегда ведет себя таким образом, как если бы для свойства <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=nameWithType> было задано значение <xref:System.ServiceModel.ReleaseInstanceMode.None?displayProperty=nameWithType> для всех операций.  
  
### <a name="sharing-instancecontext-objects"></a>Совместное использование объектов InstanceContext  
 Также для каждого сеансового канала или вызова можно задать объект <xref:System.ServiceModel.InstanceContext> , с которым он будет ассоциирован, самостоятельно назначив ассоциацию.  
  
## <a name="concurrency"></a>параллелизм  
 Параллелизм означает управление количеством потоков, одновременно активных в некотором контексте <xref:System.ServiceModel.InstanceContext> . Управление осуществляется с помощью <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A?displayProperty=nameWithType> с перечислением <xref:System.ServiceModel.ConcurrencyMode> .  
  
 Доступны следующие три режима параллелизма:  
  
- <xref:System.ServiceModel.ConcurrencyMode.Single>: Каждый контекст экземпляра может иметь максимум один поток, обрабатывающий сообщения в контексте экземпляра за раз. Другие потоки, которым требуется использовать этот же контекст экземпляра, должны оставаться блокированными, пока исходный поток не выйдет из контекста экземпляра.  
  
- <xref:System.ServiceModel.ConcurrencyMode.Multiple>: Каждый экземпляр службы может одновременно обрабатывать сообщения несколькими потоками. Чтобы использовать этот режим параллелизма, реализация службы должна быть потокобезопасной.  
  
- <xref:System.ServiceModel.ConcurrencyMode.Reentrant>: Каждый экземпляр службы обрабатывает одно сообщение за раз, но принимает вызовы повторного выполнения операций. Служба принимает эти вызовы только при вызове через клиентский объект WCF.  
  
> [!NOTE]
> Проектирование и разработка кода, который может безопасно использовать несколько потоков, может оказаться непростым делом. Перед использованием значения <xref:System.ServiceModel.ConcurrencyMode.Multiple> или <xref:System.ServiceModel.ConcurrencyMode.Reentrant> убедитесь, что служба должным образом разработана для поддержки этих режимов. Дополнительные сведения см. в разделе <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A>.  
  
 Использование параллелизма связано с режимом создания экземпляров. В <xref:System.ServiceModel.InstanceContextMode.PerCall> создании экземпляров параллелизм не имеет значения, так как каждое сообщение обрабатывается новым <xref:System.ServiceModel.InstanceContext> и, следовательно, не является активным для одного <xref:System.ServiceModel.InstanceContext>потока в.  
  
 В приведенном ниже коде представлен пример задания для свойства <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> значения <xref:System.ServiceModel.ConcurrencyMode.Multiple>.  
  
```  
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple, InstanceContextMode = InstanceContextMode.Single)]   
public class CalculatorService : ICalculatorConcurrency   
{   
    ...  
}  
```  
  
## <a name="sessions-interact-with-instancecontext-settings"></a>Сеансы взаимодействуют с параметрами InstanceContext  
 Взаимодействие сеансов и контекстов <xref:System.ServiceModel.InstanceContext> зависит от значений перечисления <xref:System.ServiceModel.SessionMode> в контракте и свойства <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> в реализации службы; сочетание этих значений определяет сопоставление каналов и конкретных объектов службы.  
  
 В приведенной ниже таблице показано, к какому результату приводит поддержка или отсутствие поддержки сеансов входящим каналом при заданном сочетании значений свойств <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> и <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> в службе.  
  
|Значение InstanceContextMode|<xref:System.ServiceModel.SessionMode.Required>|<xref:System.ServiceModel.SessionMode.Allowed>|<xref:System.ServiceModel.SessionMode.NotAllowed>|  
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|  
|PerCall|— Поведение с каналом сеанса: Сеанс и <xref:System.ServiceModel.InstanceContext> для каждого вызова.<br />-Поведение с каналом без сеанса: Возникает исключение.|— Поведение с каналом сеанса: Сеанс и <xref:System.ServiceModel.InstanceContext> для каждого вызова.<br />-Поведение с каналом без сеанса: <xref:System.ServiceModel.InstanceContext> Для каждого вызова.|— Поведение с каналом сеанса: Возникает исключение.<br />-Поведение с каналом без сеанса: <xref:System.ServiceModel.InstanceContext> Для каждого вызова.|  
|PerSession|— Поведение с каналом сеанса: Сеанс и <xref:System.ServiceModel.InstanceContext> для каждого канала.<br />-Поведение с каналом без сеанса: Возникает исключение.|— Поведение с каналом сеанса: Сеанс и <xref:System.ServiceModel.InstanceContext> для каждого канала.<br />-Поведение с каналом без сеанса: <xref:System.ServiceModel.InstanceContext> Для каждого вызова.|— Поведение с каналом сеанса: Возникает исключение.<br />-Поведение с каналом без сеанса: <xref:System.ServiceModel.InstanceContext> Для каждого вызова.|  
|Single|— Поведение с каналом сеанса: Сеанс и один <xref:System.ServiceModel.InstanceContext> для всех вызовов.<br />-Поведение с каналом без сеанса: Возникает исключение.|— Поведение с каналом сеанса: Сеанс и <xref:System.ServiceModel.InstanceContext> для созданного или заданного пользователем единственного элемента.<br />-Поведение с каналом без сеанса: Объект <xref:System.ServiceModel.InstanceContext> для созданного или заданного пользователем Singleton.|— Поведение с каналом сеанса: Возникает исключение.<br />-Поведение с каналом без сеанса: Объект <xref:System.ServiceModel.InstanceContext> для каждого созданного одноэлементного экземпляра или для заданного пользователем одноэлементного множества.|  
  
## <a name="see-also"></a>См. также

- [Использование сеансов](../../../../docs/framework/wcf/using-sessions.md)
- [Практическое руководство. Создание службы, требующей сеансов](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
- [Практическое руководство. Управление созданием экземпляров службы](../../../../docs/framework/wcf/feature-details/how-to-control-service-instancing.md)
- [Параллелизм](../../../../docs/framework/wcf/samples/concurrency.md)
- [Создание экземпляров](../../../../docs/framework/wcf/samples/instancing.md)
- [Session](../../../../docs/framework/wcf/samples/session.md)
