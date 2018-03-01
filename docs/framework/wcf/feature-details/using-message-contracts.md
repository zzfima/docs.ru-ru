---
title: "Использование контрактов сообщений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message contracts [WCF]
ms.assetid: 1e19c64a-ae84-4c2f-9155-91c54a77c249
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: db19b5188c98d157b98d65422ee38d4ed59f733a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="using-message-contracts"></a>Использование контрактов сообщений
Обычно при построении приложений [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] разработчики уделяют пристальное внимание структурам данных и вопросам сериализации, при этом им не требуется заниматься структурой сообщений, в которых передаются данные. Для таких приложений создание контрактов данных для параметров или возвращаемых значений представляет собой достаточно простую задачу. ([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Указание входящий трафик передачи данных в контрактах служб](../../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md).)  
  
 Тем не менее, иногда полный контроль над структурой сообщения SOAP столь же важен, сколь и контроль над его содержимым. Это особенно актуально, если важно обеспечить взаимодействие или контролировать определенные вопросы безопасности на уровне сообщения или части сообщения. В этих случаях можно создать *контракт сообщения* , позволяющий указать структуру точный нужного сообщения SOAP.  
  
 В этом разделе рассматривается использование различных атрибутов контрактов сообщений для создания конкретного контракта сообщения для данной операции.  
  
## <a name="using-message-contracts-in-operations"></a>Использование контрактов сообщений в операциях  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]поддерживает операции, моделируемые на основе либо *удаленной процедуры вызова (RPC) стиль* или *стиля сообщений*. В операции в стиле RPC можно использовать любой сериализуемый тип и иметь в распоряжении функции, доступные локальным вызовам, такие как множественные параметры и параметры `ref` и `out`. В этом стиле выбранная форма сериализации определяет структуру данных в соответствующих сообщениях, а сообщения для поддержки операции создаются средой выполнения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Это позволяет разработчикам, не знакомым с протоколом SOAP и сообщениями SOAP, быстро и просто создавать и использовать приложения служб.  
  
 В приведенном ниже примере кода показана операция службы, смоделированная на основе стиля RPC.  
  
```csharp  
[OperationContract]  
public BankingTransactionResponse PostBankingTransaction(BankingTransaction bt);  
```  
  
 Как правило, контракта данных достаточно для определения схемы для сообщений. Например, в предыдущем примере для большинства приложений будет достаточно, если `BankingTransaction` и `BankingTransactionResponse` имеют контракты данных для определения содержимого соответствующих сообщений SOAP. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]контрактах данных см. в разделе [использование контрактов данных](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).  
  
 Однако иногда необходимо точно контролировать процесс передачи структуры сообщения SOAP. Наиболее распространенным сценарием в таком случае является вставка настраиваемых заголовков SOAP. Другой часто используемый сценарий - определить свойства безопасности для заголовков и тела сообщения, т. е. решить, будут ли эти элементы снабжаться цифровой подписью и шифроваться. Наконец, для некоторых сторонних стеков SOAP необходимо, чтобы сообщения имели конкретный формат. Такого рода контроль обеспечивается операциями в стиле сообщений.  
  
 Операция в стиле сообщений имеет максимум один параметр и одно возвращаемое значение, причем оба типа являются типами сообщений, т. е. они сериализуются непосредственно в заданную структуру сообщения SOAP. Это может быть любой тип, отмеченный атрибутом <xref:System.ServiceModel.MessageContractAttribute>, или тип <xref:System.ServiceModel.Channels.Message>. В приведенном ниже примере кода показана операция, схожая с показанной выше операцией в стиле RPC, однако смоделированная на основе стиля сообщений.  
  
 Например, если и `BankingTransaction`, и `BankingTransactionResponse` представляют собой типы, являющиеся контрактами сообщений, код в следующих операциях является допустимым.  
  
```csharp  
[OperationContract]  
BankingTransactionResponse Process(BankingTransaction bt);  
[OperationContract]  
void Store(BankingTransaction bt);  
[OperationContract]  
BankingTransactionResponse GetResponse();  
```  
  
 В то же время следующий код является недопустимым.  
  
