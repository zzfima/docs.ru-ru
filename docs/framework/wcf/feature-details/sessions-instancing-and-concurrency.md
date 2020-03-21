---
title: Сеансы, экземпляры и параллелизм
ms.date: 03/30/2017
ms.assetid: 50797a3b-7678-44ed-8138-49ac1602f35b
ms.openlocfilehash: a7466d819e15f3bfe8def2d9407dcf2c6e0c7346
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184448"
---
# <a name="sessions-instancing-and-concurrency"></a>Сеансы, экземпляры и параллелизм
Под *сеансом* понимается скоррелированный набор всех сообщений, переданных между двумя конечными точками. *Создание экземпляров* означает управление временем жизни определенных пользователем объектов службы и связанных с ними объектов <xref:System.ServiceModel.InstanceContext> . Термин*параллелизм* означает управление количеством потоков, одновременно выполняющихся в некотором контексте <xref:System.ServiceModel.InstanceContext> .  
  
 В этом разделе описаны эти параметры, способы их использования и различные взаимодействия между ними.  
  
## <a name="sessions"></a>Сеансы  
 Если в контракте службы для свойства <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> задано значение <xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType>, такой контракт означает, что все вызовы (т. е. обмен сообщениями, на котором основана поддержка вызовов) должны быть частью одного диалога. Если в контракте указано, что сеансы для него разрешены, но не требуются, клиенты могут подключаться, создавая сеанс или не создавая его. Если сеанс завершен, но по этому же основанному на сеансе каналу отправляется сообщение, выдается исключение.  
  
 Сессии WCF имеют следующие основные концептуальные особенности:  
  
- Они явным образом инициируются и завершаются вызвавшим приложением.  
  
- Сообщения, доставленные в ходе сеанса, обрабатываются в порядке их получения.  
  
- Сеанс коррелирует группу сообщений в диалог. Такая корреляция является абстракцией. Например, один основанный на сеансах канал может коррелировать сообщения, основываясь на общем сетевом подключении, а другой - основываясь на общем теге в тексте сообщения. Функции, получаемые в результате сеанса, зависят от характера корреляции.  
  
- Общего хранилища данных, связанного с сеансом WCF, не существует.  
  
 Если вы знакомы <xref:System.Web.SessionState.HttpSessionState?displayProperty=nameWithType> с классом в ASP.NET приложений и функциональностью, которую он предоставляет, вы можете заметить следующие различия между такого рода сессиями и сессиями WCF:  
  
- ASP.NET сеансы всегда инициированы сервером.  
  
- ASP.NET сеансы неявно неупорядочены.  
  
- ASP.NET сеансы обеспечивают общий механизм хранения данных в разных запросах.  
  
 Клиентские приложения и приложения служб взаимодействуют с сеансами разными способами. Клиентское приложение инициирует сеансы, а затем получает и обрабатывает сообщения, передаваемые в рамках этого сеанса. Приложения служб могут использовать сеансы как точки расширяемости для добавления дополнительного поведения. Это можно сделать, работая непосредственно с контекстом <xref:System.ServiceModel.InstanceContext> , или реализовав пользовательский поставщик контекста экземпляров.  
  
## <a name="instancing"></a>Создание экземпляров  
 Поведение при создании экземпляров (задаваемое с помощью свойства <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> ) управляет способом создания контекста <xref:System.ServiceModel.InstanceContext> в ответ на входящие сообщения. По умолчанию каждый контекст <xref:System.ServiceModel.InstanceContext> связан с одним определенным пользователем объектом службы, поэтому (по умолчанию) задание свойства <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> также определяет создание экземпляров определенных пользователем объектов службы. Перечисление <xref:System.ServiceModel.InstanceContextMode> определяет режимы создания экземпляров.  
  
 Доступны следующие режимы создания экземпляров:  
  
- <xref:System.ServiceModel.InstanceContextMode.PerCall>: для каждого запроса клиента создается новый контекст <xref:System.ServiceModel.InstanceContext> (и, следовательно, новый объект службы).  
  
