---
title: "Привязка | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Привязка
wmi Binding  
  
## Синтаксис  
  
```  
class Binding  
{  
  BindingElement BindingElements[];  
  datetime CloseTimeout;  
  string Name;  
  string Namespace;  
  datetime OpenTimeout;  
  datetime ReceiveTimeout;  
  string Scheme;  
  datetime SendTimeout;  
};  
```  
  
## Методы  
 Класс Binding не определяет никаких методов.  
  
## Свойства  
 Класс Binding имеет следующие свойства.  
  
### BindingElements  
 Тип данных: массив BindingElement  
  
 Тип доступа: только для чтения  
  
 Коллекция элементов привязки, реализованных привязкой.  
  
### CloseTimeout  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Интервал времени, предусмотренный для завершения операции закрытия.  
  
### Name  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Имя привязки.  
  
### Namespace  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Пространство имен XML привязки.  
  
### OpenTimeout  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Интервал времени, предусмотренный для завершения операции открытия.  
  
### ReceiveTimeout  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Интервал времени, предусмотренный для завершения операции получения.  
  
### Scheme  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Схема транспорта универсальных кодов ресурсов \(URI\), которая используется производствами каналов и прослушивателей, созданными привязкой.  
  
### SendTimeout  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Интервал времени, предусмотренный для завершения операции отправки.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.ServiceModel.Channels.Binding>