```csharp  
[OperationContract]  
bool Validate(BankingTransaction bt);  
// Invalid, the return type is not a message contract.  
[OperationContract]  
void Reconcile(BankingTransaction bt1, BankingTransaction bt2);  
// Invalid, there is more than one parameter.  
```  
  
 Для каждой операции с участием типа с контрактом сообщения, не соответствующей одному из допустимых шаблонов, вызывается исключение. Конечно, на операции без участия типов с контрактами сообщений эти ограничения не распространяются.  
  
 Если тип имеет и контракт сообщения, и контракт данных, при использовании типа в операции во внимание принимается только его контракт сообщения.  
  
## <a name="defining-message-contracts"></a>Определение контрактов сообщений  
 Чтобы определить контракт сообщения для типа (т. е. определить сопоставление между типом и конвертом SOAP), примените к типу атрибут <xref:System.ServiceModel.MessageContractAttribute>. Затем примените атрибут <xref:System.ServiceModel.MessageHeaderAttribute> к тем членам типа, которые требуется превратить в заголовки SOAP, и примените атрибут <xref:System.ServiceModel.MessageBodyMemberAttribute> к тем членам, которые требуется превратить в части тела сообщения SOAP.  
  
 Приведенный ниже код представляет собой пример использования контракта сообщения.  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageHeader] public DateTime transactionDate;  
  [MessageBodyMember] private Account sourceAccount;  
  [MessageBodyMember] private Account targetAccount;  
  [MessageBodyMember] public int amount;  
}  
```  
  
 При использовании этого типа в качестве параметра операции формируется следующий конверт SOAP:  
  
```xml  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
  <s:Header>  
    <h:operation xmlns:h="http://tempuri.org/" xmlns="http://tempuri.org/">Deposit</h:operation>  
    <h:transactionDate xmlns:h="http://tempuri.org/" xmlns="http://tempuri.org/">2012-02-16T16:10:00</h:transactionDate>  
  </s:Header>  
  <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
    <BankingTransaction xmlns="http://tempuri.org/">  
      <amount>0</amount>  
      <sourceAccount xsi:nil="true"/>  
      <targetAccount xsi:nil="true"/>  
    </BankingTransaction>  
  </s:Body>  
</s:Envelope>  
```  
  
 Обратите внимание, что `operation` и `transactionDate` выглядят как заголовки SOAP, а текст SOAP состоит из элемента-оболочки `BankingTransaction`, содержащего элементы `sourceAccount`, `targetAccount` и `amount`.  
  
 Атрибуты <xref:System.ServiceModel.MessageHeaderAttribute> и <xref:System.ServiceModel.MessageBodyMemberAttribute> можно применять ко всем полям, свойствам и событиям, независимо от того, являются они открытыми, закрытыми, защищенными или внутренними.  
  
 Атрибут <xref:System.ServiceModel.MessageContractAttribute> позволяет указать атрибуты WrapperName и WrapperNamespace, от которых зависит имя элемента-оболочки в тексте сообщения SOAP. По умолчанию имя контракта сообщения типа используется для оболочки и пространства имен, в котором определен контракт сообщения `HYPERLINK "http://tempuri.org/" http://tempuri.org/` используется в качестве пространства имен по умолчанию.  
  
> [!NOTE]
>  Атрибуты <xref:System.Runtime.Serialization.KnownTypeAttribute> в контрактах сообщений не учитываются. Если атрибут <xref:System.Runtime.Serialization.KnownTypeAttribute> необходим, поместите его в операцию, в которой используется данный контракт сообщения.  
  