- <xref:System.ServiceModel.InstanceContextMode.PerSession>: новый контекст <xref:System.ServiceModel.InstanceContext> (и, следовательно, новый объект службы) создается для каждого нового сеанса клиента и существует в течение времени существования этого сеанса (для этого требуется привязка, поддерживающая сеансы).  
  
- <xref:System.ServiceModel.InstanceContextMode.Single>: все запросы клиентов за время существования приложения обрабатываются одним контекстом <xref:System.ServiceModel.InstanceContext> (и, следовательно, одним объектом службы).  
  
 В следующем примере кода показано явное задание для режима <xref:System.ServiceModel.InstanceContextMode> значения <xref:System.ServiceModel.InstanceContextMode.PerSession> в классе службы.  
  
```csharp  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]
public class CalculatorService : ICalculatorInstance
{
    ...  
}  
```  
  
 Свойство <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> управляет частотой освобождения контекста <xref:System.ServiceModel.InstanceContext> , а свойства <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=nameWithType> и <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A?displayProperty=nameWithType> управляют частотой освобождения объекта службы.  
  
### <a name="well-known-singleton-services"></a>Широко известные одноэлементные службы  
 Иногда бывает полезен один из вариантов объектов службы с одним экземпляром: можно самому создать объект службы, а затем создать основное приложение службы, используя этот объект. Для этого необходимо задать для свойства <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> значение <xref:System.ServiceModel.InstanceContextMode.Single> - в противном случае при открытии основного приложения службы возникает исключение.  
  
 Для создания такой службы используйте конструктор <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Object%2CSystem.Uri%5B%5D%29?displayProperty=nameWithType> . Он обеспечивает альтернативу реализации пользовательского <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer?displayProperty=nameWithType> , если требуется предоставить определенный экземпляр объекта для использования одноэлементной службой. Эту перегрузку можно использовать, когда трудно построить тип реализации службы (например, если он не выполняет безпаралиса).  
  
 Обратите внимание, что, когда объект предоставляется этому конструктору, некоторые функции, связанные с Фондом связи Windows (WCF), инстанимающие поведение работают по-разному. Например, вызов <xref:System.ServiceModel.InstanceContext.ReleaseServiceInstance%2A?displayProperty=nameWithType> не выполняет никаких действий, если предоставлен экземпляр одноэлементного объекта. Аналогичным образом пропускаются все другие механизмы освобождения экземпляров. Приложение <xref:System.ServiceModel.ServiceHost> всегда ведет себя таким образом, как если бы для свойства <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=nameWithType> было задано значение <xref:System.ServiceModel.ReleaseInstanceMode.None?displayProperty=nameWithType> для всех операций.  
  
### <a name="sharing-instancecontext-objects"></a>Совместное использование объектов InstanceContext  
 Также для каждого сеансового канала или вызова можно задать объект <xref:System.ServiceModel.InstanceContext> , с которым он будет ассоциирован, самостоятельно назначив ассоциацию.  
  
## <a name="concurrency"></a>Параллелизм  
 Параллелизм означает управление количеством потоков, одновременно активных в некотором контексте <xref:System.ServiceModel.InstanceContext> . Управление осуществляется с помощью <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A?displayProperty=nameWithType> с перечислением <xref:System.ServiceModel.ConcurrencyMode> .  
  
 Доступны следующие три режима параллелизма:  
  
- <xref:System.ServiceModel.ConcurrencyMode.Single>: в каждом контексте экземпляра одновременно допускается максимум один поток, обрабатывающий сообщения в контексте экземпляра. Другие потоки, которым требуется использовать этот же контекст экземпляра, должны оставаться блокированными, пока исходный поток не выйдет из контекста экземпляра.  
  
- <xref:System.ServiceModel.ConcurrencyMode.Multiple>: каждый экземпляр службы может иметь несколько потоков, параллельно обрабатывающих сообщения. Чтобы использовать этот режим параллелизма, реализация службы должна быть потокобезопасной.  
  
