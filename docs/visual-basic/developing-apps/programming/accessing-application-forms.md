---
title: "Доступ к формам приложения (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "приложения форм, доступ"
  - "формы, доступ ко всем открытым"
  - "формы, обращение к одной форме из другой"
  - "формы, связь между"
  - "My.Forms - объект"
ms.assetid: 9aaf5aaf-2012-4f97-89c7-6e62b9d17863
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Доступ к формам приложения (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Объект `My.Forms` предоставляет легкий способ доступа к экземпляру каждой формы Windows Forms, объявленной в проекте приложения.  Свойства объекта `My.Application` можно также использовать для доступа к заставке и главной форме приложения и получения списка открытых форм приложения.  
  
## Задачи  
 Следующая таблица содержит примеры, показывающие, как получить доступ к формам приложения.  
  
|||  
|-|-|  
|Целевой тип|См.|  
|Получение доступа к одной форме из другой формы в приложении.|[Объект My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)|  
|Отображение заголовков всех открытых форм приложения.|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>|  
|Обновление экрана\-заставки с данными о состоянии при запуске приложения.|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>|  
  
## См. также  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>   
 [Объект My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)