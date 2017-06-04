---
title: "&lt;transactionFlow&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# &lt;transactionFlow&gt;
Задает поддержку потока транзакций для пользовательской привязки.  
  
## Синтаксис  
  
```  
  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|transactionProtocol|Задает используемый протокол транзакций.  Допустимы следующие значения:<br /><br /> -   OleTransactions<br />-   WSAtomicTransactionOctober2004<br /><br /> Значение по умолчанию \- OleTransactions.<br /><br /> Это атрибут типа <xref:System.ServiceModel.TransactionProtocol>.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<привязка\>](../../../../../docs/framework/misc/binding.md)|Определяет все возможности пользовательской привязки.|  
  
## Заметки  
 Этот элемент позволяет включить или отключить входящий поток транзакций в параметрах привязки конечной точки, а также задать необходимый формат протокола для входящих транзакций.  Дополнительные сведения об использовании данного элемента конфигурации см. в разделе [Конфигурация транзакции ServiceModel](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) и [Включение потока транзакций](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).  
  
> [!CAUTION]
>  При использовании протокола `OleTransactions` для реализации потока транзакций от одной конечной точки к другой время ожидания транзакции может быть потеряно, если целевая конечная точка попытается запустить поток снова, используя любой протокол, отличный от `OleTransactions`.  Это может привести к тому, что время ожидания для всех узлов, находящихся ниже перехода OleTransactions, окажется больше, чем ожидалось.  
  
## См. также  
 <xref:System.ServiceModel.Configuration.TransactionFlowElement>   
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Конфигурация транзакции ServiceModel](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)   
 [Включение потока транзакций](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)