## <a name="controlling-header-and-body-part-names-and-namespaces"></a>Управление именами и пространствами имен заголовков и разделов тела  
 В SOAP-представлении контракта сообщения каждый заголовок и раздел тела сообщения сопоставляется с XML-элементом, имеющим имя и пространство имен.  
  
 По умолчанию пространство имен совпадает с пространством имен контракта службы, в котором участвует сообщение, а имя определяется именем члена, к которому применены атрибуты <xref:System.ServiceModel.MessageHeaderAttribute> или <xref:System.ServiceModel.MessageBodyMemberAttribute>.  
  
 Изменить значения по умолчанию можно, изменив свойства <xref:System.ServiceModel.MessageContractMemberAttribute.Name%2A?displayProperty=nameWithType> и <xref:System.ServiceModel.MessageContractMemberAttribute.Namespace%2A?displayProperty=nameWithType> (в родительском классе атрибутов <xref:System.ServiceModel.MessageHeaderAttribute> и <xref:System.ServiceModel.MessageBodyMemberAttribute>).  
  
 Рассмотрим класс в следующем примере кода.  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageHeader(Namespace="http://schemas.contoso.com/auditing/2005")] public bool IsAudited;  
  [MessageBodyMember(Name="transactionData")] public BankingTransactionData theData;  
}  
```  
  
 В этом примере заголовок `IsAudited` находится в пространстве имен, заданном в коде, а раздел тела сообщения, представляющий член `theData`, представляется XML-элементом с именем `transactionData`. Ниже приведен код XML, сформированный для данного контракта сообщения.  
  
```xml  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
  <s:Header>  
    <h:IsAudited xmlns:h="http://schemas.contoso.com/auditing/2005" xmlns="http://schemas.contoso.com/auditing/2005">false</h:IsAudited>  
    <h:operation xmlns:h="http://tempuri.org/" xmlns="http://tempuri.org/">Deposit</h:operation>  
  </s:Header>  
  <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
    <AuditedBankingTransaction xmlns="http://tempuri.org/">  
      <transactionData/>  
    </AuditedBankingTransaction>  
  </s:Body>  
</s:Envelope>  
```  
  
## <a name="controlling-whether-the-soap-body-parts-are-wrapped"></a>Управление заключением разделов тела SOAP-сообщений в оболочку  
 По умолчанию разделы тела SOAP-сообщения сериализуются внутри заключенного в оболочку элемента. Например, в следующем коде показан элемент-оболочка `HelloGreetingMessage`, сформированный из имени типа <xref:System.ServiceModel.MessageContractAttribute> в контракте сообщения для сообщения `HelloGreetingMessage`.  
  
 [!code-csharp[MessageHeaderAttribute#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/messageheaderattribute/cs/services.cs#3)]
 [!code-vb[MessageHeaderAttribute#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/messageheaderattribute/vb/services.vb#3)]  
  
 Чтобы подавить элемент-оболочку, присвойте свойству <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> значение `false`. Для управления именем и пространством имен элемента-оболочки используются свойства <xref:System.ServiceModel.MessageContractAttribute.WrapperName%2A> и <xref:System.ServiceModel.MessageContractAttribute.WrapperNamespace%2A>.  
  
> [!NOTE]
>  Наличие в сообщениях без оболочки более одного раздела тела противоречит WS-I Basic Profile 1.1 и не рекомендуется при разработке новых контрактов сообщений. Тем не менее, в некоторых сценариях взаимодействия может понадобиться иметь несколько разделов тела сообщения без оболочек. Если планируется передавать в теле сообщения более одного блока данных, рекомендуется использовать режим по умолчанию (с оболочкой). Наличие в сообщениях без оболочки нескольких заголовков полностью приемлемо.  
  
## <a name="using-custom-types-inside-message-contracts"></a>Использование пользовательских типов внутри контрактов сообщений  
 Каждый отдельный заголовок сообщения и раздел тела сообщения сериализуется (превращается в XML) с помощью модуля сериализации, выбранного для контракта службы, где используется сообщение. Модуль сериализации по умолчанию - `XmlFormatter` - способен обработать любой тип, имеющий контракт данных либо явно (т. е. имеющий атрибут <xref:System.Runtime.Serialization.DataContractAttribute?displayProperty=nameWithType>), либо неявно (являющийся типом-примитивом, имеющий атрибут <xref:System.SerializableAttribute?displayProperty=nameWithType> и т. д.). [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Использование контрактов данных](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).  
  
 В приведенном выше примере типы полей `Operation` и `BankingTransactionData` должны иметь контракт данных, а поле `transactionDate` является сериализуемым, потому что тип <xref:System.DateTime> является примитивом (и как таковой имеет неявный контракт данных).  
  
 Тем не менее, можно перейти на другой модуль сериализации - `XmlSerializer`. В случае такого перехода необходимо убедиться, что все типы, используемые для заголовков и разделов тела сообщений, сериализуются с помощью `XmlSerializer`.  
  
## <a name="using-arrays-inside-message-contracts"></a>Использование массивов внутри контрактов сообщений  
 В контрактах сообщений можно использовать массивы повторяющихся элементов, причем двумя способами.  
  
 Первый способ - использовать атрибут <xref:System.ServiceModel.MessageHeaderAttribute> или <xref:System.ServiceModel.MessageBodyMemberAttribute> непосредственно в массиве. В этом случае весь массив сериализуется как один элемент (т. е. один заголовок или один раздел тела) с несколькими дочерними элементами. Рассмотрим класс в следующем примере.  
  
```csharp  
[MessageContract]  
public class BankingDepositLog  
{  
  [MessageHeader] public int numRecords;  
  [MessageHeader] public DepositRecord[] records;  
  [MessageHeader] public int branchID;  
}  
```  
  
 В результате формируются заголовки SOAP-сообщения следующего вида.  
  
```xml  
<BankingDepositLog>  
<numRecords>3</numRecords>  
<records>  
  <DepositRecord>Record1</DepositRecord>  
  <DepositRecord>Record2</DepositRecord>  
  <DepositRecord>Record3</DepositRecord>  
