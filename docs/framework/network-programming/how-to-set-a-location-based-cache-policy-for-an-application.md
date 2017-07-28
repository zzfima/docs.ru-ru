---
title: "Практическое руководство. Установка политики кэша для приложения на основе расположения | Microsoft Docs"
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
  - "явное определение поведения кэша"
  - "политики кэша на основе расположения"
  - "локальный кэш"
  - "политики кэширования запроса"
  - "кэш [платформа .NET Framework], политики на основе расположения"
ms.assetid: 683bb88e-3411-4f46-9686-3411b6ba511c
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Практическое руководство. Установка политики кэша для приложения на основе расположения
Место хранения\- на основе политики кэша позволяют приложению явно задать расширения функциональности кэширования, основанную на месте запрошенного ресурса.  В этом разделе демонстрируется устанавливать политику кэша программно.  Дополнительные сведения о настройке политики для приложения с помощью файлов конфигурации см. в разделе [Элемент \<requestCaching\> \(параметры сети\)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md).  
  
### Задать расположение хранения\- на политику кэша для приложения  
  
1.  Создайте объект <xref:System.Net.Cache.RequestCachePolicy> или <xref:System.Net.Cache.HttpRequestCachePolicy>.  
  
2.  Присвойте объект политики по умолчанию для домена приложения.  
  
### Задать политику, которая принимает запрошенные ресурсы из кэша  
  
-   Создайте политику, которая принимает запрошенные ресурсы из кэша, если он доступен, в противном случае отправляет передаваемые запросы, установив кэш уровня в <xref:System.Net.Cache.HttpRequestCacheLevel>.  Запрос может выполняться любым кэшем между клиентом и сервером, включая удаленные кэши.  
  
    ```csharp  
    public static void UseCacheIfAvailable()  
    {  
        HttpRequestCachePolicy policy = new HttpRequestCachePolicy  
            (HttpRequestCacheLevel.CacheIfAvailable);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
  
    ```  
  
    ```vb  
    Public Shared Sub UseCacheIfAvailable()  
        Dim policy As New HttpRequestCachePolicy _  
             (HttpRequestCacheLevel.CacheIfAvailable)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### Задать политику, которая предотвращает какой\-либо из кэша, предоставляющего ресурсов  
  
-   Создание политики кэша, которая предотвращает какой\-либо из запрошенных предоставляющего ресурсов с помощью установки уровня <xref:System.Net.Cache.HttpRequestCacheLevel> в кэш.  Этот уровень политики удаляет ресурс из локального кэша, если присутствует и указывает на то, что удаленный кэши, они должны также удалить ресурс.  
  
    ```csharp  
    public static void DoNotUseCache()  
    {  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.NoCacheNoStore);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub DoNotUseCache()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.NoCacheNoStore)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### Задать политику, которая возвращает запрошенные ресурсы, только если их в локальном кэше  
  
-   Создайте политику, которая возвращает запрошенные ресурсы, только если их в локальном кэше, установив кэш к <xref:System.Net.Cache.HttpRequestCacheLevel>.  Если запрошенный ресурс не находится в кэше, то возникает исключение <xref:System.Net.WebException>.  
  
    ```csharp  
    public static void OnlyUseCache()  
    {  
        HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.CacheOnly);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub OnlyUseCache()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.CacheOnly)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### Задать политику, которая предотвращает локальный кэш из указав ресурсов  
  
-   Создайте политику, которая предотвращает локальный кэш из запрошенных предоставляющего ресурсов с помощью установки уровня <xref:System.Net.Cache.HttpRequestCacheLevel> в кэш.  Если запрошенный ресурс в промежуточном кэше и успешно revalidated, промежуточный кэш может предоставить запрошенный ресурс.  
  
    ```csharp  
    public static void DoNotUseLocalCache()  
    {  
     HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.Refresh);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub DoNotUseLocalCache()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.Refresh)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### Задать политику, которая предотвращает какой\-либо из кэша, предоставляющего запрошенных ресурсов  
  
-   Создание политики кэша, которая предотвращает какой\-либо из запрошенных предоставляющего ресурсов с помощью установки уровня <xref:System.Net.Cache.HttpRequestCacheLevel> в кэш.  Ресурс, возвращенный сервером могут храниться в кэше.  
  
    ```csharp  
    public static void SendToServer()  
    {  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.Reload);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub SendToServer()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.Reload)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### Задать политику, которая позволяет любой кэш к ресурсам обрабатывается, если запрошенный ресурс на сервере не новее, чем кэшированная копия  
  
-   Создайте политику, которая позволяет любой кэш к ресурсам обрабатывается, если запрошенный ресурс на сервере не новее, чем кэшированную копию, установив кэш уровня в <xref:System.Net.Cache.HttpRequestCacheLevel>.  
  
    ```csharp  
    public static void CheckServer()  
    {  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy  
             (HttpRequestCacheLevel.Revalidate);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub CheckServer()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.Revalidate)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
## См. также  
 [Управление кэшем для сетевых приложений](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [Политика кэша](../../../docs/framework/network-programming/cache-policy.md)   
 [Политики кэша на основе расположения](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [Политики кэша на основе времени](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [Элемент \<requestCaching\> \(параметры сети\)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)