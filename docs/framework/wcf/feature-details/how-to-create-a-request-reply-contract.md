---
title: "Как создать контракт типа &#171;запрос-ответ&#187; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 801d90da-3d45-4284-9c9f-56c8aadb4060
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# Как создать контракт типа &#171;запрос-ответ&#187;
Контракт «запрос\-ответ» указывает метод, который возвращает ответ.Необходима отправка ответа и его корреляция запросу согласно условиям этого контракта.Даже если метод не возвращает ответ \(`void` в C\# или `Sub` в Visual Basic\), инфраструктура создает и отправляет вызывающему объекту пустое сообщение.Чтобы запретить отправку пустого ответного сообщения, используйте для операции односторонний контракт.  
  
### Создание контракта типа запрос\-ответ  
  
1.  Создайте интерфейс на любом языке программирования.  
  
2.  Примените атрибут <xref:System.ServiceModel.ServiceContractAttribute> к интерфейсу.  
  
3.  Примените атрибут <xref:System.ServiceModel.OperationContractAttribute> к каждому методу, который могут вызывать клиенты.  
  
4.  Необязательно.Установите свойство <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> в значение `true`, чтобы избежать отправки пустого ответного сообщения.По умолчанию все операции используют контракты «запрос\-ответ».  
  
## Пример  
 В следующем образце определяется контракт для службы калькулятора, предоставляющей методы `Add` и `Subtract`.Метод `Multiply` не является частью контракта, поскольку он не отмечен классом <xref:System.ServiceModel.OperationContractAttribute>, а потому недоступен клиентам.  
  
```  
using System.ServiceModel;   
  
[ServiceContract]   
public interface ICalculator   
{   
[OperationContract]   
// It would be equivalent to write explicitly:  
// [OperationContract(IsOneWay=false)]   
int Add(int a, int b);   
  
[OperationContract]   
int Subtract(int a, int b);   
  
int Multiply(int a, int b)  
}  
```  
  
-   [!INCLUDE[crabout](../../../../includes/crabout-md.md)] об указании контрактов операции см. в описании класса <xref:System.ServiceModel.OperationContractAttribute> и свойства <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>.  
  
-   Применение атрибутов <xref:System.ServiceModel.ServiceContractAttribute> и <xref:System.ServiceModel.OperationContractAttribute> вызывает автоматическое создание определений контракта службы в документе WSDL после развертывания службы.Документ загружается путем добавления `?wsdl` к базовому адресу HTTP для службы,например `http://microsoft/CalculatorService?wsdl`.  
  
## См. также  
 <xref:System.ServiceModel.OperationContractAttribute>   
 [Создание контрактов служб](../../../../docs/framework/wcf/designing-service-contracts.md)   
 [Как создавать дуплексный контракт](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)