</records>  
<branchID>20643</branchID>  
</BankingDepositLog>  
```  
  
 Альтернативный вариант - использовать атрибут <xref:System.ServiceModel.MessageHeaderArrayAttribute>. В этом случае каждый элемент массива сериализуется независимо и, следовательно, каждый элемент массива имеет один заголовок, как показано ниже.  
  
```xml  
<numRecords>3</numRecords>  
<records>Record1</records>  
<records>Record2</records>  
<records>Record3</records>  
<branchID>20643</branchID>  
```  
  
 В качестве имени записей массива по умолчанию используется имя члена, к которому применены атрибуты <xref:System.ServiceModel.MessageHeaderArrayAttribute>.  
  
 Атрибут <xref:System.ServiceModel.MessageHeaderArrayAttribute> наследуется от класса <xref:System.ServiceModel.MessageHeaderAttribute>. Он имеет тот же набор возможностей, что и атрибуты, не являющиеся массивами; например, можно задать порядок, имя и пространство имен для массива заголовков таким же образом, каким они задаются для отдельного заголовка. При использовании для массива свойство `Order` применяется ко всему массиву.  
  
 Атрибут <xref:System.ServiceModel.MessageHeaderArrayAttribute> можно применять только к массивам, но не к коллекциям.  
  
## <a name="using-byte-arrays-in-message-contracts"></a>Использование байтовых массивов в контрактах сообщений  
 При использовании с не являющимися массивами атрибутами (<xref:System.ServiceModel.MessageBodyMemberAttribute> и <xref:System.ServiceModel.MessageHeaderAttribute>) байтовые массивы рассматриваются не как массивы, а как особый тип-примитив, который в итоговом XML-коде представляется данными в кодировке Base64.  
  
 При использовании байтовых массивов с атрибутом-массивом <xref:System.ServiceModel.MessageHeaderArrayAttribute> результаты зависят от используемого сериализатора. При использовании сериализатора по умолчанию массив представляется в виде отдельных записей для каждого байта. Если же выбран сериализатор `XmlSerializer` (с помощью атрибута <xref:System.ServiceModel.XmlSerializerFormatAttribute> в контракте службы), байтовые массивы рассматриваются как данные в кодировке Base64 независимо от того, какие атрибуты используются - массивы или нет.  
  
## <a name="signing-and-encrypting-parts-of-the-message"></a>Подписывание и шифрование частей сообщения  
 В контракте сообщения может быть указано, следует ли снабжать заголовки и/или тело сообщения цифровыми подписями и шифровать.  
  
 Это можно сделать, задав свойство <xref:System.ServiceModel.MessageContractMemberAttribute.ProtectionLevel%2A?displayProperty=nameWithType> атрибутов <xref:System.ServiceModel.MessageHeaderAttribute> и <xref:System.ServiceModel.MessageBodyMemberAttribute>. Это свойство является перечислением типа <xref:System.Net.Security.ProtectionLevel?displayProperty=nameWithType> и может принимать значения <xref:System.Net.Security.ProtectionLevel.None> (без шифрования или подписи), <xref:System.Net.Security.ProtectionLevel.Sign> (только цифровая подпись) или <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> (и шифрование, и цифровая подпись). Значение по умолчанию — <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.  
  
 Чтобы эти возможности безопасности работали, необходимо надлежащим образом настроить привязку и расширения функциональности. При использовании этих функций безопасности без надлежащей настройки (например, при попытке подписать сообщение без предоставления учетных данных) во время проверки будет вызвано исключение.  
  
 Для заголовков сообщений уровень защиты определяется отдельно для каждого заголовка.  
  
 Для разделов тела сообщений уровень защиты можно понимать как «минимальный уровень защиты». Тело имеет только один уровень защиты, независимо от количества разделов тела. Уровень защиты текста определяется наивысшим из значений свойства <xref:System.ServiceModel.MessageContractMemberAttribute.ProtectionLevel%2A> всех разделов текста. Тем не менее для каждого раздела тела сообщения следует задавать фактически необходимый минимальный уровень защиты.  
  
 Рассмотрим класс в следующем примере кода.  
  
```csharp  
[MessageContract]  
public class PatientRecord  
{  
   [MessageHeader(ProtectionLevel=None)] public int recordID;  
   [MessageHeader(ProtectionLevel=Sign)] public string patientName;  
   [MessageHeader(ProtectionLevel=EncryptAndSign)] public string SSN;  
   [MessageBodyMember(ProtectionLevel=None)] public string comments;  
   [MessageBodyMember(ProtectionLevel=Sign)] public string diagnosis;  
   [MessageBodyMember(ProtectionLevel=EncryptAndSign)] public string medicalHistory;  
}  
```  
  
 В этом примере заголовок `recordID` не защищается, заголовок `patientName`					`signed`, а заголовок `SSN` шифруется и подписывается. Как минимум к одному разделу тела - `medicalHistory` - применено свойство <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>; следовательно, все тело сообщения шифруется и подписывается, хотя для разделов комментариев и диагноза заданы более низкие уровни защиты.  
  
## <a name="soap-action"></a>Свойство Action протокола SOAP  
 В протоколе SOAP и связанных с ним стандартах веб-служб определено свойство с именем `Action`, которое может присутствовать для каждого оправляемого SOAP-сообщения. Значение этого свойства определяется свойствами <xref:System.ServiceModel.OperationContractAttribute.Action%2A?displayProperty=nameWithType> и <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A?displayProperty=nameWithType> операции.  
  
## <a name="soap-header-attributes"></a>Атрибуты заголовка по протоколу SOAP  
 В стандарте протокола SOAP определены следующие атрибуты, которые могут присутствовать в заголовке:  
  
-   `Actor/Role` (`Actor` в SOAP 1.1, `Role` в SOAP 1.2)  
  
-   `MustUnderstand`  
  
-   `Relay`  
  
 Атрибут `Actor` или `Role` задает универсальный код ресурса (URI) узла, для которого предназначен данный заголовок. Атрибут `MustUnderstand` указывает, должен ли обрабатывающий заголовок узел понимать его. Атрибут `Relay` указывает, надо ли передавать заголовок на нижележащие узлы. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не обрабатывает эти атрибуты при наличии входящих сообщений, за исключением атрибута `MustUnderstand` (см. подраздел «Управление версиями контракта сообщения» ниже в этом разделе). Тем не менее, при необходимости эти атрибуты можно считывать и записывать, как описано ниже.  
  
 При отправке сообщения эти атрибуты по умолчанию не выдаются. Это поведение можно изменить двумя способами. Во-первых, можно статически присвоить атрибутам любые требуемые значения, изменяя свойства <xref:System.ServiceModel.MessageHeaderAttribute.Actor%2A?displayProperty=nameWithType>, <xref:System.ServiceModel.MessageHeaderAttribute.MustUnderstand%2A?displayProperty=nameWithType> и <xref:System.ServiceModel.MessageHeaderAttribute.Relay%2A?displayProperty=nameWithType>, как показано в предыдущем примере кода. (Обратите внимание, что свойства `Role` здесь нет; задание свойства <xref:System.ServiceModel.MessageHeaderAttribute.Actor%2A> порождает атрибут `Role` при использовании протокола SOAP 1.2).  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader(Actor="http://auditingservice.contoso.com", MustUnderstand=true)] public bool IsAudited;  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember] public BankingTransactionData theData;  
}  
```  
  
 Второй способ управлять этими атрибутами - динамически посредством кода. Это можно делать, заключая требуемый тип заголовка в тип <xref:System.ServiceModel.MessageHeader%601> (не путайте этот тип с неуниверсальной версией) и используя тип вместе с атрибутом <xref:System.ServiceModel.MessageHeaderAttribute>. Затем можно использовать свойства класса <xref:System.ServiceModel.MessageHeader%601> для задания атрибутов протокола SOAP, как показано в следующем примере кода.  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public MessageHeader<bool> IsAudited;  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember] public BankingTransactionData theData;  
}  
// application code:  
BankingTransaction bt = new BankingTransaction();  
bt.IsAudited = new MessageHeader<bool>();  
bt.IsAudited.Content = false; // Set IsAudited header value to "false"  
bt.IsAudited.Actor="http://auditingservice.contoso.com";  
bt.IsAudited.MustUnderstand=true;  
```  
  
 Если используются и динамический, и статический механизмы управления, статические параметры используются по умолчанию, однако могут позднее быть переопределены с помощью динамического механизма, как показано в следующем примере кода.  
  
```csharp  
[MessageHeader(MustUnderstand=true)] public MessageHeader<Person> documentApprover;  
// later on in the code:  
BankingTransaction bt = new BankingTransaction();  
bt.documentApprover = new MessageHeader<Person>();  
bt.documentApprover.MustUnderstand = false; // override the static default of 'true'  
```  
  
 Допускается создание повторяющихся заголовков с динамическим управлением атрибутами, как показано в следующем примере кода.  
  
```csharp  
[MessageHeaderArray] public MessageHeader<Person> documentApprovers[];  
```  
  
 На стороне получения чтение этих атрибутов SOAP возможно только при использовании класса <xref:System.ServiceModel.MessageHeader%601> для заголовка в типе. Для определения значений атрибутов полученного сообщения рассмотрите свойства `Actor`, `Relay` или `MustUnderstand` заголовка типа <xref:System.ServiceModel.MessageHeader%601>.  
  
 При получении сообщения и затем отправке его обратно круговой путь совершают только значения атрибутов SOAP для заголовков типа <xref:System.ServiceModel.MessageHeader%601>.  
  
## <a name="order-of-soap-body-parts"></a>Порядок разделов тела SOAP-сообщения  
 В некоторых случаях может потребоваться управлять порядком разделов тела сообщения. По умолчанию порядок элементов текста сообщения алфавитный, однако его можно изменить с помощью свойства <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A?displayProperty=nameWithType>. Это свойство имеет ту же семантику, что и свойство <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A?displayProperty=nameWithType>, за исключением поведения в сценариях наследования (в контрактах сообщений элементы тела сообщения базовых типов не сортируются перед элементами тела сообщения производных типов). [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Порядок членов данных](../../../../docs/framework/wcf/feature-details/data-member-order.md).  
  
 В следующем примере элемент `amount` в обычном случае был бы первым, поскольку он идет первым по алфавиту. Однако в данном случае свойство <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A> помещает его на третью позицию.  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember(Order=1)] public Account sourceAccount;  
  [MessageBodyMember(Order=2)] public Account targetAccount;  
  [MessageBodyMember(Order=3)] public int amount;  
}  
```  
  
