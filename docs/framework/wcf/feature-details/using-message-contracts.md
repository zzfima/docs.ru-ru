---
title: "Использование контрактов сообщений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: message contracts [WCF]
ms.assetid: 1e19c64a-ae84-4c2f-9155-91c54a77c249
caps.latest.revision: "46"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 521393aabb9d5674b00194926cb67071cc4566bc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="using-message-contracts"></a><span data-ttu-id="ec13d-102">Использование контрактов сообщений</span><span class="sxs-lookup"><span data-stu-id="ec13d-102">Using Message Contracts</span></span>
<span data-ttu-id="ec13d-103">Обычно при построении приложений [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] разработчики уделяют пристальное внимание структурам данных и вопросам сериализации, при этом им не требуется заниматься структурой сообщений, в которых передаются данные.</span><span class="sxs-lookup"><span data-stu-id="ec13d-103">Typically when building [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] applications, developers pay close attention to the data structures and serialization issues and do not need to concern themselves with the structure of the messages in which the data is carried.</span></span> <span data-ttu-id="ec13d-104">Для таких приложений создание контрактов данных для параметров или возвращаемых значений представляет собой достаточно простую задачу.</span><span class="sxs-lookup"><span data-stu-id="ec13d-104">For these applications, creating data contracts for the parameters or return values is straightforward.</span></span> <span data-ttu-id="ec13d-105">([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Указание входящий трафик передачи данных в контрактах служб](../../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md).)</span><span class="sxs-lookup"><span data-stu-id="ec13d-105">([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Specifying Data Transfer in Service Contracts](../../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md).)</span></span>  
  
 <span data-ttu-id="ec13d-106">Тем не менее, иногда полный контроль над структурой сообщения SOAP столь же важен, сколь и контроль над его содержимым.</span><span class="sxs-lookup"><span data-stu-id="ec13d-106">However, sometimes complete control over the structure of a SOAP message is just as important as control over its contents.</span></span> <span data-ttu-id="ec13d-107">Это особенно актуально, если важно обеспечить взаимодействие или контролировать определенные вопросы безопасности на уровне сообщения или части сообщения.</span><span class="sxs-lookup"><span data-stu-id="ec13d-107">This is especially true when interoperability is important or to specifically control security issues at the level of the message or message part.</span></span> <span data-ttu-id="ec13d-108">В этих случаях можно создать *контракт сообщения* , позволяющий указать структуру точный нужного сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="ec13d-108">In these cases, you can create a *message contract* that enables you to specify the structure of the precise SOAP message required.</span></span>  
  
 <span data-ttu-id="ec13d-109">В этом разделе рассматривается использование различных атрибутов контрактов сообщений для создания конкретного контракта сообщения для данной операции.</span><span class="sxs-lookup"><span data-stu-id="ec13d-109">This topic discusses how to use the various message contract attributes to create a specific message contract for your operation.</span></span>  
  
## <a name="using-message-contracts-in-operations"></a><span data-ttu-id="ec13d-110">Использование контрактов сообщений в операциях</span><span class="sxs-lookup"><span data-stu-id="ec13d-110">Using Message Contracts in Operations</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="ec13d-111">поддерживает операции, моделируемые на основе либо *удаленной процедуры вызова (RPC) стиль* или *стиля сообщений*.</span><span class="sxs-lookup"><span data-stu-id="ec13d-111"> supports operations modeled on either the *remote procedure call (RPC) style* or the *messaging style*.</span></span> <span data-ttu-id="ec13d-112">В операции в стиле RPC можно использовать любой сериализуемый тип и иметь в распоряжении функции, доступные локальным вызовам, такие как множественные параметры и параметры `ref` и `out`.</span><span class="sxs-lookup"><span data-stu-id="ec13d-112">In an RPC-style operation, you can use any serializable type, and you have access to the features that are available to local calls, such as multiple parameters and `ref` and `out` parameters.</span></span> <span data-ttu-id="ec13d-113">В этом стиле выбранная форма сериализации определяет структуру данных в соответствующих сообщениях, а сообщения для поддержки операции создаются средой выполнения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ec13d-113">In this style, the form of serialization chosen controls the structure of the data in the underlying messages, and the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] runtime creates the messages to support the operation.</span></span> <span data-ttu-id="ec13d-114">Это позволяет разработчикам, не знакомым с протоколом SOAP и сообщениями SOAP, быстро и просто создавать и использовать приложения служб.</span><span class="sxs-lookup"><span data-stu-id="ec13d-114">This enables developers who are not familiar with SOAP and SOAP messages to quickly and easily create and use service applications.</span></span>  
  
 <span data-ttu-id="ec13d-115">В приведенном ниже примере кода показана операция службы, смоделированная на основе стиля RPC.</span><span class="sxs-lookup"><span data-stu-id="ec13d-115">The following code example shows a service operation modeled on the RPC style.</span></span>  
  
