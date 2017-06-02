---
title: "Приложения с интерфейсом MDI | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "формы, MDI - интерфейс"
  - "MDI - интерфейс"
  - "Windows Forms, MDI - приложения"
  - "окна, MDI - интерфейс"
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Приложения с интерфейсом MDI
Приложения с многооконным интерфейсом \(MDI\) позволяют отображать несколько документов сразу, при этом каждый документ отображается в отдельном окне.  Приложения с MDI\-интерфейсом часто содержат элементы меню Window с вложенным меню для переключения между окнами или документами.  
  
> [!NOTE]
>  В Windows Forms существуют определенные различия в работе MDI\-форм и окон с однодокументным интерфейсом \(SDI\).  Свойство `Opacity` не влияет на внешний вид дочерних форм MDI.  Кроме того, метод <xref:System.Windows.Forms.Form.CenterToParent%2A> не влияет на поведение дочерних форм MDI.  
  
## В этом подразделе  
 [Практическое руководство. Создание родительских MDI\-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 Указания по созданию контейнера для нескольких документов в приложении с MDI\-интерфейсом.  
  
 [Практическое руководство. Создание дочерних MDI\-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 Указания по созданию одного или нескольких окон, которые работают в родительской MDI\-форме.  
  
 [Практическое руководство. Определение активной дочерней MDI\-формы](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 Указания по проверке наличия фокуса у определенной формы и отправке данных этой формы в буфер обмена.  
  
 [Практическое руководство. Отправка данных в активную дочернюю MDI\-форму](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 Указания по передаче сведений в активное дочернее окно.  
  
 [Практическое руководство. Упорядочение дочерних форм интерфейса MDI](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)  
 Указания по мозаичному или каскадному размещению и расположению дочерних окон в приложении с MDI\-интерфейсом.