## <a name="message-contract-versioning"></a>Управление версиями контракта сообщения  
 Иногда контракты сообщений требуется изменять. Например, новая версия приложения может добавлять в сообщение дополнительный заголовок. Затем при отправке сообщений от новой версии к старой системе приходится иметь дело с дополнительным заголовком, равно как и с недостающим заголовком при отправке сообщений в обратном направлении.  
  
 К управлению версиями заголовков применяются следующие правила.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не возражает против недостающих заголовков - соответствующие члены сохраняют свои значения по умолчанию.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] также не учитывает непредвиденные дополнительные заголовки. Единственное исключение из этого правила - когда дополнительный заголовок входящего SOAP-сообщения имеет атрибут `MustUnderstand` со значением `true`. В этом случае вызывается исключение, поскольку не удается обработать заголовок, который должен быть понят.  
  
 Аналогичные правила управления версиями применяются к телам сообщений - и недостающие, и дополнительные разделы тела сообщения не учитываются.  
  
## <a name="inheritance-considerations"></a>Замечания о наследовании  
 Тип с контрактом сообщения может наследовать от другого типа при условии, что базовый тип также имеет контракт сообщения.  
  
 При создании сообщения или доступе к сообщению с использованием типа с контрактом сообщения, наследующего от других типов с контрактами сообщений, применяются следующие правила.  
  
