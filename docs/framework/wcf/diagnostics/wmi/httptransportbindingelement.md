---
title: "HttpTransportBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 088a7bce-6bb2-4839-ad74-f68d4b1aa0f9
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# HttpTransportBindingElement
HttpTransportBindingElement  
  
## Синтаксис  
  
```  
class HttpTransportBindingElement : TransportBindingElement  
{  
  boolean AllowCookies;  
  string AuthenticationScheme;  
  boolean BypassProxyOnLocal;  
  string HostNameComparisonMode;  
  boolean KeepAliveEnabled;  
  sint32 MaxBufferSize;  
  string ProxyAddress;  
  string ProxyAuthenticationScheme;  
  string Realm;  
  string TransferMode;  
  boolean UnsafeConnectionNtlmAuthentication;  
  boolean UseDefaultWebProxy;  
};  
```  
  
## Методы  
 Класс HttpTransportBindingElement не определяет никаких методов.  
  
## Свойства  
 Класс HttpTransportBindingElement имеет следующие свойства.  
  
### AllowCookies  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Значение, указывающее, принимает ли клиент файлы cookie, и распространяет ли он их по запросу.  
  
### AuthenticationScheme  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Схема проверки подлинности, используемая для проверки подлинности клиентских запросов, обрабатываемых HTTP\-прослушивателем.  
  
### BypassProxyOnLocal  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Значение, указывающее, игнорируются ли прокси\-серверы для локальных адресов.  
  
### HostNameComparisonMode  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Значение, указывающее, используется ли имя узла для доступа к службе при сопоставлении по универсальному коду ресурса \(URI\).  
  
### KeepAliveEnabled  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Когда включено, соединения HTTP остаются в активном состоянии независимо от уровня активности.  
  
### MaxBufferSize  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальный размер буферного пула.  
  
### ProxyAddress  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Универсальный код ресурса \(URI\), который содержит адрес прокси\-сервера, используемого для выполнения HTTP\-запросов.  
  
### ProxyAuthenticationScheme  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Схема проверки подлинности, используемая для проверки подлинности клиентских запросов, обрабатываемых прокси\-сервером HTTP.  
  
### Realm  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Область проверки подлинности.  
  
### TransferMode  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Значение, указывающее статус сообщения: помещено в буфер или поток, запрос или ответ.  
  
### UnsafeConnectionNtlmAuthentication  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Значение, указывающее, разрешено ли на сервере совместное использование небезопасных подключений.  
  
### UseDefaultWebProxy  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Значение, указывающее, используются ли параметры прокси\-сервера компьютера или пользователя.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>