```csharp  
[OperationContract]  
public BankingTransactionResponse PostBankingTransaction(BankingTransaction bt);  
```  
  
 <span data-ttu-id="ec13d-116">Как правило, контракта данных достаточно для определения схемы для сообщений.</span><span class="sxs-lookup"><span data-stu-id="ec13d-116">Normally, a data contract is sufficient to define the schema for the messages.</span></span> <span data-ttu-id="ec13d-117">Например, в предыдущем примере для большинства приложений будет достаточно, если `BankingTransaction` и `BankingTransactionResponse` имеют контракты данных для определения содержимого соответствующих сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="ec13d-117">For instance, in the preceding example, it is sufficient for most applications if `BankingTransaction` and `BankingTransactionResponse` have data contracts to define the contents of the underlying SOAP messages.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="ec13d-118">контрактах данных см. в разделе [использование контрактов данных](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="ec13d-118"> data contracts, see [Using Data Contracts](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).</span></span>  
  
 <span data-ttu-id="ec13d-119">Однако иногда необходимо точно контролировать процесс передачи структуры сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="ec13d-119">However, occasionally it is necessary to precisely control how the structure of the SOAP message transmitted over the wire.</span></span> <span data-ttu-id="ec13d-120">Наиболее распространенным сценарием в таком случае является вставка настраиваемых заголовков SOAP.</span><span class="sxs-lookup"><span data-stu-id="ec13d-120">The most common scenario for this is inserting custom SOAP headers.</span></span> <span data-ttu-id="ec13d-121">Другой часто используемый сценарий - определить свойства безопасности для заголовков и тела сообщения, т. е. решить, будут ли эти элементы снабжаться цифровой подписью и шифроваться.</span><span class="sxs-lookup"><span data-stu-id="ec13d-121">Another common scenario is to define security properties for the message's headers and body, that is, to decide whether these elements are digitally signed and encrypted.</span></span> <span data-ttu-id="ec13d-122">Наконец, для некоторых сторонних стеков SOAP необходимо, чтобы сообщения имели конкретный формат.</span><span class="sxs-lookup"><span data-stu-id="ec13d-122">Finally, some third-party SOAP stacks require messages be in a specific format.</span></span> <span data-ttu-id="ec13d-123">Такого рода контроль обеспечивается операциями в стиле сообщений.</span><span class="sxs-lookup"><span data-stu-id="ec13d-123">Messaging-style operations provide this control.</span></span>  
  
 <span data-ttu-id="ec13d-124">Операция в стиле сообщений имеет максимум один параметр и одно возвращаемое значение, причем оба типа являются типами сообщений, т. е. они сериализуются непосредственно в заданную структуру сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="ec13d-124">A messaging-style operation has at most one parameter and one return value where both types are message types; that is, they serialize directly into a specified SOAP message structure.</span></span> <span data-ttu-id="ec13d-125">Это может быть любой тип, отмеченный атрибутом <xref:System.ServiceModel.MessageContractAttribute>, или тип <xref:System.ServiceModel.Channels.Message>.</span><span class="sxs-lookup"><span data-stu-id="ec13d-125">This may be any type marked with the <xref:System.ServiceModel.MessageContractAttribute> or the <xref:System.ServiceModel.Channels.Message> type.</span></span> <span data-ttu-id="ec13d-126">В приведенном ниже примере кода показана операция, схожая с показанной выше операцией в стиле RPC, однако смоделированная на основе стиля сообщений.</span><span class="sxs-lookup"><span data-stu-id="ec13d-126">The following code example shows an operation similar to the preceding RCP-style, but which uses the messaging style.</span></span>  
  
 <span data-ttu-id="ec13d-127">Например, если и `BankingTransaction`, и `BankingTransactionResponse` представляют собой типы, являющиеся контрактами сообщений, код в следующих операциях является допустимым.</span><span class="sxs-lookup"><span data-stu-id="ec13d-127">For example, if `BankingTransaction` and `BankingTransactionResponse` are both types that are message contracts, then the code in the following operations is valid.</span></span>  
  
```csharp  
[OperationContract]  
BankingTransactionResponse Process(BankingTransaction bt);  
[OperationContract]  
void Store(BankingTransaction bt);  
[OperationContract]  
BankingTransactionResponse GetResponse();  
```  
  
 <span data-ttu-id="ec13d-128">В то же время следующий код является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="ec13d-128">However, the following code is invalid.</span></span>  
  
```csharp  
[OperationContract]  
bool Validate(BankingTransaction bt);  
// Invalid, the return type is not a message contract.  
[OperationContract]  
void Reconcile(BankingTransaction bt1, BankingTransaction bt2);  
// Invalid, there is more than one parameter.  
```  
  
 <span data-ttu-id="ec13d-129">Для каждой операции с участием типа с контрактом сообщения, не соответствующей одному из допустимых шаблонов, вызывается исключение.</span><span class="sxs-lookup"><span data-stu-id="ec13d-129">An exception is thrown for any operation that involves a message contract type and that does not follow one of the valid patterns.</span></span> <span data-ttu-id="ec13d-130">Конечно, на операции без участия типов с контрактами сообщений эти ограничения не распространяются.</span><span class="sxs-lookup"><span data-stu-id="ec13d-130">Of course, operations that do not involve message contract types are not subject to these restrictions.</span></span>  
  
 <span data-ttu-id="ec13d-131">Если тип имеет и контракт сообщения, и контракт данных, при использовании типа в операции во внимание принимается только его контракт сообщения.</span><span class="sxs-lookup"><span data-stu-id="ec13d-131">If a type has both a message contract and a data contract, only its message contract is considered when the type is used in an operation.</span></span>  
  
## <a name="defining-message-contracts"></a><span data-ttu-id="ec13d-132">Определение контрактов сообщений</span><span class="sxs-lookup"><span data-stu-id="ec13d-132">Defining Message Contracts</span></span>  
 <span data-ttu-id="ec13d-133">Чтобы определить контракт сообщения для типа (т. е. определить сопоставление между типом и конвертом SOAP), примените к типу атрибут <xref:System.ServiceModel.MessageContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ec13d-133">To define a message contract for a type (that is, to define the mapping between the type and a SOAP envelope), apply the <xref:System.ServiceModel.MessageContractAttribute> to the type.</span></span> <span data-ttu-id="ec13d-134">Затем примените атрибут <xref:System.ServiceModel.MessageHeaderAttribute> к тем членам типа, которые требуется превратить в заголовки SOAP, и примените атрибут <xref:System.ServiceModel.MessageBodyMemberAttribute> к тем членам, которые требуется превратить в части тела сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="ec13d-134">Then apply the <xref:System.ServiceModel.MessageHeaderAttribute> to those members of the type you want to make into SOAP headers, and apply the <xref:System.ServiceModel.MessageBodyMemberAttribute> to those members you want to make into parts of the SOAP body of the message.</span></span>  
  
 <span data-ttu-id="ec13d-135">Приведенный ниже код представляет собой пример использования контракта сообщения.</span><span class="sxs-lookup"><span data-stu-id="ec13d-135">The following code provides an example of using a message contract.</span></span>  
  
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
  
 <span data-ttu-id="ec13d-136">При использовании этого типа в качестве параметра операции формируется следующий конверт SOAP:</span><span class="sxs-lookup"><span data-stu-id="ec13d-136">When using this type as an operation parameter, the following SOAP envelope is generated:</span></span>  
  
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
  
 <span data-ttu-id="ec13d-137">Обратите внимание, что `operation` и `transactionDate` выглядят как заголовки SOAP, а текст SOAP состоит из элемента-оболочки `BankingTransaction`, содержащего элементы `sourceAccount`, `targetAccount` и `amount`.</span><span class="sxs-lookup"><span data-stu-id="ec13d-137">Notice that `operation` and `transactionDate` appear as SOAP headers and the SOAP body consists of a wrapper element `BankingTransaction` containing `sourceAccount`,`targetAccount`, and `amount`.</span></span>  
  
 <span data-ttu-id="ec13d-138">Атрибуты <xref:System.ServiceModel.MessageHeaderAttribute> и <xref:System.ServiceModel.MessageBodyMemberAttribute> можно применять ко всем полям, свойствам и событиям, независимо от того, являются они открытыми, закрытыми, защищенными или внутренними.</span><span class="sxs-lookup"><span data-stu-id="ec13d-138">You can apply the <xref:System.ServiceModel.MessageHeaderAttribute> and <xref:System.ServiceModel.MessageBodyMemberAttribute> to all fields, properties, and events, regardless of whether they are public, private, protected, or internal.</span></span>  
  
 <span data-ttu-id="ec13d-139">Атрибут <xref:System.ServiceModel.MessageContractAttribute> позволяет указать атрибуты WrapperName и WrapperNamespace, от которых зависит имя элемента-оболочки в тексте сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="ec13d-139">The <xref:System.ServiceModel.MessageContractAttribute> allows you to specify the WrapperName and WrapperNamespace attributes which control the name of the wrapper element in the body of the SOAP message.</span></span> <span data-ttu-id="ec13d-140">По умолчанию имя контракта сообщения типа используется для оболочки и пространства имен, в котором определен контракт сообщения `HYPERLINK "http://tempuri.org/" http://tempuri.org/` используется в качестве пространства имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ec13d-140">By default the name of the message contract type is used for the wrapper and the namespace in which the message contract is defined  `HYPERLINK "http://tempuri.org/" http://tempuri.org/` is used as the default namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec13d-141">Атрибуты <xref:System.Runtime.Serialization.KnownTypeAttribute> в контрактах сообщений не учитываются.</span><span class="sxs-lookup"><span data-stu-id="ec13d-141"><xref:System.Runtime.Serialization.KnownTypeAttribute> attributes are ignored in message contracts.</span></span> <span data-ttu-id="ec13d-142">Если атрибут <xref:System.Runtime.Serialization.KnownTypeAttribute> необходим, поместите его в операцию, в которой используется данный контракт сообщения.</span><span class="sxs-lookup"><span data-stu-id="ec13d-142">If a <xref:System.Runtime.Serialization.KnownTypeAttribute> is required, place it on the operation that is using the message contract in question.</span></span>  
  
## <a name="controlling-header-and-body-part-names-and-namespaces"></a><span data-ttu-id="ec13d-143">Управление именами и пространствами имен заголовков и разделов тела</span><span class="sxs-lookup"><span data-stu-id="ec13d-143">Controlling Header and Body Part Names and Namespaces</span></span>  
 <span data-ttu-id="ec13d-144">В SOAP-представлении контракта сообщения каждый заголовок и раздел тела сообщения сопоставляется с XML-элементом, имеющим имя и пространство имен.</span><span class="sxs-lookup"><span data-stu-id="ec13d-144">In the SOAP representation of a message contract, each header and body part maps to an XML element that has a name and a namespace.</span></span>  
  
 <span data-ttu-id="ec13d-145">По умолчанию пространство имен совпадает с пространством имен контракта службы, в котором участвует сообщение, а имя определяется именем члена, к которому применены атрибуты <xref:System.ServiceModel.MessageHeaderAttribute> или <xref:System.ServiceModel.MessageBodyMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ec13d-145">By default, the namespace is the same as the namespace of the service contract that the message is participating in, and the name is determined by the member name to which the <xref:System.ServiceModel.MessageHeaderAttribute> or the <xref:System.ServiceModel.MessageBodyMemberAttribute> attributes are applied.</span></span>  
  
 <span data-ttu-id="ec13d-146">Изменить значения по умолчанию можно, изменив свойства <xref:System.ServiceModel.MessageContractMemberAttribute.Name%2A?displayProperty=nameWithType> и <xref:System.ServiceModel.MessageContractMemberAttribute.Namespace%2A?displayProperty=nameWithType> (в родительском классе атрибутов <xref:System.ServiceModel.MessageHeaderAttribute> и <xref:System.ServiceModel.MessageBodyMemberAttribute>).</span><span class="sxs-lookup"><span data-stu-id="ec13d-146">You can change these defaults by manipulating the <xref:System.ServiceModel.MessageContractMemberAttribute.Name%2A?displayProperty=nameWithType> and <xref:System.ServiceModel.MessageContractMemberAttribute.Namespace%2A?displayProperty=nameWithType> (on the parent class of the <xref:System.ServiceModel.MessageHeaderAttribute> and <xref:System.ServiceModel.MessageBodyMemberAttribute> attributes).</span></span>  
  
 <span data-ttu-id="ec13d-147">Рассмотрим класс в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="ec13d-147">Consider the class in the following code example.</span></span>  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageHeader(Namespace="http://schemas.contoso.com/auditing/2005")] public bool IsAudited;  
  [MessageBodyMember(Name="transactionData")] public BankingTransactionData theData;  
}  
```  
  
 <span data-ttu-id="ec13d-148">В этом примере заголовок `IsAudited` находится в пространстве имен, заданном в коде, а раздел тела сообщения, представляющий член `theData`, представляется XML-элементом с именем `transactionData`.</span><span class="sxs-lookup"><span data-stu-id="ec13d-148">In this example, the `IsAudited` header is in the namespace specified in the code, and the body part that represents the `theData` member is represented by an XML element with the name `transactionData`.</span></span> <span data-ttu-id="ec13d-149">Ниже приведен код XML, сформированный для данного контракта сообщения.</span><span class="sxs-lookup"><span data-stu-id="ec13d-149">The following shows the XML generated for this message contract.</span></span>  
  
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
  
## <a name="controlling-whether-the-soap-body-parts-are-wrapped"></a><span data-ttu-id="ec13d-150">Управление заключением разделов тела SOAP-сообщений в оболочку</span><span class="sxs-lookup"><span data-stu-id="ec13d-150">Controlling Whether the SOAP Body Parts Are Wrapped</span></span>  
 <span data-ttu-id="ec13d-151">По умолчанию разделы тела SOAP-сообщения сериализуются внутри заключенного в оболочку элемента.</span><span class="sxs-lookup"><span data-stu-id="ec13d-151">By default, the SOAP body parts are serialized inside a wrapped element.</span></span> <span data-ttu-id="ec13d-152">Например, в следующем коде показан элемент-оболочка `HelloGreetingMessage`, сформированный из имени типа <xref:System.ServiceModel.MessageContractAttribute> в контракте сообщения для сообщения `HelloGreetingMessage`.</span><span class="sxs-lookup"><span data-stu-id="ec13d-152">For example, the following code shows the `HelloGreetingMessage` wrapper element generated from the name of the <xref:System.ServiceModel.MessageContractAttribute> type in the message contract for the `HelloGreetingMessage` message.</span></span>  
  
 [!code-csharp[MessageHeaderAttribute#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/messageheaderattribute/cs/services.cs#3)]
 [!code-vb[MessageHeaderAttribute#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/messageheaderattribute/vb/services.vb#3)]  
  
 <span data-ttu-id="ec13d-153">Чтобы подавить элемент-оболочку, присвойте свойству <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> значение `false`.</span><span class="sxs-lookup"><span data-stu-id="ec13d-153">To suppress the wrapper element, set the <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> property to `false`.</span></span> <span data-ttu-id="ec13d-154">Для управления именем и пространством имен элемента-оболочки используются свойства <xref:System.ServiceModel.MessageContractAttribute.WrapperName%2A> и <xref:System.ServiceModel.MessageContractAttribute.WrapperNamespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="ec13d-154">To control the name and the namespace of the wrapper element, use the <xref:System.ServiceModel.MessageContractAttribute.WrapperName%2A> and <xref:System.ServiceModel.MessageContractAttribute.WrapperNamespace%2A> properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec13d-155">Наличие в сообщениях без оболочки более одного раздела тела противоречит WS-I Basic Profile 1.1 и не рекомендуется при разработке новых контрактов сообщений.</span><span class="sxs-lookup"><span data-stu-id="ec13d-155">Having more than one message body part in messages that are not wrapped is not compliant with WS-I Basic Profile 1.1 and is not recommended when designing new message contracts.</span></span> <span data-ttu-id="ec13d-156">Тем не менее, в некоторых сценариях взаимодействия может понадобиться иметь несколько разделов тела сообщения без оболочек.</span><span class="sxs-lookup"><span data-stu-id="ec13d-156">However, it may be necessary to have more than one unwrapped message body part in certain specific interoperability scenarios.</span></span> <span data-ttu-id="ec13d-157">Если планируется передавать в теле сообщения более одного блока данных, рекомендуется использовать режим по умолчанию (с оболочкой).</span><span class="sxs-lookup"><span data-stu-id="ec13d-157">If you are going to transmit more than one piece of data in a message body, it is recommended to use the default (wrapped) mode.</span></span> <span data-ttu-id="ec13d-158">Наличие в сообщениях без оболочки нескольких заголовков полностью приемлемо.</span><span class="sxs-lookup"><span data-stu-id="ec13d-158">Having more than one message header in unwrapped messages is completely acceptable.</span></span>  
  
## <a name="using-custom-types-inside-message-contracts"></a><span data-ttu-id="ec13d-159">Использование пользовательских типов внутри контрактов сообщений</span><span class="sxs-lookup"><span data-stu-id="ec13d-159">Using Custom Types Inside Message Contracts</span></span>  
 <span data-ttu-id="ec13d-160">Каждый отдельный заголовок сообщения и раздел тела сообщения сериализуется (превращается в XML) с помощью модуля сериализации, выбранного для контракта службы, где используется сообщение.</span><span class="sxs-lookup"><span data-stu-id="ec13d-160">Each individual message header and message body part is serialized (turned into XML) using the chosen serialization engine for the service contract where the message is used.</span></span> <span data-ttu-id="ec13d-161">Модуль сериализации по умолчанию - `XmlFormatter` - способен обработать любой тип, имеющий контракт данных либо явно (т. е. имеющий атрибут <xref:System.Runtime.Serialization.DataContractAttribute?displayProperty=nameWithType>), либо неявно (являющийся типом-примитивом, имеющий атрибут <xref:System.SerializableAttribute?displayProperty=nameWithType> и т. д.).</span><span class="sxs-lookup"><span data-stu-id="ec13d-161">The default serialization engine, the `XmlFormatter`, can handle any type that has a data contract, either explicitly (by having the <xref:System.Runtime.Serialization.DataContractAttribute?displayProperty=nameWithType>) or implicitly (by being a primitive type, having the <xref:System.SerializableAttribute?displayProperty=nameWithType>, and so on).</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="ec13d-162">[Использование контрактов данных](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="ec13d-162"> [Using Data Contracts](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).</span></span>  
  
 <span data-ttu-id="ec13d-163">В приведенном выше примере типы полей `Operation` и `BankingTransactionData` должны иметь контракт данных, а поле `transactionDate` является сериализуемым, потому что тип <xref:System.DateTime> является примитивом (и как таковой имеет неявный контракт данных).</span><span class="sxs-lookup"><span data-stu-id="ec13d-163">In the preceding example, the `Operation` and `BankingTransactionData` types must have a data contract, and `transactionDate` is serializable because <xref:System.DateTime> is a primitive (and so has an implicit data contract).</span></span>  
  
 <span data-ttu-id="ec13d-164">Тем не менее, можно перейти на другой модуль сериализации - `XmlSerializer`.</span><span class="sxs-lookup"><span data-stu-id="ec13d-164">However, it is possible to switch to a different serialization engine, the `XmlSerializer`.</span></span> <span data-ttu-id="ec13d-165">В случае такого перехода необходимо убедиться, что все типы, используемые для заголовков и разделов тела сообщений, сериализуются с помощью `XmlSerializer`.</span><span class="sxs-lookup"><span data-stu-id="ec13d-165">If you make such a switch, you should ensure that all of the types used for message headers and body parts are serializable using the `XmlSerializer`.</span></span>  
  
## <a name="using-arrays-inside-message-contracts"></a><span data-ttu-id="ec13d-166">Использование массивов внутри контрактов сообщений</span><span class="sxs-lookup"><span data-stu-id="ec13d-166">Using Arrays Inside Message Contracts</span></span>  
 <span data-ttu-id="ec13d-167">В контрактах сообщений можно использовать массивы повторяющихся элементов, причем двумя способами.</span><span class="sxs-lookup"><span data-stu-id="ec13d-167">You can use arrays of repeating elements in message contracts in two ways.</span></span>  
  
 <span data-ttu-id="ec13d-168">Первый способ - использовать атрибут <xref:System.ServiceModel.MessageHeaderAttribute> или <xref:System.ServiceModel.MessageBodyMemberAttribute> непосредственно в массиве.</span><span class="sxs-lookup"><span data-stu-id="ec13d-168">The first is to use a <xref:System.ServiceModel.MessageHeaderAttribute> or a <xref:System.ServiceModel.MessageBodyMemberAttribute> directly on the array.</span></span> <span data-ttu-id="ec13d-169">В этом случае весь массив сериализуется как один элемент (т. е. один заголовок или один раздел тела) с несколькими дочерними элементами.</span><span class="sxs-lookup"><span data-stu-id="ec13d-169">In this case, the entire array is serialized as one element (that is, one header or one body part) with multiple child elements.</span></span> <span data-ttu-id="ec13d-170">Рассмотрим класс в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ec13d-170">Consider the class in the following example.</span></span>  
  
```csharp  
[MessageContract]  
public class BankingDepositLog  
{  
  [MessageHeader] public int numRecords;  
  [MessageHeader] public DepositRecord[] records;  
  [MessageHeader] public int branchID;  
}  
```  
  
 <span data-ttu-id="ec13d-171">В результате формируются заголовки SOAP-сообщения следующего вида.</span><span class="sxs-lookup"><span data-stu-id="ec13d-171">This results in SOAP headers is similar to the following.</span></span>  
  
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
  
 <span data-ttu-id="ec13d-172">Альтернативный вариант - использовать атрибут <xref:System.ServiceModel.MessageHeaderArrayAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ec13d-172">An alternative to this is to use the <xref:System.ServiceModel.MessageHeaderArrayAttribute>.</span></span> <span data-ttu-id="ec13d-173">В этом случае каждый элемент массива сериализуется независимо и, следовательно, каждый элемент массива имеет один заголовок, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="ec13d-173">In this case, each array element is serialized independently and so that each array element has one header, similar to the following.</span></span>  
  
```xml  
<numRecords>3</numRecords>  
<records>Record1</records>  
<records>Record2</records>  
<records>Record3</records>  
<branchID>20643</branchID>  
```  
  
 <span data-ttu-id="ec13d-174">В качестве имени записей массива по умолчанию используется имя члена, к которому применены атрибуты <xref:System.ServiceModel.MessageHeaderArrayAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ec13d-174">The default name for array entries is the name of the member to which the <xref:System.ServiceModel.MessageHeaderArrayAttribute> attributes is applied.</span></span>  
  
 <span data-ttu-id="ec13d-175">Атрибут <xref:System.ServiceModel.MessageHeaderArrayAttribute> наследуется от класса <xref:System.ServiceModel.MessageHeaderAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ec13d-175">The <xref:System.ServiceModel.MessageHeaderArrayAttribute> attribute inherits from the <xref:System.ServiceModel.MessageHeaderAttribute>.</span></span> <span data-ttu-id="ec13d-176">Он имеет тот же набор функций, что и атрибуты, не являющиеся массивами; например, можно задать порядок, имя и пространство имен для массива заголовков таким же образом, каким они задаются для отдельного заголовка.</span><span class="sxs-lookup"><span data-stu-id="ec13d-176">It has the same set of features as the non-array attributes, for example, it is possible to set the order, name, and namespace for an array of headers in the same way you set it for a single header.</span></span> <span data-ttu-id="ec13d-177">При использовании для массива свойство `Order` применяется ко всему массиву.</span><span class="sxs-lookup"><span data-stu-id="ec13d-177">When you use the `Order` property on an array, it applies to the entire array.</span></span>  
  
 <span data-ttu-id="ec13d-178">Атрибут <xref:System.ServiceModel.MessageHeaderArrayAttribute> можно применять только к массивам, но не к коллекциям.</span><span class="sxs-lookup"><span data-stu-id="ec13d-178">You can apply the <xref:System.ServiceModel.MessageHeaderArrayAttribute> only to arrays, not collections.</span></span>  
  
## <a name="using-byte-arrays-in-message-contracts"></a><span data-ttu-id="ec13d-179">Использование байтовых массивов в контрактах сообщений</span><span class="sxs-lookup"><span data-stu-id="ec13d-179">Using Byte Arrays in Message Contracts</span></span>  
 <span data-ttu-id="ec13d-180">При использовании с не являющимися массивами атрибутами (<xref:System.ServiceModel.MessageBodyMemberAttribute> и <xref:System.ServiceModel.MessageHeaderAttribute>) байтовые массивы рассматриваются не как массивы, а как особый тип-примитив, который в итоговом XML-коде представляется данными в кодировке Base64.</span><span class="sxs-lookup"><span data-stu-id="ec13d-180">Byte arrays, when used with the non-array attributes (<xref:System.ServiceModel.MessageBodyMemberAttribute> and <xref:System.ServiceModel.MessageHeaderAttribute>), are not treated as arrays but as a special primitive type represented as Base64-encoded data in the resulting XML.</span></span>  
  
 <span data-ttu-id="ec13d-181">При использовании байтовых массивов с атрибутом-массивом <xref:System.ServiceModel.MessageHeaderArrayAttribute> результаты зависят от используемого сериализатора.</span><span class="sxs-lookup"><span data-stu-id="ec13d-181">When you use byte arrays with the array attribute <xref:System.ServiceModel.MessageHeaderArrayAttribute>, the results depend on the serializer in use.</span></span> <span data-ttu-id="ec13d-182">При использовании сериализатора по умолчанию массив представляется в виде отдельных записей для каждого байта.</span><span class="sxs-lookup"><span data-stu-id="ec13d-182">With the default serializer, the array is represented as an individual entry for each byte.</span></span> <span data-ttu-id="ec13d-183">Если же выбран сериализатор `XmlSerializer` (с помощью атрибута <xref:System.ServiceModel.XmlSerializerFormatAttribute> в контракте службы), байтовые массивы рассматриваются как данные в кодировке Base64 независимо от того, какие атрибуты используются - массивы или нет.</span><span class="sxs-lookup"><span data-stu-id="ec13d-183">However, when the `XmlSerializer` is selected, (using the <xref:System.ServiceModel.XmlSerializerFormatAttribute> on the service contract), byte arrays are treated as Base64 data regardless of whether the array or non-array attributes are used.</span></span>  
  
## <a name="signing-and-encrypting-parts-of-the-message"></a><span data-ttu-id="ec13d-184">Подписывание и шифрование частей сообщения</span><span class="sxs-lookup"><span data-stu-id="ec13d-184">Signing and Encrypting Parts of the Message</span></span>  
 <span data-ttu-id="ec13d-185">В контракте сообщения может быть указано, следует ли снабжать заголовки и/или тело сообщения цифровыми подписями и шифровать.</span><span class="sxs-lookup"><span data-stu-id="ec13d-185">A message contract can indicate whether the headers and/or body of the message should be digitally signed and encrypted.</span></span>  
  
 <span data-ttu-id="ec13d-186">Это можно сделать, задав свойство <xref:System.ServiceModel.MessageContractMemberAttribute.ProtectionLevel%2A?displayProperty=nameWithType> атрибутов <xref:System.ServiceModel.MessageHeaderAttribute> и <xref:System.ServiceModel.MessageBodyMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ec13d-186">This is done by setting the <xref:System.ServiceModel.MessageContractMemberAttribute.ProtectionLevel%2A?displayProperty=nameWithType> property on the <xref:System.ServiceModel.MessageHeaderAttribute> and <xref:System.ServiceModel.MessageBodyMemberAttribute> attributes.</span></span> <span data-ttu-id="ec13d-187">Это свойство является перечислением типа <xref:System.Net.Security.ProtectionLevel?displayProperty=nameWithType> и может принимать значения <xref:System.Net.Security.ProtectionLevel.None> (без шифрования или подписи), <xref:System.Net.Security.ProtectionLevel.Sign> (только цифровая подпись) или <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> (и шифрование, и цифровая подпись).</span><span class="sxs-lookup"><span data-stu-id="ec13d-187">The property is an enumeration of the <xref:System.Net.Security.ProtectionLevel?displayProperty=nameWithType> type and can be set to <xref:System.Net.Security.ProtectionLevel.None> (no encryption or signature), <xref:System.Net.Security.ProtectionLevel.Sign> (digital signature only), or <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> (both encryption and a digital signature).</span></span> <span data-ttu-id="ec13d-188">Значение по умолчанию — <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span><span class="sxs-lookup"><span data-stu-id="ec13d-188">The default is <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span></span>  
  
 <span data-ttu-id="ec13d-189">Чтобы эти функции безопасности работали, необходимо надлежащим образом настроить привязку и расширения функциональности.</span><span class="sxs-lookup"><span data-stu-id="ec13d-189">For these security features to work, you must properly configure the binding and behaviors.</span></span> <span data-ttu-id="ec13d-190">При использовании этих функций безопасности без надлежащей настройки (например, при попытке подписать сообщение без предоставления учетных данных) во время проверки будет вызвано исключение.</span><span class="sxs-lookup"><span data-stu-id="ec13d-190">If you use these security features without the proper configuration (for example, attempting to sign a message without supplying your credentials), an exception is thrown at validation time.</span></span>  
  
 <span data-ttu-id="ec13d-191">Для заголовков сообщений уровень защиты определяется отдельно для каждого заголовка.</span><span class="sxs-lookup"><span data-stu-id="ec13d-191">For message headers, the protection level is determined individually for each header.</span></span>  
  
 <span data-ttu-id="ec13d-192">Для разделов тела сообщений уровень защиты можно понимать как «минимальный уровень защиты».</span><span class="sxs-lookup"><span data-stu-id="ec13d-192">For message body parts, the protection level can be thought of as the "minimum protection level."</span></span> <span data-ttu-id="ec13d-193">Тело имеет только один уровень защиты, независимо от количества разделов тела.</span><span class="sxs-lookup"><span data-stu-id="ec13d-193">The body has only one protection level, regardless of the number of body parts.</span></span> <span data-ttu-id="ec13d-194">Уровень защиты текста определяется наивысшим из значений свойства <xref:System.ServiceModel.MessageContractMemberAttribute.ProtectionLevel%2A> всех разделов текста.</span><span class="sxs-lookup"><span data-stu-id="ec13d-194">The protection level of the body is determined by the highest <xref:System.ServiceModel.MessageContractMemberAttribute.ProtectionLevel%2A> property setting of all the body parts.</span></span> <span data-ttu-id="ec13d-195">Тем не менее для каждого раздела тела сообщения следует задавать фактически необходимый минимальный уровень защиты.</span><span class="sxs-lookup"><span data-stu-id="ec13d-195">However, you should set the protection level of each body part to the actual minimum protection level required.</span></span>  
  
 <span data-ttu-id="ec13d-196">Рассмотрим класс в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="ec13d-196">Consider the class in the following code example.</span></span>  
  
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
  
 <span data-ttu-id="ec13d-197">В этом примере заголовок `recordID` не защищается, заголовок `patientName`					`signed`, а заголовок `SSN` шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="ec13d-197">In this example, the `recordID` header is not protected, `patientName` is `signed`, and `SSN` is encrypted and signed.</span></span> <span data-ttu-id="ec13d-198">Как минимум к одному разделу тела - `medicalHistory` - применено свойство <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>; следовательно, все тело сообщения шифруется и подписывается, хотя для разделов комментариев и диагноза заданы более низкие уровни защиты.</span><span class="sxs-lookup"><span data-stu-id="ec13d-198">At least one body part, `medicalHistory`, has <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> applied, and thus the entire message body is encrypted and signed, even though the comments and diagnosis body parts specify lower protection levels.</span></span>  
  
## <a name="soap-action"></a><span data-ttu-id="ec13d-199">Свойство Action протокола SOAP</span><span class="sxs-lookup"><span data-stu-id="ec13d-199">SOAP Action</span></span>  
 <span data-ttu-id="ec13d-200">В протоколе SOAP и связанных с ним стандартах веб-служб определено свойство с именем `Action`, которое может присутствовать для каждого оправляемого SOAP-сообщения.</span><span class="sxs-lookup"><span data-stu-id="ec13d-200">SOAP and related Web services standards define a property called `Action` that can be present for every SOAP message sent.</span></span> <span data-ttu-id="ec13d-201">Значение этого свойства определяется свойствами <xref:System.ServiceModel.OperationContractAttribute.Action%2A?displayProperty=nameWithType> и <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A?displayProperty=nameWithType> операции.</span><span class="sxs-lookup"><span data-stu-id="ec13d-201">The operation's <xref:System.ServiceModel.OperationContractAttribute.Action%2A?displayProperty=nameWithType> and <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A?displayProperty=nameWithType> properties control the value of this property.</span></span>  
  
## <a name="soap-header-attributes"></a><span data-ttu-id="ec13d-202">Атрибуты заголовка по протоколу SOAP</span><span class="sxs-lookup"><span data-stu-id="ec13d-202">SOAP Header Attributes</span></span>  
 <span data-ttu-id="ec13d-203">В стандарте протокола SOAP определены следующие атрибуты, которые могут присутствовать в заголовке:</span><span class="sxs-lookup"><span data-stu-id="ec13d-203">The SOAP standard defines the following attributes that may exist on a header:</span></span>  
  
-   <span data-ttu-id="ec13d-204">`Actor/Role` (`Actor` в SOAP 1.1, `Role` в SOAP 1.2)</span><span class="sxs-lookup"><span data-stu-id="ec13d-204">`Actor/Role` (`Actor` in SOAP 1.1, `Role` in SOAP 1.2)</span></span>  
  
-   `MustUnderstand`  
  
-   `Relay`  
  
 <span data-ttu-id="ec13d-205">Атрибут `Actor` или `Role` задает универсальный код ресурса (URI) узла, для которого предназначен данный заголовок.</span><span class="sxs-lookup"><span data-stu-id="ec13d-205">The `Actor` or `Role` attribute specifies the Uniform Resource Identifier (URI) of the node for which a given header is intended.</span></span> <span data-ttu-id="ec13d-206">Атрибут `MustUnderstand` указывает, должен ли обрабатывающий заголовок узел понимать его.</span><span class="sxs-lookup"><span data-stu-id="ec13d-206">The `MustUnderstand` attribute specifies whether the node processing the header must understand it.</span></span> <span data-ttu-id="ec13d-207">Атрибут `Relay` указывает, надо ли передавать заголовок на нижележащие узлы.</span><span class="sxs-lookup"><span data-stu-id="ec13d-207">The `Relay` attribute specifies whether the header is to be relayed to downstream nodes.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="ec13d-208"> не обрабатывает эти атрибуты при наличии входящих сообщений, за исключением атрибута `MustUnderstand` (см. подраздел «Управление версиями контракта сообщения» ниже в этом разделе).</span><span class="sxs-lookup"><span data-stu-id="ec13d-208"> does not perform any processing of these attributes on incoming messages, except for the `MustUnderstand` attribute, as specified in the "Message Contract Versioning" section later in this topic.</span></span> <span data-ttu-id="ec13d-209">Тем не менее, при необходимости эти атрибуты можно считывать и записывать, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="ec13d-209">However, it allows you to read and write these attributes as necessary, as in the following description.</span></span>  
  
 <span data-ttu-id="ec13d-210">При отправке сообщения эти атрибуты по умолчанию не выдаются.</span><span class="sxs-lookup"><span data-stu-id="ec13d-210">When sending a message, these attributes are not emitted by default.</span></span> <span data-ttu-id="ec13d-211">Это поведение можно изменить двумя способами.</span><span class="sxs-lookup"><span data-stu-id="ec13d-211">You can change this in two ways.</span></span> <span data-ttu-id="ec13d-212">Во-первых, можно статически присвоить атрибутам любые требуемые значения, изменяя свойства <xref:System.ServiceModel.MessageHeaderAttribute.Actor%2A?displayProperty=nameWithType>, <xref:System.ServiceModel.MessageHeaderAttribute.MustUnderstand%2A?displayProperty=nameWithType> и <xref:System.ServiceModel.MessageHeaderAttribute.Relay%2A?displayProperty=nameWithType>, как показано в предыдущем примере кода.</span><span class="sxs-lookup"><span data-stu-id="ec13d-212">First, you may statically set the attributes to any desired values by changing the <xref:System.ServiceModel.MessageHeaderAttribute.Actor%2A?displayProperty=nameWithType>, <xref:System.ServiceModel.MessageHeaderAttribute.MustUnderstand%2A?displayProperty=nameWithType>, and <xref:System.ServiceModel.MessageHeaderAttribute.Relay%2A?displayProperty=nameWithType> properties, as shown in the following code example.</span></span> <span data-ttu-id="ec13d-213">(Обратите внимание, что свойства `Role` здесь нет; задание свойства <xref:System.ServiceModel.MessageHeaderAttribute.Actor%2A> порождает атрибут `Role` при использовании протокола SOAP 1.2).</span><span class="sxs-lookup"><span data-stu-id="ec13d-213">(Note that there is no `Role` property; setting the <xref:System.ServiceModel.MessageHeaderAttribute.Actor%2A> property emits the `Role` attribute if you are using SOAP 1.2).</span></span>  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader(Actor="http://auditingservice.contoso.com", MustUnderstand=true)] public bool IsAudited;  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember] public BankingTransactionData theData;  
}  
```  
  
 <span data-ttu-id="ec13d-214">Второй способ управлять этими атрибутами - динамически посредством кода.</span><span class="sxs-lookup"><span data-stu-id="ec13d-214">The second way to control these attributes is dynamically, through code.</span></span> <span data-ttu-id="ec13d-215">Это можно делать, заключая требуемый тип заголовка в тип <xref:System.ServiceModel.MessageHeader%601> (не путайте этот тип с неуниверсальной версией) и используя тип вместе с атрибутом <xref:System.ServiceModel.MessageHeaderAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ec13d-215">You can achieve this by wrapping the desired header type in the <xref:System.ServiceModel.MessageHeader%601> type (be sure not to confuse this type with the non-generic version) and by using the type together with the <xref:System.ServiceModel.MessageHeaderAttribute>.</span></span> <span data-ttu-id="ec13d-216">Затем можно использовать свойства класса <xref:System.ServiceModel.MessageHeader%601> для задания атрибутов протокола SOAP, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="ec13d-216">Then, you can use properties on the <xref:System.ServiceModel.MessageHeader%601> to set the SOAP attributes, as shown in the following code example.</span></span>  
  
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
  
 <span data-ttu-id="ec13d-217">Если используются и динамический, и статический механизмы управления, статические параметры используются по умолчанию, однако могут позднее быть переопределены с помощью динамического механизма, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="ec13d-217">If you use both the dynamic and the static control mechanisms, the static settings are used as a default but can later be overridden by using the dynamic mechanism, as shown in the following code.</span></span>  
  