-   Все заголовки сообщения в иерархии наследования собираются вместе и образуют полный набор заголовков для сообщения.  
  
-   Все разделы тела сообщения в иерархии наследования собираются вместе и образуют полное тело сообщения. Разделы текста сообщения упорядочиваются согласно обычным правилам (по свойству <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A?displayProperty=nameWithType>, а затем по алфавиту), независимо от их места в иерархии наследования. Использовать наследование контрактов сообщения в случаях, где разделы тела сообщения имеются на нескольких уровнях дерева наследования, крайне нежелательно. Если базовый класс и производный класс определяют заголовок или раздел тела сообщения с одинаковым именем, для хранения значения этого заголовка или раздела тела используется член «самого базового» класса.  
  
 Рассмотрим классы в следующем примере кода.  
  
```csharp  
[MessageContract]  
public class PersonRecord  
{  
  [MessageHeader(Name="ID")] public int personID;  
  [MessageBodyMember] public string patientName;  
}  
  
[MessageContract]  
public class PatientRecord : PersonRecord  
{  
  [MessageHeader(Name="ID")] public int patientID;  
  [MessageBodyMember] public string diagnosis;  
}  
```  
  
 Класс `PatientRecord` описывает сообщение с одним заголовком с именем `ID`. Этот заголовок соответствует члену `personID`, а не члену `patientID`, поскольку выбирается самый базовый член. Следовательно, поле `patientID` в этом случае бесполезно. Тело сообщения содержит элемент `diagnosis`, за которым следует элемент `patientName` (алфавитный порядок). Обратите внимание, что в этом примере показана крайне нежелательная схема: и в базовом, и в производном контракте сообщения имеются разделы тела сообщения.  
  
