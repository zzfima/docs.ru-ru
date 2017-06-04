---
title: "Извлечение сведений о настройке из домена приложения | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "AppDomainSetup - объект"
  - "домены приложений, загрузка сведений о настройке"
  - "загрузка сведений о настройке"
ms.assetid: 5cdb12ae-1e37-4a62-8ec7-93d6dcc6e8d9
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Извлечение сведений о настройке из домена приложения
Каждый экземпляр домена приложения содержит свойства и сведения <xref:System.AppDomainSetup>.  Сведения о настройке можно получить из домена приложения с помощью класса <xref:System.AppDomain?displayProperty=fullName>.  Этот класс предоставляет несколько членов, извлекающих сведения конфигурации домена приложения.  
  
 Кроме того, для получения сведений о настройке домена приложения можно использовать объект **AppDomainSetup**, который передавался в домен при его создании.  
  
 В следующем примере создается новый домен приложения и выполняется вывод значений нескольких его членов на консоль.  
  
 [!code-cpp[AppDomain_Setup#2](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source2.cpp#2)]
 [!code-csharp[AppDomain_Setup#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source2.cs#2)]
 [!code-vb[AppDomain_Setup#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source2.vb#2)]  
  
 В следующем примере для домена приложения задаются и извлекаются сведения о настройке.  Обратите внимание на то, что `AppDomain.SetupInformation.ApplicationBase` получает сведения о конфигурации.  
  
 [!code-cpp[AppDomain_Setup#3](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source3.cpp#3)]
 [!code-csharp[AppDomain_Setup#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source3.cs#3)]
 [!code-vb[AppDomain_Setup#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source3.vb#3)]  
  
## См. также  
 [Hosting Overview](http://msdn.microsoft.com/ru-ru/ea527626-99e3-4995-81c4-c8f3e60eb6d5)   
 [Programming with Application Domains](http://msdn.microsoft.com/ru-ru/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [Использование доменов приложений](../../../docs/framework/app-domains/use.md)