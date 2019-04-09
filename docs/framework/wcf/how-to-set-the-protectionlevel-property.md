---
title: Практическое руководство. Установка свойства ProtectionLevel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, security
- ProtectionLevel property
ms.assetid: 3d4e8f80-0f9e-4a26-9899-beb6584e78df
ms.openlocfilehash: ce9fc8549218db5a1446026421f1a7ba1e5a23aa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089852"
---
# <a name="how-to-set-the-protectionlevel-property"></a><span data-ttu-id="85347-102">Практическое руководство. Установка свойства ProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="85347-102">How to: Set the ProtectionLevel Property</span></span>
<span data-ttu-id="85347-103">Уровень защиты можно задать, применив соответствующий атрибут и задав свойство.</span><span class="sxs-lookup"><span data-stu-id="85347-103">You can set the protection level by applying an appropriate attribute and setting the property.</span></span> <span data-ttu-id="85347-104">Защиту на уровне службы можно задать таким образом, чтобы она влияла на все части каждого сообщения, можно также задать защиту на более детализированных уровнях - от методов до частей сообщения.</span><span class="sxs-lookup"><span data-stu-id="85347-104">You can set protection at the service level to affect all parts of every message, or you can set protection at increasingly granular levels, from methods to message parts.</span></span> <span data-ttu-id="85347-105">Дополнительные сведения о `ProtectionLevel` свойство, см. в разделе [уровень защиты понимание](../../../docs/framework/wcf/understanding-protection-level.md).</span><span class="sxs-lookup"><span data-stu-id="85347-105">For more information about the `ProtectionLevel` property, see [Understanding Protection Level](../../../docs/framework/wcf/understanding-protection-level.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85347-106">Уровни защиты можно задавать только в коде, а не в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="85347-106">You can set protection levels only in code, not in configuration.</span></span>  
  
### <a name="to-sign-all-messages-for-a-service"></a><span data-ttu-id="85347-107">Подписание всех сообщений для службы</span><span class="sxs-lookup"><span data-stu-id="85347-107">To sign all messages for a service</span></span>  
  
1.  <span data-ttu-id="85347-108">Создайте интерфейс для службы.</span><span class="sxs-lookup"><span data-stu-id="85347-108">Create an interface for the service.</span></span>  
  
2.  <span data-ttu-id="85347-109">Примените к службе атрибут <xref:System.ServiceModel.ServiceContractAttribute> и задайте значение <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> для свойства <xref:System.Net.Security.ProtectionLevel.Sign>, как показано в следующем примере кода (уровень по умолчанию - <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>).</span><span class="sxs-lookup"><span data-stu-id="85347-109">Apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the service and set the <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> property to <xref:System.Net.Security.ProtectionLevel.Sign>, as shown in the following code (the default level is <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>).</span></span>  
  
     [!code-csharp[C_ProtectionLevel#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#1)]
     [!code-vb[C_ProtectionLevel#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#1)]  
  
### <a name="to-sign-all-message-parts-for-an-operation"></a><span data-ttu-id="85347-110">Подписание всех частей сообщения для операции</span><span class="sxs-lookup"><span data-stu-id="85347-110">To sign all message parts for an operation</span></span>  
  
1.  <span data-ttu-id="85347-111">Создайте интерфейс для службы и примените к нему атрибут <xref:System.ServiceModel.ServiceContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="85347-111">Create an interface for the service and apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the interface.</span></span>  
  
2.  <span data-ttu-id="85347-112">Добавьте в интерфейс объявление метода.</span><span class="sxs-lookup"><span data-stu-id="85347-112">Add a method declaration to the interface.</span></span>  
  
3.  <span data-ttu-id="85347-113">Примените к методу атрибут <xref:System.ServiceModel.OperationContractAttribute> и задайте значение <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> для свойства <xref:System.Net.Security.ProtectionLevel.Sign>, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="85347-113">Apply the <xref:System.ServiceModel.OperationContractAttribute> attribute to the method, and set the <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> property to <xref:System.Net.Security.ProtectionLevel.Sign>, as shown in the following code.</span></span>  
  
     [!code-csharp[C_ProtectionLevel#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#2)]
     [!code-vb[C_ProtectionLevel#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#2)]  
  
## <a name="protecting-fault-messages"></a><span data-ttu-id="85347-114">Защита сообщений об ошибках</span><span class="sxs-lookup"><span data-stu-id="85347-114">Protecting Fault Messages</span></span>  
 <span data-ttu-id="85347-115">Создаваемые в службе исключения можно отправить клиенту в виде ошибок SOAP.</span><span class="sxs-lookup"><span data-stu-id="85347-115">Exceptions that are thrown on a service can be sent to a client as SOAP faults.</span></span> <span data-ttu-id="85347-116">Дополнительные сведения о создании строго типизированных ошибок, см. в разделе [задание и обработка сбоев в контрактах и службах](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md) и [как: Объявление сбоев в контрактах служб](../../../docs/framework/wcf/how-to-declare-faults-in-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="85347-116">For more information about creating strongly typed faults, see [Specifying and Handling Faults in Contracts and Services](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md) and [How to: Declare Faults in Service Contracts](../../../docs/framework/wcf/how-to-declare-faults-in-service-contracts.md).</span></span>  
  
#### <a name="to-protect-a-fault-message"></a><span data-ttu-id="85347-117">Защита сообщения об ошибке</span><span class="sxs-lookup"><span data-stu-id="85347-117">To protect a fault message</span></span>  
  
1.  <span data-ttu-id="85347-118">Создайте тип, представляющий сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="85347-118">Create a type that represents the fault message.</span></span> <span data-ttu-id="85347-119">В следующем примере описано создание класса, именуемого `MathFault`, с двумя полями.</span><span class="sxs-lookup"><span data-stu-id="85347-119">The following example creates a class named `MathFault` with two fields.</span></span>  
  
2.  <span data-ttu-id="85347-120">Примените к типу атрибут <xref:System.Runtime.Serialization.DataContractAttribute>, а к каждому полю, которое должно быть сериализовано, - атрибут <xref:System.Runtime.Serialization.DataMemberAttribute>, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="85347-120">Apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the type and a <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to each field that should be serialized, as shown in the following code.</span></span>  
  
     [!code-csharp[C_ProtectionLevel#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#3)]
     [!code-vb[C_ProtectionLevel#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#3)]  
  
3.  <span data-ttu-id="85347-121">Примените атрибут <xref:System.ServiceModel.FaultContractAttribute> к методу, который будет возвращать ошибку, и настройте параметр `detailType` к типу класса ошибки в интерфейсе, который будет возвращать ошибку,</span><span class="sxs-lookup"><span data-stu-id="85347-121">In the interface that will return the fault, apply the <xref:System.ServiceModel.FaultContractAttribute> attribute to the method that will return the fault and set the `detailType` parameter to the type of the fault class.</span></span>  
  
4.  <span data-ttu-id="85347-122">Задайте для свойства <xref:System.ServiceModel.FaultContractAttribute.ProtectionLevel%2A> значение <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> в конструкторе, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="85347-122">Also in the constructor, set the <xref:System.ServiceModel.FaultContractAttribute.ProtectionLevel%2A> property to <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>, as shown in the following code.</span></span>  
  
     [!code-csharp[C_ProtectionLevel#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#4)]
     [!code-vb[C_ProtectionLevel#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#4)]  
  
## <a name="protecting-message-parts"></a><span data-ttu-id="85347-123">Защита частей сообщения</span><span class="sxs-lookup"><span data-stu-id="85347-123">Protecting Message Parts</span></span>  
 <span data-ttu-id="85347-124">Для защиты частей сообщения следует использовать контракт сообщения.</span><span class="sxs-lookup"><span data-stu-id="85347-124">Use a message contract to protect parts of a message.</span></span> <span data-ttu-id="85347-125">Дополнительные сведения о контрактах сообщений см. в разделе [Using Message Contracts](../../../docs/framework/wcf/feature-details/using-message-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="85347-125">For more information about message contracts, see [Using Message Contracts](../../../docs/framework/wcf/feature-details/using-message-contracts.md).</span></span>  
  
#### <a name="to-protect-a-message-body"></a><span data-ttu-id="85347-126">Защита тела сообщения</span><span class="sxs-lookup"><span data-stu-id="85347-126">To protect a message body</span></span>  
  
1.  <span data-ttu-id="85347-127">Создайте тип, представляющий сообщение.</span><span class="sxs-lookup"><span data-stu-id="85347-127">Create a type that represents the message.</span></span> <span data-ttu-id="85347-128">В следующем примере описано создание класса `Company` двумя полями: `CompanyName` и `CompanyID`.</span><span class="sxs-lookup"><span data-stu-id="85347-128">The following example creates a `Company` class with two fields, `CompanyName` and `CompanyID`.</span></span>  
  
2.  <span data-ttu-id="85347-129">Примените атрибут <xref:System.ServiceModel.MessageContractAttribute> к классу и задайте значение <xref:System.ServiceModel.MessageContractAttribute.ProtectionLevel%2A> для свойства <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span><span class="sxs-lookup"><span data-stu-id="85347-129">Apply the <xref:System.ServiceModel.MessageContractAttribute> attribute to the class and set the <xref:System.ServiceModel.MessageContractAttribute.ProtectionLevel%2A> property to <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span></span>  
  
3.  <span data-ttu-id="85347-130">Примените атрибут <xref:System.ServiceModel.MessageHeaderAttribute> к полю, которое будет выражено как заголовок сообщения, и задайте значение `ProtectionLevel` для свойства <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span><span class="sxs-lookup"><span data-stu-id="85347-130">Apply the <xref:System.ServiceModel.MessageHeaderAttribute> attribute to a field that will be expressed as a message header and set the `ProtectionLevel` property to <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span></span>  
  
4.  <span data-ttu-id="85347-131">Применить <xref:System.ServiceModel.MessageBodyMemberAttribute> к любому полю, которое будет выражено как часть текста сообщения и задайте `ProtectionLevel` свойства <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="85347-131">Apply the <xref:System.ServiceModel.MessageBodyMemberAttribute> to any field that will be expressed as part of the message body, and set the `ProtectionLevel` property to <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>, as shown in the following example.</span></span>  
  
     [!code-csharp[C_ProtectionLevel#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#5)]
     [!code-vb[C_ProtectionLevel#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="85347-132">Пример</span><span class="sxs-lookup"><span data-stu-id="85347-132">Example</span></span>  
 <span data-ttu-id="85347-133">В следующем примере демонстрируется, как задать свойство `ProtectionLevel` нескольких классов атрибута в разных местах службы.</span><span class="sxs-lookup"><span data-stu-id="85347-133">The following example sets the `ProtectionLevel` property of several attribute classes at various places in a service.</span></span>  
  
 [!code-csharp[C_ProtectionLevel#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#6)]
 [!code-vb[C_ProtectionLevel#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#6)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="85347-134">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="85347-134">Compiling the Code</span></span>  
 <span data-ttu-id="85347-135">В следующем примере кода показаны пространства имен, необходимые для компиляции примера кода.</span><span class="sxs-lookup"><span data-stu-id="85347-135">The following code shows the namespaces required to compile the example code.</span></span>  
  
 [!code-csharp[C_ProtectionLevel#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#0)]
 [!code-vb[C_ProtectionLevel#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="85347-136">См. также</span><span class="sxs-lookup"><span data-stu-id="85347-136">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- <xref:System.ServiceModel.FaultContractAttribute>
- <xref:System.ServiceModel.MessageContractAttribute>
- <xref:System.ServiceModel.MessageBodyMemberAttribute>
- [<span data-ttu-id="85347-137">Основные сведения об уровне защиты</span><span class="sxs-lookup"><span data-stu-id="85347-137">Understanding Protection Level</span></span>](../../../docs/framework/wcf/understanding-protection-level.md)