- <xref:System.ServiceModel.ConcurrencyMode.Reentrant>: каждый экземпляр службы одновременно обрабатывает одно сообщение, но принимает вызовы операций с повторным входом. Служба принимает эти вызовы только тогда, когда она вызывает через объект клиента WCF.  
  
> [!NOTE]
> Проектирование и разработка кода, который может безопасно использовать несколько потоков, может оказаться непростым делом. Перед использованием значения <xref:System.ServiceModel.ConcurrencyMode.Multiple> или <xref:System.ServiceModel.ConcurrencyMode.Reentrant> убедитесь, что служба должным образом разработана для поддержки этих режимов. Дополнительные сведения см. в разделе <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A>.  
  
 Использование параллелизма связано с режимом создания экземпляров. В <xref:System.ServiceModel.InstanceContextMode.PerCall> инстансционе, параллелизм не имеет значения, потому что каждое сообщение обрабатывается новым <xref:System.ServiceModel.InstanceContext> и, следовательно, не более одного потока активен в . <xref:System.ServiceModel.InstanceContext>  
  
 В приведенном ниже коде представлен пример задания для свойства <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> значения <xref:System.ServiceModel.ConcurrencyMode.Multiple>.  
  
```csharp
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
|PerCall|- Поведение с сессионным <xref:System.ServiceModel.InstanceContext> каналом: сеанс и для каждого звонка.<br />- Поведение с каналом без сеанса: выбрасывается исключение.|- Поведение с сессионным <xref:System.ServiceModel.InstanceContext> каналом: сеанс и для каждого звонка.<br />- Поведение с бессессионным каналом: An <xref:System.ServiceModel.InstanceContext> для каждого звонка.|- Поведение с сессионным каналом: выбрасывается исключение.<br />- Поведение с бессессионным каналом: An <xref:System.ServiceModel.InstanceContext> для каждого звонка.|  
|PerSession|- Поведение с сессионным <xref:System.ServiceModel.InstanceContext> каналом: сеанс и для каждого канала.<br />- Поведение с каналом без сеанса: выбрасывается исключение.|- Поведение с сессионным <xref:System.ServiceModel.InstanceContext> каналом: сеанс и для каждого канала.<br />- Поведение с бессессионным каналом: An <xref:System.ServiceModel.InstanceContext> для каждого звонка.|- Поведение с сессионным каналом: выбрасывается исключение.<br />- Поведение с бессессионным каналом: An <xref:System.ServiceModel.InstanceContext> для каждого звонка.|  
|Один|- Поведение с сеансивным <xref:System.ServiceModel.InstanceContext> каналом: сеанс и один для всех вызовов.<br />- Поведение с каналом без сеанса: выбрасывается исключение.|- Поведение с сеансивным <xref:System.ServiceModel.InstanceContext> каналом: сеанс и для созданного или пользовательского синглтона.<br />- Поведение с каналом <xref:System.ServiceModel.InstanceContext> без сеанса: An для созданного или пользовательского синглтона.|- Поведение с сессионным каналом: выбрасывается исключение.<br />- Поведение с каналом <xref:System.ServiceModel.InstanceContext> без сеанса: An для каждого созданного синглтона или для определенного пользователем синглтона.|  
  
## <a name="see-also"></a>См. также раздел

- [Использование сеансов](../../../../docs/framework/wcf/using-sessions.md)
- [Практическое руководство. Создание службы, для которой требуются сеансы](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
- [Практическое руководство. Управление созданием экземпляров служб](../../../../docs/framework/wcf/feature-details/how-to-control-service-instancing.md)
- [Параллелизма](../../../../docs/framework/wcf/samples/concurrency.md)
- [Создание экземпляров](../../../../docs/framework/wcf/samples/instancing.md)
- [Сессии](../../../../docs/framework/wcf/samples/session.md)