```csharp  
[MessageHeader(MustUnderstand=true)] public MessageHeader<Person> documentApprover;  
// later on in the code:  
BankingTransaction bt = new BankingTransaction();  
bt.documentApprover = new MessageHeader<Person>();  
bt.documentApprover.MustUnderstand = false; // override the static default of 'true'  
```  
  
 <span data-ttu-id="ec13d-218">Допускается создание повторяющихся заголовков с динамическим управлением атрибутами, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="ec13d-218">Creating repeated headers with dynamic attribute control is allowed, as shown in the following code.</span></span>  
  
```csharp  
[MessageHeaderArray] public MessageHeader<Person> documentApprovers[];  
```  
  
 <span data-ttu-id="ec13d-219">На стороне получения чтение этих атрибутов SOAP возможно только при использовании класса <xref:System.ServiceModel.MessageHeader%601> для заголовка в типе.</span><span class="sxs-lookup"><span data-stu-id="ec13d-219">On the receiving side, reading these SOAP attributes can only be done if the <xref:System.ServiceModel.MessageHeader%601> class is used for the header in the type.</span></span> <span data-ttu-id="ec13d-220">Для определения значений атрибутов полученного сообщения рассмотрите свойства `Actor`, `Relay` или `MustUnderstand` заголовка типа <xref:System.ServiceModel.MessageHeader%601>.</span><span class="sxs-lookup"><span data-stu-id="ec13d-220">Examine the `Actor`, `Relay`, or `MustUnderstand` properties of a header of the <xref:System.ServiceModel.MessageHeader%601> type to discover the attribute settings on the received message.</span></span>  
  
 <span data-ttu-id="ec13d-221">При получении сообщения и затем отправке его обратно круговой путь совершают только значения атрибутов SOAP для заголовков типа <xref:System.ServiceModel.MessageHeader%601>.</span><span class="sxs-lookup"><span data-stu-id="ec13d-221">When a message is received and then sent back, the SOAP attribute settings only go round-trip for headers of the <xref:System.ServiceModel.MessageHeader%601> type.</span></span>  
  
