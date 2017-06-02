---
title: "Управление подключениями | Microsoft Docs"
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
  - "Интернет, подключения"
  - "HTTP, классы для подключения"
  - "запрос данных из Интернета, подключения"
  - "отправка данных, подключения"
  - "получение данных, подключения"
  - "класс ServicePoint, о классе ServicePoint"
  - "ответ на интернет-запрос, подключения"
  - "подключения [платформа .NET Framework], классы"
  - "сетевые ресурсы, подключения"
  - "загрузка интернет-ресурсов, подключения"
  - "класс ServicePointManager, о классе ServicePointManager"
ms.assetid: 9b3d3de7-189f-4f7d-81ae-9c29c441aaaa
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Управление подключениями
Приложения, использующие HTTP для подключения к ресурсам данных могут использовать классы <xref:System.Net.ServicePoint> и <xref:System.Net.ServicePointManager> платформы .NET Framework для управления подключения к Интернету и помочь их для достижения оптимальных масштабирования и производительности.  
  
 Класс **ServicePoint** предоставляет приложение с конечной точкой, в которую приложение может подключиться, чтобы получить доступ к ресурсам интернета.  Каждое **ServicePoint** содержит сведения, способствующий оптимизируют соединения с сервером через интернет, совместно использовать данные по оптимизации между соединениями для повышения производительности.  
  
 Каждое **ServicePoint** задан универсальный код ресурса \(uri\) и фрагментов относится в соответствии с идентификатором и узла схемы универсальный код ресурса \(uri\).  Например, один и тот же экземпляр **ServicePoint** реализации бы запросы Uri http:\/\/www.contoso.com\/index.htm и http:\/\/www.contoso.com\/news.htm?date\=today, поскольку они имеют один и тот же идентификатор схемы \(HTTP\) и фрагменты узла \(www.contoso.com\).  Если приложение уже имеет постоянное подключение к серверу www.contoso.com, она использует это соединение для извлечения оба запроса, что позволяет избежать необходимости создать 2 соединения.  
  
 **ServicePointManager** статический класс, который управляет созданием и разрушение экземпляров **ServicePoint**.  **ServicePointManager** создает **ServicePoint** если приложение запрашивает интернет\-ресурс, который отсутствует в коллекции существующих экземпляров **ServicePoint**.  Экземпляры **ServicePoint** уничтожаются при их превышали их максимальное время простоя или если количество существующих экземпляров **ServicePoint** превышает максимальное количество экземпляров **ServicePoint** для приложения.  Можно вести наблюдение и по умолчанию максимальное время бездействия и максимальное число экземпляров **ServicePoint**  путем установки свойства <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A> и <xref:System.Net.ServicePointManager.MaxServicePoints%2A> на **ServicePointManager**.  
  
 Количество связь между клиентом и сервером может иметь драматический влияние на пропускную способность приложения.  По умолчанию приложение с помощью класса <xref:System.Net.HttpWebRequest> использует до 2 постоянных подключений к данному серверу, но можно задать максимальное число соединений на основе в\- приложения.  
  
> [!NOTE]
>  Вычисленные пределы HTTP\/1.1 число соединений из приложения до 2 соединений в сервер.  
  
 Оптимальное число зависит от соединений реальные условия, при которых выполняется приложение.  Увеличение числа соединений, доступных приложению не может повлиять на производительность приложения.  Определения влияния нескольких подключений, пока тесты производительности выполнения меняющ число подключений.  Можно изменить количество соединений, используемых приложением, изменив статическое свойство <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> в классе **ServicePointManager** при инициализации приложения, как показано в следующем образце кода.  
  
```csharp  
// Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4;  
```  
  
```vb  
' Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4  
```  
  
 Чтобы изменить свойство **ServicePointManager.DefaultConnectionLimit** не влияет на экземпляры **ServicePoint** ранее, инициализируемые.  Следующий код демонстрирует изменение ограничения подключения на существующем **ServicePoint** для сервера http:\/\/www.contoso.com значение, хранящееся в `newLimit`.  
  
```csharp  
Uri uri = new Uri("http://www.contoso.com/");  
ServicePoint sp = ServicePointManager.FindServicePoint(uri);  
sp.ConnectionLimit = newLimit;  
```  
  
```vb  
Dim uri As New Uri("http://www.contoso.com/")  
Dim sp As ServicePoint = ServicePointManager.FindServicePoint(uri)  
sp.ConnectionLimit = newLimit  
```  
  
## См. также  
 [Группирование подключений](../../../docs/framework/network-programming/connection-grouping.md)   
 [Использование протоколов приложений](../../../docs/framework/network-programming/using-application-protocols.md)