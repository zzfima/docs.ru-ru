---
title: "Практическое руководство. Установка политики кэша для приложения на основе времени по умолчанию"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- time-based cache policies
- cache [.NET Framework], time-based policies
- default time-based cache policy
ms.assetid: 6bfce066-a2e7-4add-a05e-85c12ec9f07f
caps.latest.revision: 9
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f462c55919025b92014a99d73b9a6b779465f98e
ms.contentlocale: ru-ru
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-set-the-default-time-based-cache-policy-for-an-application"></a>Практическое руководство. Установка политики кэша для приложения на основе времени по умолчанию
Политики кэша на основе времени по умолчанию позволяют приложению определить поведение кэширования с помощью заголовков, которые отправляются с кэшируемым ресурсом. Поведение кэширования определяется в разделах 13 и 14 стандарта RFC 2616, который доступен на сайте [http://www.ietf.org](http://www.ietf.org/). Это поведение кэширования подходит для большинства приложений.  
  
### <a name="to-set-the-default-automatic-policy-for-an-application"></a>Установка политики кэша по умолчанию для приложения  
  
1.  Создайте объект политики на основе времени по умолчанию.  
  
2.  Установите этот объект политики как объект по умолчанию для домена приложения.  
  
## <a name="example"></a>Пример  
 В двух примерах в этом разделе формируются идентичные политики.  
  
 В следующем примере создается политика на основе времени по умолчанию. Затем эта политика устанавливается в качестве политики по умолчанию для домена приложения.  
  
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
  
 Политику кэша на основе времени по умолчанию также можно создать с помощью класса <xref:System.Net.Cache.RequestCachePolicy>, как показано в следующем примере:  
  
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
  
## <a name="see-also"></a>См. также  
 [Управление кэшем для сетевых приложений](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [Политика кэша](../../../docs/framework/network-programming/cache-policy.md)   
 [Политики кэша на основе расположения](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [Политики кэша на основе времени](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [Элемент \<requestCaching> (сетевые параметры)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)