## <a name="order-of-soap-body-parts"></a><span data-ttu-id="ec13d-222">Порядок разделов тела SOAP-сообщения</span><span class="sxs-lookup"><span data-stu-id="ec13d-222">Order of SOAP Body Parts</span></span>  
 <span data-ttu-id="ec13d-223">В некоторых случаях может потребоваться управлять порядком разделов тела сообщения.</span><span class="sxs-lookup"><span data-stu-id="ec13d-223">In some circumstances, you may need to control the order of the body parts.</span></span> <span data-ttu-id="ec13d-224">По умолчанию порядок элементов текста сообщения алфавитный, однако его можно изменить с помощью свойства <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ec13d-224">The order of the body elements is alphabetical by default, but can be controlled by the <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="ec13d-225">Это свойство имеет ту же семантику, что и свойство <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A?displayProperty=nameWithType>, за исключением поведения в сценариях наследования (в контрактах сообщений элементы тела сообщения базовых типов не сортируются перед элементами тела сообщения производных типов).</span><span class="sxs-lookup"><span data-stu-id="ec13d-225">This property has the same semantics as the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A?displayProperty=nameWithType> property, except for the behavior in inheritance scenarios (in message contracts, base type body members are not sorted before the derived type body members).</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="ec13d-226">[Порядок членов данных](../../../../docs/framework/wcf/feature-details/data-member-order.md).</span><span class="sxs-lookup"><span data-stu-id="ec13d-226"> [Data Member Order](../../../../docs/framework/wcf/feature-details/data-member-order.md).</span></span>  
  
 <span data-ttu-id="ec13d-227">В следующем примере элемент `amount` в обычном случае был бы первым, поскольку он идет первым по алфавиту.</span><span class="sxs-lookup"><span data-stu-id="ec13d-227">In the following example, `amount` would normally come first because it is first alphabetically.</span></span> <span data-ttu-id="ec13d-228">Однако в данном случае свойство <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A> помещает его на третью позицию.</span><span class="sxs-lookup"><span data-stu-id="ec13d-228">However, the <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A> property puts it into the third position.</span></span>  
  
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
  
