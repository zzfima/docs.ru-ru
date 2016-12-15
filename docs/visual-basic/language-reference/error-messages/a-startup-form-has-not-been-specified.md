---
title: "Начальная форма не указана | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrAppModel_NoStartupForm"
dev_langs: 
  - "VB"
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Начальная форма не указана
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Приложение использует класс <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>, но не указывает начальную форму.  
  
 Это может произойти, если установить флажок **Включить исполняющую среду** в конструкторе проекта, но **Начальная форма** не указана.  Дополнительные сведения см. в разделе [Страница «Приложение» в конструкторе проектов \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic).  
  
### Чтобы исправить эту ошибку  
  
1.  Укажите автоматически запускаемый объект для приложения.  
  
     Дополнительные сведения см. в разделе [Страница «Приложение» в конструкторе проектов \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic).  
  
2.  Переопределите метод <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>, чтобы установить свойство <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> начальной формы.  
  
## См. также  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>   
 [Обзор модели приложения в Visual Basic](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)