---
title: "Как устанавливать свойства ProtectionLevel | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "свойство ProtectionLevel"
  - "WCF, безопасность"
ms.assetid: 3d4e8f80-0f9e-4a26-9899-beb6584e78df
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Как устанавливать свойства ProtectionLevel
Уровень защиты можно задать, применив соответствующий атрибут и задав свойство.Вы можете установить защиту на уровне службы таким образом, чтобы она влияла на все части каждого сообщения, либо задать защиту на каждом уровне отдельно — от методов до частей сообщения.[!INCLUDE[crabout](../../../includes/crabout-md.md)] свойствах `ProtectionLevel` см. в разделе [Основные сведения об уровне защиты](../../../docs/framework/wcf/understanding-protection-level.md).  
  
> [!NOTE]
>  Уровни защиты можно задавать только в коде, а не в конфигурации.  
  
### Подписание всех сообщений для службы  
  
1.  Создайте интерфейс для службы.  
  
2.  Примените к службе атрибут <xref:System.ServiceModel.ServiceContractAttribute> и задайте значение <xref:System.Net.Security.ProtectionLevel> для свойства <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A>, как показано в следующем примере кода \(уровень по умолчанию — <xref:System.Net.Security.ProtectionLevel>\).  
  
     [!code-csharp[C_ProtectionLevel#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#1)]
     [!code-vb[C_ProtectionLevel#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#1)]  
  
### Подписание всех частей сообщения для операции  
  
1.  Создайте интерфейс для службы и примените к нему атрибут <xref:System.ServiceModel.ServiceContractAttribute>.  
  
2.  Добавьте в интерфейс объявление метода.  
  
3.  Примените к методу атрибут <xref:System.ServiceModel.OperationContractAttribute> и задайте значение <xref:System.Net.Security.ProtectionLevel> для свойства <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A>, как показано в следующем примере кода.  
  
     [!code-csharp[C_ProtectionLevel#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#2)]
     [!code-vb[C_ProtectionLevel#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#2)]  
  
## Защита сообщений об ошибках  
 Создаваемые в службе исключения можно отправить клиенту в виде ошибок SOAP.[!INCLUDE[crabout](../../../includes/crabout-md.md)] о создании строго типизированных ошибок см. в разделах [Задание и обработка сбоев в контрактах и службах](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md) и [Практическое руководство. Объявление сбоев в контрактах служб](../../../docs/framework/wcf/how-to-declare-faults-in-service-contracts.md).  
  
#### Защита сообщения об ошибке  
  
1.  Создайте тип, представляющий сообщение об ошибке.В следующем примере описано создание класса, именуемого `MathFault`, с двумя полями.  
  
2.  Примените к типу атрибут <xref:System.Runtime.Serialization.DataContractAttribute>, а к каждому полю, которое должно быть сериализовано, — атрибут <xref:System.Runtime.Serialization.DataMemberAttribute>, как показано в следующем примере кода.  
  
     [!code-csharp[C_ProtectionLevel#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#3)]
     [!code-vb[C_ProtectionLevel#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#3)]  
  
3.  Примените атрибут <xref:System.ServiceModel.FaultContractAttribute> к методу, который будет возвращать ошибку, и настройте параметр `detailType` к типу класса ошибки в интерфейсе, который будет возвращать ошибку,  
  
4.  Задайте для свойства <xref:System.ServiceModel.FaultContractAttribute.ProtectionLevel%2A> значение <xref:System.Net.Security.ProtectionLevel> в конструкторе, как показано в следующем примере кода.  
  
     [!code-csharp[C_ProtectionLevel#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#4)]
     [!code-vb[C_ProtectionLevel#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#4)]  
  
## Защита частей сообщения  
 Для защиты частей сообщения следует использовать контракт сообщения.[!INCLUDE[crabout](../../../includes/crabout-md.md)] контрактах сообщения, см. в разделе [Использование контрактов сообщений](../../../docs/framework/wcf/feature-details/using-message-contracts.md).  
  
#### Защита тела сообщения  
  
1.  Создайте тип, представляющий сообщение.В следующем примере описано создание класса `Company` двумя полями: `CompanyName` и `CompanyID`.  
  
2.  Примените атрибут <xref:System.ServiceModel.MessageContractAttribute> к классу и задайте значение <xref:System.Net.Security.ProtectionLevel> для свойства <xref:System.ServiceModel.MessageContractAttribute.ProtectionLevel%2A>.  
  
3.  Примените атрибут <xref:System.ServiceModel.MessageHeaderAttribute> к полю, которое будет выражено как заголовок сообщения, и задайте значение <xref:System.Net.Security.ProtectionLevel> для свойства `ProtectionLevel`.  
  
4.  Примените атрибут <xref:System.ServiceModel.MessageBodyMemberAttribute> к любому полю, которое будет выражено как часть текста сообщения, и задайте значение `ProtectionLevel` для свойства <xref:System.Net.Security.ProtectionLevel>, как показано в следующем примере.  
  
     [!code-csharp[C_ProtectionLevel#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#5)]
     [!code-vb[C_ProtectionLevel#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#5)]  
  
## Пример  
 В следующем примере демонстрируется, как задать свойство `ProtectionLevel` нескольких классов атрибута в разных местах службы.  
  
 [!code-csharp[C_ProtectionLevel#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#6)]
 [!code-vb[C_ProtectionLevel#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#6)]  
  
## Компиляция кода  
 В следующем примере кода показаны пространства имен, необходимые для компиляции примера кода.  
  
 [!code-csharp[C_ProtectionLevel#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#0)]
 [!code-vb[C_ProtectionLevel#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#0)]  
  
## См. также  
 <xref:System.ServiceModel.ServiceContractAttribute>   
 <xref:System.ServiceModel.OperationContractAttribute>   
 <xref:System.ServiceModel.FaultContractAttribute>   
 <xref:System.ServiceModel.MessageContractAttribute>   
 <xref:System.ServiceModel.MessageBodyMemberAttribute>   
 [Основные сведения об уровне защиты](../../../docs/framework/wcf/understanding-protection-level.md)