## <a name="message-contract-versioning"></a><span data-ttu-id="ec13d-229">Управление версиями контракта сообщения</span><span class="sxs-lookup"><span data-stu-id="ec13d-229">Message Contract Versioning</span></span>  
 <span data-ttu-id="ec13d-230">Иногда контракты сообщений требуется изменять.</span><span class="sxs-lookup"><span data-stu-id="ec13d-230">Occasionally, you may need to change message contracts.</span></span> <span data-ttu-id="ec13d-231">Например, новая версия приложения может добавлять в сообщение дополнительный заголовок.</span><span class="sxs-lookup"><span data-stu-id="ec13d-231">For example, a new version of your application may add an extra header to a message.</span></span> <span data-ttu-id="ec13d-232">Затем при отправке сообщений от новой версии к старой системе приходится иметь дело с дополнительным заголовком, равно как и с недостающим заголовком при отправке сообщений в обратном направлении.</span><span class="sxs-lookup"><span data-stu-id="ec13d-232">Then, when sending from the new version to the old, the system must deal with an extra header, as well as a missing header when going in the other direction.</span></span>  
  
 <span data-ttu-id="ec13d-233">К управлению версиями заголовков применяются следующие правила.</span><span class="sxs-lookup"><span data-stu-id="ec13d-233">The following rules apply for versioning headers:</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="ec13d-234"> не возражает против недостающих заголовков - соответствующие члены сохраняют свои значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ec13d-234"> does not object to the missing headers—the corresponding members are left at their default values.</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="ec13d-235"> также не учитывает непредвиденные дополнительные заголовки.</span><span class="sxs-lookup"><span data-stu-id="ec13d-235"> also ignores unexpected extra headers.</span></span> <span data-ttu-id="ec13d-236">Единственное исключение из этого правила - когда дополнительный заголовок входящего SOAP-сообщения имеет атрибут `MustUnderstand` со значением `true`. В этом случае вызывается исключение, поскольку не удается обработать заголовок, который должен быть понят.</span><span class="sxs-lookup"><span data-stu-id="ec13d-236">The one exception to this rule is if the extra header has a `MustUnderstand` attribute set to `true` in the incoming SOAP message—in this case, an exception is thrown because a header that must be understood cannot be processed.</span></span>  
  
 <span data-ttu-id="ec13d-237">Аналогичные правила управления версиями применяются к телам сообщений - и недостающие, и дополнительные разделы тела сообщения не учитываются.</span><span class="sxs-lookup"><span data-stu-id="ec13d-237">Message bodies have similar versioning rules—both missing and additional message body parts are ignored.</span></span>  
  
