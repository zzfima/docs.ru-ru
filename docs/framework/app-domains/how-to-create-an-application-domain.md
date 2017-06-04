---
title: "Практическое руководство. Создание домена приложения | Microsoft Docs"
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
  - "домены приложений, создание"
ms.assetid: ba1fa43e-49f5-47d9-bd7f-3024af16f4ba
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Создание домена приложения
Хост\-приложение CLR автоматически создает домены приложений в нужный момент.  Тем не менее можно создать собственные домены приложений и загрузить их в те сборки, которыми требуется управлять отдельно.  Кроме того, домены приложений можно создать из доменов, выполняющих код.  
  
 Создать новый домен приложения можно с помощью одного из перегруженных методов **CreateDomain** в классе <xref:System.AppDomain?displayProperty=fullName>.  Для домена приложения можно назначить имя и использовать его в ссылках на домен.  
  
 В следующем примере создается новый домен приложения, которому назначается имя `MyDomain`, после чего на консоль выводятся имя домена хоста и нового созданного дочернего домена приложения.  
  
## Пример  
 [!code-cpp[ADCreateDomain#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADCreateDomain/CPP/source2.cpp#2)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
  
## См. также  
 [Hosting Overview](http://msdn.microsoft.com/ru-ru/ea527626-99e3-4995-81c4-c8f3e60eb6d5)   
 [Programming with Application Domains](http://msdn.microsoft.com/ru-ru/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [Использование доменов приложений](../../../docs/framework/app-domains/use.md)