---
title: "Ссылка My (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My - функция"
  - "My - ссылка"
ms.assetid: 6f803bd7-21ff-4569-b1fe-b00a6678b1e3
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Ссылка My (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Средство `My` ускоряет и упрощает программирование путем предоставления интуитивно понятного доступа к часто используемым методам, свойствам и событиям.  В следующей таблице перечислены объекты, содержащиеся в `My`, и действия, которые могут быть выполнены с каждым из них.  
  
|**Действие**|**Объект.**|  
|------------------|-----------------|  
|Доступ к сведениям о приложениях и службам.|Объект `My.Application` состоит из следующих классов:<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase> предоставляет члены, которые доступны во всех проектах.<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> предоставляет члены, доступные в приложениях Windows Forms.<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase> предоставляет члены, доступные в консольных приложениях.|  
|Доступ к локальному компьютеру и его ресурсам, службам и данным.|`My.Computer` \(<xref:Microsoft.VisualBasic.Devices.Computer>\)|  
|Доступ к формам в текущем проекте.|[Объект My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)|  
|Доступ к журналу приложения.|`My.Application.Log` \(<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log%2A>\)|  
|Доступ к текущему веб\-запросу.|[Объект My.Request](../../../visual-basic/language-reference/objects/my-request-object.md)|  
|Доступ к ресурсам элементов.|[Объект My.Resources](../../../visual-basic/language-reference/objects/my-resources-object.md)|  
|Доступ к текущему веб\-ответу.|[Объект My.Response](../../../visual-basic/language-reference/objects/my-response-object.md)|  
|Доступ к параметрам пользовательского уровня и уровня приложения.|[Объект My.Settings](../../../visual-basic/language-reference/objects/my-settings-object.md)|  
|Доступ к контексту безопасности текущего пользователя.|`My.User` \(<xref:Microsoft.VisualBasic.ApplicationServices.User>\)|  
|Доступ к веб\-службам XML, на которые ссылается текущий проект.|[Объект My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)|  
  
## См. также  
 [Обзор модели приложения в Visual Basic](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)   
 [Разработка с использованием My](../../../visual-basic/developing-apps/development-with-my/index.md)