## <a name="inheritance-considerations"></a><span data-ttu-id="ec13d-238">Замечания о наследовании</span><span class="sxs-lookup"><span data-stu-id="ec13d-238">Inheritance Considerations</span></span>  
 <span data-ttu-id="ec13d-239">Тип с контрактом сообщения может наследовать от другого типа при условии, что базовый тип также имеет контракт сообщения.</span><span class="sxs-lookup"><span data-stu-id="ec13d-239">A message contract type can inherit from another type, as long as the base type also has a message contract.</span></span>  
  
 <span data-ttu-id="ec13d-240">При создании сообщения или доступе к сообщению с использованием типа с контрактом сообщения, наследующего от других типов с контрактами сообщений, применяются следующие правила.</span><span class="sxs-lookup"><span data-stu-id="ec13d-240">When creating or accessing a message using a message contract type that inherits from other message contract types, the following rules apply:</span></span>  
  
-   <span data-ttu-id="ec13d-241">Все заголовки сообщения в иерархии наследования собираются вместе и образуют полный набор заголовков для сообщения.</span><span class="sxs-lookup"><span data-stu-id="ec13d-241">All of the message headers in the inheritance hierarchy are collected together to form the full set of headers for the message.</span></span>  
  
-   <span data-ttu-id="ec13d-242">Все разделы тела сообщения в иерархии наследования собираются вместе и образуют полное тело сообщения.</span><span class="sxs-lookup"><span data-stu-id="ec13d-242">All of the message body parts in the inheritance hierarchy are collected together to form the full message body.</span></span> <span data-ttu-id="ec13d-243">Разделы текста сообщения упорядочиваются согласно обычным правилам (по свойству <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A?displayProperty=nameWithType>, а затем по алфавиту), независимо от их места в иерархии наследования.</span><span class="sxs-lookup"><span data-stu-id="ec13d-243">The body parts are ordered according to the usual ordering rules (by <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A?displayProperty=nameWithType> property and then alphabetical), with no relevance to their place in the inheritance hierarchy.</span></span> <span data-ttu-id="ec13d-244">Использовать наследование контрактов сообщения в случаях, где разделы тела сообщения имеются на нескольких уровнях дерева наследования, крайне нежелательно.</span><span class="sxs-lookup"><span data-stu-id="ec13d-244">Using message contract inheritance where message body parts occur at multiple levels of the inheritance tree is strongly discouraged.</span></span> <span data-ttu-id="ec13d-245">Если базовый класс и производный класс определяют заголовок или раздел тела сообщения с одинаковым именем, для хранения значения этого заголовка или раздела тела используется член «самого базового» класса.</span><span class="sxs-lookup"><span data-stu-id="ec13d-245">If a base class and a derived class define a header or a body part with the same name, the member from the base-most class is used to store the value of that header or body part.</span></span>  
  
 <span data-ttu-id="ec13d-246">Рассмотрим классы в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="ec13d-246">Consider the classes in the following code example.</span></span>  
  
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
  
 <span data-ttu-id="ec13d-247">Класс `PatientRecord` описывает сообщение с одним заголовком с именем `ID`.</span><span class="sxs-lookup"><span data-stu-id="ec13d-247">The `PatientRecord` class describes a message with one header called `ID`.</span></span> <span data-ttu-id="ec13d-248">Этот заголовок соответствует члену `personID`, а не члену `patientID`, поскольку выбирается самый базовый член.</span><span class="sxs-lookup"><span data-stu-id="ec13d-248">The header corresponds to the `personID` and not the `patientID` member, because the base-most member is chosen.</span></span> <span data-ttu-id="ec13d-249">Следовательно, поле `patientID` в этом случае бесполезно.</span><span class="sxs-lookup"><span data-stu-id="ec13d-249">Thus, the `patientID` field is useless in this case.</span></span> <span data-ttu-id="ec13d-250">Тело сообщения содержит элемент `diagnosis`, за которым следует элемент `patientName` (алфавитный порядок).</span><span class="sxs-lookup"><span data-stu-id="ec13d-250">The body of the message contains the `diagnosis` element followed by the `patientName` element, because that is the alphabetical order.</span></span> <span data-ttu-id="ec13d-251">Обратите внимание, что в этом примере показана крайне нежелательная схема: и в базовом, и в производном контракте сообщения имеются разделы тела сообщения.</span><span class="sxs-lookup"><span data-stu-id="ec13d-251">Notice that the example shows a pattern that is strongly discouraged: both the base and the derived message contracts have message body parts.</span></span>  
  
