---
title: "Практическое руководство. Выгрузка домена приложения | Microsoft Docs"
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
  - "Unload - метод"
  - "домены приложений, выгрузка"
  - "выгрузка доменов приложений"
ms.assetid: f356116d-e415-4f7c-a332-6e6a60227192
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Выгрузка домена приложения
После завершения использования домена приложения выгрузите его с помощью метода [System.AppDomain.Unload](frlrfSystemAppDomainClassUnloadTopic).  Метод **Unload** аккуратно закрывает указанный домен приложения.  Во время процесса выгрузки к домену приложения невозможно осуществить доступ из новых потоков, кроме того, при этом происходит освобождение структур данных приложения, связанных с этим доменом.  
  
 Сборки, загруженные в домен приложения, удаляются и не могут быть доступны в дальнейшем.  Если сборка в домене приложения является нейтральной по отношению к домену, то данные сборки остаются в памяти до тех пор, пока не будет закрыт весь процесс.  Не существует способа выгрузки, нейтральной по отношению к домену сборки, кроме закрытия всего процесса.  Существуют ситуации, когда запрос на выгрузку домена приложения не работает, что приводит к исключению <xref:System.CannotUnloadAppDomainException>.  
  
 В следующем примере показаны создание нового домена приложения с именем `MyDomain`, вывод данных на консоль и затем выгрузка домена приложения.  Обратите внимание, что в коде предпринимается попытка вывести на консоль понятное имя выгруженного домена приложения.  При этом создается исключение, которое обрабатывается операторами try\/catch в конце программы.  
  
## Пример  
 [!code-cpp[System.AppDomain.Load#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source3.cpp#3)]
 [!code-csharp[System.AppDomain.Load#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source3.cs#3)]
 [!code-vb[System.AppDomain.Load#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source3.vb#3)]  
  
## См. также  
 [Programming with Application Domains](http://msdn.microsoft.com/ru-ru/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [Практическое руководство. Создание домена приложения](../../../docs/framework/app-domains/how-to-create-an-application-domain.md)   
 [Использование доменов приложений](../../../docs/framework/app-domains/use.md)