## <a name="wsdl-considerations"></a>Замечания о WSDL  
 При создании контракта на языке WSDL из службы, в которой используются контракты сообщений, важно помнить, что в полученном WSDL-коде отражаются не все возможности контракта сообщения. Необходимо учитывать следующее.  
  
-   На языке WSDL нельзя выразить понятие массива заголовков. При создании сообщений с массивом заголовков с использованием атрибута <xref:System.ServiceModel.MessageHeaderArrayAttribute> в полученном WSDL-коде вместо массива отражается только один заголовок.  
  
-   Полученный WSDL-документ может не отражать некоторую информацию об уровне защиты.  
  
-   Имя типа сообщения, сформированного в WSDL-коде, совпадает с именем класса типа контракта сообщения.  
  
-   При использовании в нескольких операциях одного и того же контракта сообщения в WSDL-документе формируется несколько типов сообщений. Имена делаются уникальными путем добавления номеров "2", "3" и т. д. для использования в дальнейшем. При обратном импорте WSDL-кода создается несколько типов с контрактами сообщений, идентичных за исключением имен.  
  
## <a name="soap-encoding-considerations"></a>Замечания о кодировании SOAP  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] позволяет использовать устаревший стиль кодирования SOAP в XML, что, однако, не рекомендуется. При использовании этого стиля (путем присвоения значения `Use` свойству `Encoded` атрибута <xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=nameWithType>, примененного к контракту службы) следует принять во внимание также следующее.  
  