## <a name="wsdl-considerations"></a><span data-ttu-id="ec13d-252">Замечания о WSDL</span><span class="sxs-lookup"><span data-stu-id="ec13d-252">WSDL Considerations</span></span>  
 <span data-ttu-id="ec13d-253">При создании контракта на языке WSDL из службы, в которой используются контракты сообщений, важно помнить, что в полученном WSDL-коде отражаются не все функции контракта сообщения.</span><span class="sxs-lookup"><span data-stu-id="ec13d-253">When generating a Web Services Description Language (WSDL) contract from a service that uses message contracts, it is important to remember that not all message contract features are reflected in the resulting WSDL.</span></span> <span data-ttu-id="ec13d-254">Необходимо учитывать следующее.</span><span class="sxs-lookup"><span data-stu-id="ec13d-254">Consider the following points:</span></span>  
  
-   <span data-ttu-id="ec13d-255">На языке WSDL нельзя выразить понятие массива заголовков.</span><span class="sxs-lookup"><span data-stu-id="ec13d-255">WSDL cannot express the concept of an array of headers.</span></span> <span data-ttu-id="ec13d-256">При создании сообщений с массивом заголовков с использованием атрибута <xref:System.ServiceModel.MessageHeaderArrayAttribute> в полученном WSDL-коде вместо массива отражается только один заголовок.</span><span class="sxs-lookup"><span data-stu-id="ec13d-256">When creating messages with an array of headers using the <xref:System.ServiceModel.MessageHeaderArrayAttribute>, the resulting WSDL reflects only one header instead of the array.</span></span>  
  
-   <span data-ttu-id="ec13d-257">Полученный WSDL-документ может не отражать некоторую информацию об уровне защиты.</span><span class="sxs-lookup"><span data-stu-id="ec13d-257">The resulting WSDL document may not reflect some protection-level information.</span></span>  
  
-   <span data-ttu-id="ec13d-258">Имя типа сообщения, сформированного в WSDL-коде, совпадает с именем класса типа контракта сообщения.</span><span class="sxs-lookup"><span data-stu-id="ec13d-258">The message type generated in the WSDL has the same name as the class name of the message contract type.</span></span>  
  
-   <span data-ttu-id="ec13d-259">При использовании в нескольких операциях одного и того же контракта сообщения в WSDL-документе формируется несколько типов сообщений.</span><span class="sxs-lookup"><span data-stu-id="ec13d-259">When using the same message contract in multiple operations, multiple message types are generated in the WSDL document.</span></span> <span data-ttu-id="ec13d-260">Имена делаются уникальными путем добавления номеров "2", "3" и т. д. для использования в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="ec13d-260">The names are made unique by adding the numbers "2", "3", and so on, for subsequent uses.</span></span> <span data-ttu-id="ec13d-261">При обратном импорте WSDL-кода создается несколько типов с контрактами сообщений, идентичных за исключением имен.</span><span class="sxs-lookup"><span data-stu-id="ec13d-261">When importing back the WSDL, multiple message contract types are created and are identical except for their names.</span></span>  
  
