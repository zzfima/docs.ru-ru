---
title: "Конечная точка | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Конечная точка
Конечная точка  
  
## Синтаксис  
  
```  
class Endpoint  
{  
  string Address;  
  string AddressHeaders[];  
  string AddressIdentity;  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  Binding Binding;  
  string ContractName;  
  string CounterInstanceName;  
  string ListenUri;  
  string Name;  
  sint32 ProcessId;  
  Contract ref;  
};  
```  
  
## Методы  
 Класс Endpoint определяет следующий метод.  
  
|Метод|Описание|  
|-----------|--------------|  
|[GetOperationCounterInstanceName](../../../../../docs/framework/wcf/diagnostics/wmi/getoperationcounterinstancename.md)|Извлекает имя экземпляра счетчика производительности операций|  
  
## Свойства  
 Класс Endpoint имеет следующие свойства.  
  
### Адрес  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Универсальный код ресурса \(URI\), содержащий адрес конечной точки.  
  
### AddressHeaders  
 Тип данных: массив строк  
  
 Тип доступа: только для чтения  
  
 Коллекция заголовков адреса, прикрепленных к этой конечной точке.  
  
### AddressIdentity  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Удостоверение конечной точки.  
  
### AppDomainId  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Идентификатор домена приложения, который размещает конечную точку.  
  
### Поведения  
 Тип данных: массив Behavior  
  
 Тип доступа: только для чтения  
  
 Коллекция поведений, реализуемых этой конечной точкой.  
  
### Привязка  
 Тип данных: Binding  
  
 Тип доступа: только для чтения  
  
 Привязка, используемая этой конечной точкой.  
  
### ContractName  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Строка, в которой указывается, какой контракт предоставляется этой конечной точкой.  
  
### CounterInstanceName  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Имя экземпляра счетчиков производительности конечной точки.  
  
### ListenUri  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Универсальный код ресурса \(URI\), от которого данная конечная точка ожидает передачи данных.  
  
### Имя  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Уникальное имя конечной точки.  
  
### ProcessId  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Возвращает идентификатор процесса, который размещает конечную точку.  
  
### ref  
 Тип данных: Contract  
  
 Тип доступа: только для чтения  
  
 Контракт, предоставляемый этой конечной точкой.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|