---
title: "ServiceBehaviorAttribute | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5faa266f-587f-4e03-828d-1c7dd5acfe65
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# ServiceBehaviorAttribute
ServiceBehaviorAttribute  
  
## Синтаксис  
  
```  
class ServiceBehaviorAttribute : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  string ConfigurationName;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  string InstanceContextMode;  
  sint32 MaxItemsInObjectGraph;  
  string Name;  
  string Namespace;  
  boolean ReleaseServiceInstanceOnTransactionComplete;  
  boolean TransactionAutoCompleteOnSessionClose;  
  string TransactionIsolationLevel;  
  datetime TransactionTimeout;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## Методы  
 Класс ServiceBehaviorAttribute не определяет никаких методов.  
  
## Свойства  
 Класс ServiceBehaviorAttribute имеет следующие свойства.  
  
### AutomaticSessionShutdown  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Указывает, следует ли автоматически закрывать сеанс, когда клиент закрывает выходной сеанс.  
  
### ConcurrencyMode  
 Тип данных: string  
Тип доступа: только для чтения  
  
 Указывает, поддерживает служба один поток, несколько потоков или повторные входящие вызовы.  
  
### ConfigurationName  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Имя конфигурации службы.  
  
### IgnoreExtensionDataObject  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Указывает, требуется ли передать неизвестные данные сериализации по сети.  
  
### IncludeExceptionDetailInFaults  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Указывает, включать ли информацию об управляемых исключениях в сведения об ошибках SOAP, возвращаемые клиентам для отладки.  
  
### InstanceContextMode  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Указывает, когда создается новый объект службы.  
  
### MaxItemsInObjectGraph  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное количество элементов, допустимое в сериализованном объекте.  
  
### Name  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Имя атрибута службы в WSDL.  
  
### Namespace  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Целевое пространство имен службы в WSDL.  
  
### ReleaseServiceInstanceOnTransactionComplete  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Указывает, производится ли повторное использование объекта службы после завершения текущей транзакции.  
  
### TransactionAutoCompleteOnSessionClose  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Указывает, завершаются ли ожидающие транзакции при закрытии текущего сеанса.  
  
### TransactionIsolationLevel  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Указывает уровень изоляции транзакции.  
  
### TransactionTimeout  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Период времени, в течение которого транзакция должна быть завершена.  
  
### UseSynchronizationContext  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Указывает, использовать ли текущий контекст синхронизации для выбора потока выполнения.  
  
### ValidateMustUnderstand  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Указывает, кем выполняется принудительная обработка заголовка SOAP MustUnderstand: системой или приложением.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.ServiceModel.ServiceBehaviorAttribute>