---
title: "Help Systems in Windows Forms Applications | Microsoft Docs"
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
  - "Help, adding to Windows applications"
  - "Windows applications, providing Help systems"
  - "What's This? Help"
  - "Help, Windows Forms"
  - "HelpProvider component [Windows Forms], providing Help in Windows applications"
ms.assetid: 2a96a278-432c-41fc-9e3c-5bfedf5e1267
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Help Systems in Windows Forms Applications
Одним из наиболее важных преимуществ, которые разработчик может предоставить пользователям, является исчерпывающая справочная система,  к которой всегда можно обратиться в случае затруднений.  Предоставление справочной системы в приложениях Windows легко обеспечить с помощью [Компонент HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md).  
  
## Различные типы справки  
 Компонент Windows Forms <xref:System.Windows.Forms.HelpProvider> используется для связи файла справки HTML Help 1.x \(либо CHM\-файла, созданного с помощью HTML Help Workshop, либо HTM\-файла\) с приложением Windows.  Компонент <xref:System.Windows.Forms.HelpProvider> может использоваться для предоставления контекстной справки для элементов управления Windows Forms или конкретных элементов управления.  Кроме того, компонент <xref:System.Windows.Forms.HelpProvider> позволяет открыть файл справки для конкретной области, например для главной страницы содержания, указателя или для функции поиска.  Общие сведения о компоненте <xref:System.Windows.Forms.HelpProvider> см. в разделе [Общие сведения о компоненте HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-overview-windows-forms.md).  Сведения по использованию компонента <xref:System.Windows.Forms.HelpProvider> для отображения всплывающей справки в формах Windows Forms см. в разделе [Практическое руководство. Отображение всплывающей справки](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md).  Сведения об использовании компонента <xref:System.Windows.Forms.ToolTip> для отображения справки, касающейся определенного элемента управления, см. в разделе [Отображение справки по элементам управления с помощью всплывающих подсказок](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md).  
  
 Имеется возможность создать файлы справки HTML Help 1.x с помощью HTML Help Workshop.  Дополнительные сведения о HTML\-справке см. в разделе "HTML Help Workshop" или в других разделах "HTML Help" сети MSDN.  
  
## См. также  
 [Интеграция справки пользователя в формы Windows Forms](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)   
 [Компонент HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md)   
 [Компонент ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)   
 [Общие сведения о Windows Forms](../../../../docs/framework/winforms/windows-forms-overview.md)   
 [Windows Forms](../../../../docs/framework/winforms/index.md)