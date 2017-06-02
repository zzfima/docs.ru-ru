---
title: "Практическое руководство. Настройка домена приложения | Microsoft Docs"
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
  - "домены приложений, настройка"
  - "ApplicationBase - свойство"
ms.assetid: 07ea8438-7a34-49f0-a7e8-3d6ff7e4a482
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Настройка домена приложения
Сведения о настройке нового домена приложения среде CLR можно предоставить с помощью класса <xref:System.AppDomainSetup>.  При создании собственных доменов приложений наиболее важным свойством является <xref:System.AppDomainSetup.ApplicationBase%2A>.  Другие свойства **AppDomainSetup** используются главным образом узлами среды выполнения для настройки определенного домена приложения.  
  
 Свойство **ApplicationBase** определяет корневой каталог приложения.  Когда среде выполнения требуется ответить на запрос о типе, то она выполняет поиск сборки, содержащей тип в каталоге, определенном в свойстве **ApplicationBase**.  
  
> [!NOTE]
>  Новый домен приложения наследует только свойство **ApplicationBase** своего создателя.  
  
 В следующем примере создается экземпляр класса **AppDomainSetup**, используемого для создания нового домена приложения, производится вывод данных на консоль и затем выгрузка домена приложения.  
  
## Пример  
 [!code-cpp[ADApplicationBase#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADApplicationBase/CPP/source2.cpp#2)]
 [!code-csharp[ADApplicationBase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADApplicationBase/CS/source2.cs#2)]
 [!code-vb[ADApplicationBase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADApplicationBase/VB/source2.vb#2)]  
  
## См. также  
 [Hosting Overview](http://msdn.microsoft.com/ru-ru/ea527626-99e3-4995-81c4-c8f3e60eb6d5)   
 [Programming with Application Domains](http://msdn.microsoft.com/ru-ru/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [Использование доменов приложений](../../../docs/framework/app-domains/use.md)