---
title: "Как асинхронно реализовывать операции службы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4e5d2ea5-d8f8-4712-bd18-ea3c5461702c
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Как асинхронно реализовывать операции службы
В приложениях [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] операция службы может быть реализована асинхронно или синхронно без жесткого задания способа вызова клиентом.Например, асинхронные операции службы могут вызываться синхронно или синхронные операции службы могут вызываться асинхронно.Пример, в котором показана реализация асинхронной операции в службе, см. в разделе [Как асинхронно вызывать операции службы](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).[!INCLUDE[crabout](../../../includes/crabout-md.md)] о синхронных и асинхронных операциях см. в разделе [Создание контрактов служб](../../../docs/framework/wcf/designing-service-contracts.md) и [Синхронные и асинхронные операции](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).В этом разделе описывается базовая структура асинхронной операции службы, код не завершен.Полный образец стороны службы и клиента приведен в разделе [Asynchronous](http://msdn.microsoft.com/ru-ru/833db946-f511-4f64-a26f-2759a11217c7).  
  
### Асинхронная реализация операции службы  
  
1.  В контракте службы объявите пару асинхронных методов в соответствии с рекомендациями по асинхронной разработке для платформы .NET.Метод `Begin` принимает параметр, объект обратного вызова и объект состояния, а возвращает <xref:System.IAsyncResult?displayProperty=fullName>; соответствующий метод `End` принимает <xref:System.IAsyncResult?displayProperty=fullName> и возвращает возвращаемое значение.Дополнительные сведения об асинхронных вызовах см. в разделе [Асинхронные шаблоны разработки](http://go.microsoft.com/fwlink/?LinkId=248221).  
  
2.  Пометьте метод `Begin` пары асинхронных методов атрибутом <xref:System.ServiceModel.OperationContractAttribute?displayProperty=fullName> и задайте для свойства <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A?displayProperty=fullName> значение `true`.Например, приведенный ниже код выполняет шаги 1 и 2.  
  
     [!code-csharp[C_SyncAsyncClient#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#6)]
     [!code-vb[C_SyncAsyncClient#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#6)]  
  
3.  Реализуйте пару методов `Begin/End` в классе своей службы в соответствии с рекомендациями по асинхронной разработке.Например, в следующем примере кода показана реализация, в которой строка записывается в консоль как в части `Begin`, так и в части `End` асинхронной операции службы, и возвращаемое значение операции `End` возвращается клиенту.Полный пример кода см. в подразделе "Пример".  
  
     [!code-csharp[C_SyncAsyncClient#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#3)]
     [!code-vb[C_SyncAsyncClient#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#3)]  
  
## Пример  
 В следующих примерах кода показаны:  
  
1.  Интерфейс контракта службы с:  
  
    1.  Синхронной операцией `SampleMethod`.  
  
    2.  Асинхронной операцией `BeginSampleMethod`.  
  
    3.  Парой асинхронных операций `BeginServiceAsyncMethod`\/`EndServiceAsyncMethod`.  
  
2.  Реализацией службы с использованием объекта <xref:System.IAsyncResult?displayProperty=fullName>.  
  
 [!code-csharp[C_SyncAsyncClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#1)]
 [!code-vb[C_SyncAsyncClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#1)]  
  
## См. также  
 [Создание контрактов служб](../../../docs/framework/wcf/designing-service-contracts.md)   
 [Синхронные и асинхронные операции](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md)