## <a name="soap-encoding-considerations"></a><span data-ttu-id="ec13d-262">Замечания о кодировании SOAP</span><span class="sxs-lookup"><span data-stu-id="ec13d-262">SOAP Encoding Considerations</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="ec13d-263"> позволяет использовать устаревший стиль кодирования SOAP в XML, что, однако, не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="ec13d-263"> allows you to use the legacy SOAP encoding style of XML, however, its use is not recommended.</span></span> <span data-ttu-id="ec13d-264">При использовании этого стиля (путем присвоения значения `Use` свойству `Encoded` атрибута <xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=nameWithType>, примененного к контракту службы) следует принять во внимание также следующее.</span><span class="sxs-lookup"><span data-stu-id="ec13d-264">When using this style (by setting the `Use` property to `Encoded` on the <xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=nameWithType> applied to the service contract), the following additional considerations apply:</span></span>  
  
-   <span data-ttu-id="ec13d-265">Заголовки сообщений не поддерживаются; это значит, что атрибут <xref:System.ServiceModel.MessageHeaderAttribute> и атрибут-массив <xref:System.ServiceModel.MessageHeaderArrayAttribute> несовместимы с кодированием SOAP.</span><span class="sxs-lookup"><span data-stu-id="ec13d-265">The message headers are not supported; this means that the attribute <xref:System.ServiceModel.MessageHeaderAttribute> and the array attribute <xref:System.ServiceModel.MessageHeaderArrayAttribute> are incompatible with SOAP encoding.</span></span>  
  
-   <span data-ttu-id="ec13d-266">Если контракт сообщения не заключен в оболочку, т. е. если свойство <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> имеет значение `false`, контракт сообщения может иметь только один раздел тела сообщения.</span><span class="sxs-lookup"><span data-stu-id="ec13d-266">If the message contract is not wrapped, that is, if the property <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> is set to `false`, the message contract can have only one body part.</span></span>  
  
-   <span data-ttu-id="ec13d-267">Имя элемента-оболочки для контракта сообщения запроса должно совпадать с именем операции.</span><span class="sxs-lookup"><span data-stu-id="ec13d-267">The name of the wrapper element for the request message contract must match the operation name.</span></span> <span data-ttu-id="ec13d-268">Для этого используется свойство `WrapperName` контракта сообщения.</span><span class="sxs-lookup"><span data-stu-id="ec13d-268">Use the `WrapperName` property of the message contract for this.</span></span>  
  
-   <span data-ttu-id="ec13d-269">Имя элемента-оболочки для контракта ответного сообщения должно представлять собой имя операции, снабженное суффиксом "Response".</span><span class="sxs-lookup"><span data-stu-id="ec13d-269">The name of the wrapper element for the response message contract must be the same as the name of the operation suffixed by 'Response'.</span></span> <span data-ttu-id="ec13d-270">Для этого используется свойство <xref:System.ServiceModel.MessageContractAttribute.WrapperName%2A> контракта сообщения.</span><span class="sxs-lookup"><span data-stu-id="ec13d-270">Use the <xref:System.ServiceModel.MessageContractAttribute.WrapperName%2A> property of the message contract for this.</span></span>  
  
-   <span data-ttu-id="ec13d-271">Кодирование SOAP сохраняет ссылки на объекты.</span><span class="sxs-lookup"><span data-stu-id="ec13d-271">SOAP encoding preserves object references.</span></span> <span data-ttu-id="ec13d-272">Например, рассмотрим следующий код.</span><span class="sxs-lookup"><span data-stu-id="ec13d-272">For example, consider the following code.</span></span>  
  
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
  
 <span data-ttu-id="ec13d-273">После сериализации сообщения с использованием кодирования SOAP элементы `changedFrom` и `changedTo` не содержат собственных копий `p`, а вместо этого указывают на копию внутри элемента `changedBy`.</span><span class="sxs-lookup"><span data-stu-id="ec13d-273">After serializing the message using SOAP encoding, `changedFrom` and `changedTo` do not contain their own copies of `p`, but instead point to the copy inside the `changedBy` element.</span></span>  
  
## <a name="performance-considerations"></a><span data-ttu-id="ec13d-274">Особенности производительности</span><span class="sxs-lookup"><span data-stu-id="ec13d-274">Performance Considerations</span></span>  
 <span data-ttu-id="ec13d-275">Каждый заголовок сообщения и раздел тела сообщения сериализуется независимо от других.</span><span class="sxs-lookup"><span data-stu-id="ec13d-275">Every message header and message body part is serialized independently of the others.</span></span> <span data-ttu-id="ec13d-276">Следовательно, одни те же пространства имен могут повторно объявляться для каждого заголовка и раздела тела.</span><span class="sxs-lookup"><span data-stu-id="ec13d-276">Therefore, the same namespaces can be declared again for each header and body part.</span></span> <span data-ttu-id="ec13d-277">Для улучшения производительности, особенно в части размера сообщения на линии связи, множественные заголовки и разделы тела сообщения следует объединять в один заголовок или раздел тела.</span><span class="sxs-lookup"><span data-stu-id="ec13d-277">To improve performance, especially in terms of the size of the message on the wire, consolidate multiple headers and body parts into a single header or body part.</span></span> <span data-ttu-id="ec13d-278">Например, вместо следующего кода</span><span class="sxs-lookup"><span data-stu-id="ec13d-278">For example, instead of the following code:</span></span>  
  
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
  
 <span data-ttu-id="ec13d-279">используйте такой код:</span><span class="sxs-lookup"><span data-stu-id="ec13d-279">Use this code.</span></span>  
  
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
  
### <a name="event-based-asynchronous-and-message-contracts"></a><span data-ttu-id="ec13d-280">Асинхронная модель на основе событий и контракты сообщений</span><span class="sxs-lookup"><span data-stu-id="ec13d-280">Event-based Asynchronous and Message Contracts</span></span>  
 <span data-ttu-id="ec13d-281">Согласно правилам разработки для асинхронной модели на основе событий, если возвращается несколько значений, одно значение возвращается как свойство `Result`, а остальные возвращаются как свойства объекта <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="ec13d-281">The design guidelines for the event-based asynchronous model state that if more than one value is returned, one value is returned as the `Result` property and the others are returned as properties on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="ec13d-282">Одним из результатов этого является то, что если клиент импортирует метаданные с использованием параметров асинхронных команд на основе событий и операция возвращает более одного значения, объект <xref:System.EventArgs> по умолчанию возвращает одно значение как свойство `Result`, а остальные являются свойствами объекта <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="ec13d-282">One result of this is that if a client imports metadata using the event-based asynchronous command options and the operation returns more than one value, the default <xref:System.EventArgs> object returns one value as the `Result` property and the remainder are properties of the <xref:System.EventArgs> object.</span></span>  
  
 <span data-ttu-id="ec13d-283">Если требуется получать объект сообщения как свойство `Result`, чтобы возвращаемые значения были свойствами этого объекта, используйте параметр команды `/messageContract`.</span><span class="sxs-lookup"><span data-stu-id="ec13d-283">If you want to receive the message object as the `Result` property and have the returned values as properties on that object, use the `/messageContract` command option.</span></span> <span data-ttu-id="ec13d-284">При этом формируется сигнатура, которая возвращает ответное сообщение как свойство `Result` объекта <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="ec13d-284">This generates a signature that returns the response message as the `Result` property on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="ec13d-285">Все внутренние возвращаемые значения тогда будут свойствами объекта ответного сообщения.</span><span class="sxs-lookup"><span data-stu-id="ec13d-285">All internal return values are then properties of the response message object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec13d-286">См. также</span><span class="sxs-lookup"><span data-stu-id="ec13d-286">See Also</span></span>  
 [<span data-ttu-id="ec13d-287">Использование контрактов данных</span><span class="sxs-lookup"><span data-stu-id="ec13d-287">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [<span data-ttu-id="ec13d-288">Проектирование и реализация служб</span><span class="sxs-lookup"><span data-stu-id="ec13d-288">Designing and Implementing Services</span></span>](../../../../docs/framework/wcf/designing-and-implementing-services.md)
