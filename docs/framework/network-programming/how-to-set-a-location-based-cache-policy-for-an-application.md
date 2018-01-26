---
title: "Практическое руководство. Установка политики кэша для приложения на основе расположения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- expliciting defining cache behavior
- location-based cache policies
- local cache
- request cache policies
- cache [.NET Framework], location-based policies
ms.assetid: 683bb88e-3411-4f46-9686-3411b6ba511c
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 9d54a34b5d7cf40a6eaa9d777b9b05a1be34f177
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-a-location-based-cache-policy-for-an-application"></a>Практическое руководство. Установка политики кэша для приложения на основе расположения
Политики кэша на основе расположения позволяют приложению явным образом определить поведение кэша на основе расположения запрошенного ресурса. В этом разделе описана установка политики кэша программным способом. Сведения об установке политики для приложения с помощью файлов конфигурации см. в разделе [Элемент \<requestCaching> (сетевые параметры)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md).  
  
### <a name="to-set-a-location-based-cache-policy-for-an-application"></a>Установка политики кэша для приложения на основе расположения  
  
1.  Создайте объект <xref:System.Net.Cache.RequestCachePolicy> или <xref:System.Net.Cache.HttpRequestCachePolicy>.  
  
2.  Установите этот объект политики как объект по умолчанию для домена приложения.  
  
### <a name="to-set-a-policy-that-takes-requested-resources-from-a-cache"></a>Установка политики, которая принимает запрошенные ресурсы из кэша  
  
-   Создайте политику, которая принимает запрошенные ресурсы из кэша, если они есть в кэше. В противном случае запросы отправляются на сервер с помощью установки уровня кэширования <xref:System.Net.Cache.HttpRequestCacheLevel.CacheIfAvailable>. Для выполнения запроса может использоваться любой кэш между клиентом и сервером, включая удаленный кэш.  
  
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
  
### <a name="to-set-a-policy-that-prevents-any-cache-from-supplying-resources"></a>Установка политики, которая полностью запрещает получение ресурсов из кэша  
  
-   Создайте политику, которая полностью запрещает получение запрошенных ресурсов из кэша, установив уровень кэширования <xref:System.Net.Cache.HttpRequestCacheLevel.NoCacheNoStore>. С этой политикой ресурс удаляется из локального кэша (если он присутствует в локальном кэше), а также из удаленных кэшей.  
  
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
  
### <a name="to-set-a-policy-that-returns-requested-resources-only-if-they-are-in-the-local-cache"></a>Установка политики, которая возвращает запрошенные ресурсы, только если они присутствуют в локальном кэше  
  
-   Создайте политику, которая возвращает запрошенные ресурсы только в том случае, если они присутствуют в локальном кэше, установив уровень кэширования <xref:System.Net.Cache.HttpRequestCacheLevel.CacheOnly>. Если запрошенный ресурс отсутствует в кэше, выдается исключение <xref:System.Net.WebException>.  
  
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
  
### <a name="to-set-a-policy-that-prevents-the-local-cache-from-supplying-resources"></a>Установка политики, которая запрещает получение ресурсов из локального кэша  
  
-   Создайте политику, которая запрещает получение запрошенных ресурсов из локального кэша, установив уровень кэширования <xref:System.Net.Cache.HttpRequestCacheLevel.Refresh>. Если запрошенный ресурс находится в промежуточном кэше и успешно проверен, ресурс может быть возвращен из промежуточного кэша.  
  
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
  
### <a name="to-set-a-policy-that-prevents-any-cache-from-supplying-requested-resources"></a>Установка политики, которая полностью запрещает получение запрошенных ресурсов из кэша  
  
-   Создайте политику, которая полностью запрещает получение запрошенных ресурсов из кэша, установив уровень кэширования <xref:System.Net.Cache.HttpRequestCacheLevel.Reload>. Ресурс, возвращенный сервером, может быть сохранен в кэше.  
  
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
  
### <a name="to-set-a-policy-that-allows-any-cache-to-supply-requested-resources-if-the-resource-on-the-server-is-not-newer-than-the-cached-copy"></a>Установка политики, которая разрешает получение запрошенных ресурсов из любого кэша, если кэшированная копия не старше ресурса на сервере  
  
-   Создайте политику, которая разрешает получение запрошенных ресурсов из любого кэша, если кэшированная копия не старше ресурса на сервере, установив уровень кэширования <xref:System.Net.Cache.HttpRequestCacheLevel.Revalidate>.  
  
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
  
## <a name="see-also"></a>См. также  
 [Управление кэшем для сетевых приложений](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [Политика кэша](../../../docs/framework/network-programming/cache-policy.md)  
 [Политики кэша на основе расположения](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [Политики кэша на основе времени](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 [Элемент \<requestCaching> (сетевые параметры)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)
