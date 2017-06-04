---
title: "Практическое руководство. Установка политики кэша для приложения на основе времени по умолчанию | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "политики кэша на основе времени"
  - "кэш [платформа .NET Framework], политики на основе времени"
  - "политика кэша на основе времени по умолчанию"
ms.assetid: 6bfce066-a2e7-4add-a05e-85c12ec9f07f
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Практическое руководство. Установка политики кэша для приложения на основе времени по умолчанию
Time\- на основе значение по умолчанию политика кэша позволяет приложению иметь свою расширения функциональности кэша указанную заголовками, отправленными с кэшировать ресурсом и расширения функциональности кэша указанную в шагах 13 и 14 RFC 2616, доступном по адресу. [http:\/\/www.ietf.org](http://www.ietf.org/) Это подходит функциональности кэша для большинства приложений.  
  
### Установить по умолчанию автоматическую политику для приложения  
  
1.  Создайте объект Time\- по умолчанию на основе политик.  
  
2.  Присвойте объект политики по умолчанию для домена приложения.  
  
## Пример  
 2 Примера в этом разделе, создают идентичные политики.  
  
 В следующем примере создается на основе политики по умолчанию Time\- и задает его как значение по умолчанию для домена приложения.  
  
```csharp  
public static void SetDefaultTimeBasedPolicy ()  
{  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy ();  
    HttpWebRequest.DefaultCachePolicy = policy ;  
}  
```  
  
```vb  
Public Shared Sub SetDefaultTimeBasedPolicy ()  
    Dim policy = New HttpRequestCachePolicy ()  
    HttpWebRequest.DefaultCachePolicy = policy  
End Sub  
```  
  
 Можно также создать на основе Time\- значение по умолчанию политика кэша, используя класс <xref:System.Net.Cache.RequestCachePolicy> как показано в следующем примере:  
  
```csharp  
public static void SetDefaultTimeBasedPolicy2()  
{  
    RequestCachePolicy policy = new RequestCachePolicy ();  
    HttpWebRequest.DefaultCachePolicy = policy ;  
}  
```  
  
```vb  
Public Shared Sub SetDefaultTimeBasedPolicy2()  
    Dim policy As New RequestCachePolicy()  
    HttpWebRequest.DefaultCachePolicy = policy  
End Sub  
  
```  
  
## См. также  
 [Управление кэшем для сетевых приложений](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [Политика кэша](../../../docs/framework/network-programming/cache-policy.md)   
 [Политики кэша на основе расположения](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [Политики кэша на основе времени](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [Элемент \<requestCaching\> \(параметры сети\)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)