-   Заголовки сообщений не поддерживаются; это значит, что атрибут <xref:System.ServiceModel.MessageHeaderAttribute> и атрибут-массив <xref:System.ServiceModel.MessageHeaderArrayAttribute> несовместимы с кодированием SOAP.  
  
-   Если контракт сообщения не заключен в оболочку, т. е. если свойство <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> имеет значение `false`, контракт сообщения может иметь только один раздел тела сообщения.  
  
-   Имя элемента-оболочки для контракта сообщения запроса должно совпадать с именем операции. Для этого используется свойство `WrapperName` контракта сообщения.  
  
-   Имя элемента-оболочки для контракта ответного сообщения должно представлять собой имя операции, снабженное суффиксом "Response". Для этого используется свойство <xref:System.ServiceModel.MessageContractAttribute.WrapperName%2A> контракта сообщения.  
  
-   Кодирование SOAP сохраняет ссылки на объекты. Например, рассмотрим следующий код.  
  
    ```csharp  
    [MessageContract(WrapperName="updateChangeRecord")]  
    public class ChangeRecordRequest  
    {  
      [MessageBodyMember] Person changedBy;  
      [MessageBodyMember] Person changedFrom;  
      [MessageBodyMember] Person changedTo;  
    }  
  
    [MessageContract(WrapperName="updateChangeRecordResponse")]  
    public class ChangeRecordResponse  
    {  
      [MessageBodyMember] Person changedBy;  
      [MessageBodyMember] Person changedFrom;  
      [MessageBodyMember] Person changedTo;  
    }  
  
    // application code:  
    ChangeRecordRequest cr = new ChangeRecordRequest();  
    Person p = new Person("John Doe");  
    cr.changedBy=p;  
    cr.changedFrom=p;  
    cr.changedTo=p;  
    ```  
  
 После сериализации сообщения с использованием кодирования SOAP элементы `changedFrom` и `changedTo` не содержат собственных копий `p`, а вместо этого указывают на копию внутри элемента `changedBy`.  
  
## <a name="performance-considerations"></a>Особенности производительности  
 Каждый заголовок сообщения и раздел тела сообщения сериализуется независимо от других. Следовательно, одни те же пространства имен могут повторно объявляться для каждого заголовка и раздела тела. Для улучшения производительности, особенно в части размера сообщения на линии связи, множественные заголовки и разделы тела сообщения следует объединять в один заголовок или раздел тела. Например, вместо следующего кода  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember] public Account sourceAccount;  
  [MessageBodyMember] public Account targetAccount;  
  [MessageBodyMember] public int amount;  
}  
```  
  
 используйте такой код:  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember] public OperationDetails details;  
}  
  
[DataContract]  
public class OperationDetails  
{  
  [DataMember] public Account sourceAccount;  
  [DataMember] public Account targetAccount;  
  [DataMember] public int amount;  
}  
```  
  
### <a name="event-based-asynchronous-and-message-contracts"></a>Асинхронная модель на основе событий и контракты сообщений  
 Согласно правилам разработки для асинхронной модели на основе событий, если возвращается несколько значений, одно значение возвращается как свойство `Result`, а остальные возвращаются как свойства объекта <xref:System.EventArgs>. Одним из результатов этого является то, что если клиент импортирует метаданные с использованием параметров асинхронных команд на основе событий и операция возвращает более одного значения, объект <xref:System.EventArgs> по умолчанию возвращает одно значение как свойство `Result`, а остальные являются свойствами объекта <xref:System.EventArgs>.  
  
 Если требуется получать объект сообщения как свойство `Result`, чтобы возвращаемые значения были свойствами этого объекта, используйте параметр команды `/messageContract`. При этом формируется сигнатура, которая возвращает ответное сообщение как свойство `Result` объекта <xref:System.EventArgs>. Все внутренние возвращаемые значения тогда будут свойствами объекта ответного сообщения.  
  
## <a name="see-also"></a>См. также  
 [Использование контрактов данных](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [Проектирование и реализация служб](../../../../docs/framework/wcf/designing-and-implementing-services.md)
