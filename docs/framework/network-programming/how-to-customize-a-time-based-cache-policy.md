---
title: "Практическое руководство. Настройка политики кэша на основе времени | Microsoft Docs"
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
  - "настройка политик кэша на основе времени"
  - "кэш [платформа .NET Framework], политики на основе времени"
ms.assetid: 8d84f936-2376-4356-9264-03162e0f9279
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# Практическое руководство. Настройка политики кэша на основе времени
Создание Time\- на основе политики кэша можно настраивать реакция на событие кэширования, указав значения на максимальную длительность, свежесть min, max, черствость или дата синхронизации кэша.  Объект <xref:System.Net.Cache.HttpRequestCachePolicy> предоставляет несколько конструкторов, позволяющие указать допустимые комбинации этих значений.  
  
### Создание Time\- на основе политики кэша, которая использует дату синхронизации кэша  
  
-   Создайте Time\- на основе политики кэша, которая использует дату синхронизации кэша путем передачи объекта <xref:System.DateTime> в конструктор <xref:System.Net.Cache.HttpRequestCachePolicy>.  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateLastSyncPolicy(DateTime when)  
    {  
        HttpRequestCachePolicy policy =   
            new HttpRequestCachePolicy(when);  
        Console.WriteLine("When: {0}", when);  
        Console.WriteLine(policy.ToString());  
        return policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Function CreateLastSyncPolicy([when] As DateTime) As HttpRequestCachePolicy  
        Dim policy As New HttpRequestCachePolicy([when])  
        Console.WriteLine("When: {0}", [when])  
        Console.WriteLine(policy.ToString())  
        Return policy  
    End Function  
    ```  
  
 Результат аналогичен следующему:  
  
```  
When: 1/14/2004 8:07:30 AM  
Level:Default CacheSyncDate:1/14/2004 8:07:30 AM  
```  
  
### Создание Time\- на основе политики кэша, которая основывается на наименьшей актуальности  
  
-   Создайте Time\- на основе политики кэша, которая основывается на наименьшей актуальности, указав <xref:System.Net.Cache.HttpCacheAgeControl> в качестве значения параметра `cacheAgeControl` и передачи объекта <xref:System.TimeSpan> в конструктор <xref:System.Net.Cache.HttpRequestCachePolicy>.  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateMinFreshPolicy(TimeSpan span)  
    {  
        HttpRequestCachePolicy policy =   
            new HttpRequestCachePolicy(HttpCacheAgeControl.MinFresh, span);  
        Console.WriteLine(policy.ToString());  
        return policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Function CreateMinFreshPolicy(span As TimeSpan) As HttpRequestCachePolicy  
        Dim policy As New HttpRequestCachePolicy(HttpCacheAgeControl.MinFresh, span)  
        Console.WriteLine(policy.ToString())  
        Return policy  
    End Function  
    ```  
  
 Для следующего вызова:  
  
```  
CreateMinFreshPolicy(new TimeSpan(1,0,0));  
```  
  
```  
Level:Default MinFresh:3600  
  
```  
  
### Создание Time\- на основе политики кэша, которая основывается на наименьшей актуальности и максимальную длительность  
  
-   Создайте Time\- на основе политики кэша, которая основывается на наименьшей актуальности и максимальную длительность, указав <xref:System.Net.Cache.HttpCacheAgeControl> в качестве значения параметра `cacheAgeControl` и передачи 2 объекта <xref:System.TimeSpan> в конструктор <xref:System.Net.Cache.HttpRequestCachePolicy>, один для указания максимальную длительность на ресурсы и секунду, чтобы задать минимальную позволенную свежесть для объекта, возвращаемого из кэша.  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateFreshAndAgePolicy(TimeSpan freshMinimum, TimeSpan ageMaximum)  
    {  
        HttpRequestCachePolicy policy =   
        new HttpRequestCachePolicy(HttpCacheAgeControl.MaxAgeAndMinFresh, ageMaximum, freshMinimum);  
        Console.WriteLine(policy.ToString());  
        return policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Function CreateFreshAndAgePolicy(freshMinimum As TimeSpan, ageMaximum As TimeSpan) As HttpRequestCachePolicy  
        Dim policy As New HttpRequestCachePolicy(HttpCacheAgeControl.MaxAgeAndMinFresh, ageMaximum, freshMinimum)  
        Console.WriteLine(policy.ToString())  
        Return policy  
    End Function  
    ```  
  
 Для следующего вызова:  
  
```  
CreateFreshAndAgePolicy(new TimeSpan(5,0,0), new TimeSpan(10,0,0));  
```  
  
```  
Level:Default MaxAge:36000 MinFresh:18000  
```  
  
## См. также  
 [Управление кэшем для сетевых приложений](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [Политика кэша](../../../docs/framework/network-programming/cache-policy.md)   
 [Политики кэша на основе расположения](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [Политики кэша на основе времени](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [Элемент \<requestCaching\> \(параметры сети\)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)