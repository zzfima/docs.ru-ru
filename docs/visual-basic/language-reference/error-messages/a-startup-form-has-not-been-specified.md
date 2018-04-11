---
title: Начальная форма не указана
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fdffc182ee66497d68aafb7dc37cfef75b4d2e9f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="a-startup-form-has-not-been-specified"></a>Начальная форма не указана
Приложение использует <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> класса, но не указывает начальную форму.  
  
 Это может произойти, если **Включить исполняющую среду** флажок в конструкторе проектов, но **Начальная форма** не указан. Дополнительные сведения см. в разделе [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Укажите автоматически запускаемый объект для приложения.  
  
     Дополнительные сведения см. в разделе [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
2.  Переопределить <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> метод, чтобы задать <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> свойства форму запуска.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>  
 [Обзор модели приложения в Visual Basic](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
