---
title: "PrivacyNoticeBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0cf110b1-e25b-4d67-986b-10cb04dc4826
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# PrivacyNoticeBindingElement
PrivacyNoticeBindingElement  
  
## Синтаксис  
  
```  
class PrivacyNoticeBindingElement : BindingElement  
{  
  sint32 PrivacyNoticeVersion;  
  string Url;  
};  
```  
  
## Методы  
 Класс PrivacyNoticeBindingElement не определяет никаких методов.  
  
## Свойства  
 Класс PrivacyNoticeBindingElement имеет следующие свойства.  
  
### PrivacyNoticeVersion  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Версия уведомления о конфиденциальности.  
  
### Url  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 URL\-адрес, по которому расположено уведомление о конфиденциальности.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>