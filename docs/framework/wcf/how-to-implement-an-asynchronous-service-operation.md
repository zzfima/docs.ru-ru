---
title: Практическое руководство. Асинхронная реализация операции службы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e5d2ea5-d8f8-4712-bd18-ea3c5461702c
ms.openlocfilehash: b706ec49db123f33b3fc1ab0f420ed9a47e32f67
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320954"
---
# <a name="how-to-implement-an-asynchronous-service-operation"></a>Практическое руководство. Асинхронная реализация операции службы
В приложениях Windows Communication Foundation (WCF) операция службы может быть реализована асинхронно или синхронно без указания клиенту способа его вызова. Например, асинхронные операции службы могут вызываться синхронно, а синхронные операции службы могут вызываться асинхронно. Пример асинхронного вызова операции в клиентском приложении см. [в разделе как вызывать операции службы асинхронно](./feature-details/how-to-call-wcf-service-operations-asynchronously.md). Дополнительные сведения о синхронных и асинхронных операциях см. в разделе [Разработка контрактов служб](designing-service-contracts.md) и [синхронных и асинхронных операций](synchronous-and-asynchronous-operations.md). В этом разделе описывается базовая структура асинхронной операции службы, код не завершен. Полный пример обеих сторон службы и клиента см. в разделе [асинхронный](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms751505(v=vs.100)).  
  
### <a name="implement-a-service-operation-asynchronously"></a>Асинхронная реализация операции службы  
  
1. В контракте службы объявите пару асинхронных методов в соответствии с рекомендациями по асинхронной разработке для платформы .NET. Метод `Begin` принимает параметр, объект обратного вызова и объект состояния, а возвращает <xref:System.IAsyncResult?displayProperty=nameWithType>; соответствующий метод `End` принимает <xref:System.IAsyncResult?displayProperty=nameWithType> и возвращает возвращаемое значение. Дополнительные сведения о асинхронных вызовах см. в разделе [шаблоны разработки асинхронного программирования](https://go.microsoft.com/fwlink/?LinkId=248221).  
  
2. Пометьте метод `Begin` пары асинхронных методов атрибутом <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType> и задайте для свойства <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A?displayProperty=nameWithType> значение `true`. Например, приведенный ниже код выполняет шаги 1 и 2.  
  
     [!code-csharp[C_SyncAsyncClient#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#6)]
     [!code-vb[C_SyncAsyncClient#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#6)]  
  
3. Реализуйте пару методов `Begin/End` в классе своей службы в соответствии с рекомендациями по асинхронной разработке. Например, в следующем примере кода показана реализация, в которой строка записывается в консоль как в части `Begin`, так и в части `End` асинхронной операции службы, и возвращаемое значение операции `End` возвращается клиенту. Полный пример кода см. в подразделе "Пример".  
  
     [!code-csharp[C_SyncAsyncClient#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#3)]
     [!code-vb[C_SyncAsyncClient#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#3)]  
  
## <a name="example"></a>Пример  
 В следующих примерах кода показаны:  
  
1. Интерфейс контракта службы с:  
  
    1. Синхронной операцией `SampleMethod`.  
  
    2. Асинхронной операцией `BeginSampleMethod`.  
  
    3. Асинхронная `BeginServiceAsyncMethod`/`EndServiceAsyncMethod`ная пара операций.  
  
2. Реализацией службы с использованием объекта <xref:System.IAsyncResult?displayProperty=nameWithType>.  
  
 [!code-csharp[C_SyncAsyncClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#1)]
 [!code-vb[C_SyncAsyncClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#1)]  
  
## <a name="see-also"></a>См. также:

- [Разработка контрактов службы](designing-service-contracts.md)
- [Синхронные и асинхронные операции](synchronous-and-asynchronous-operations.md)
