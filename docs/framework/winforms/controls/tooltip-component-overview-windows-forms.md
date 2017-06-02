---
title: "Общие сведения о компоненте ToolTip (Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ToolTip"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ToolTip - компонент [Windows Forms], сведения о компоненте ToolTip"
  - "всплывающие подсказки [Windows Forms], сведения о всплывающих подсказках"
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Общие сведения о компоненте ToolTip (Windows Forms)
Компонент Windows Forms <xref:System.Windows.Forms.ToolTip> отображает текст при наведении указателя мыши на элементы управления.  Компонент ToolTip можно связать с любым элементом управления.  Пример использования этого компонента: для экономии места в форме можно создать кнопку в виде маленького значка и воспользоваться компонентом ToolTip, чтобы объяснить функцию кнопки.  
  
## Использование компонента ToolTip  
 Компонент <xref:System.Windows.Forms.ToolTip> предоставляет свойство `ToolTip` нескольким элементам управления в форме Windows Forms или в другом контейнере.  Например, поместив один компонент <xref:System.Windows.Forms.ToolTip> в форму, можно вывести текст "Введите сюда ваше имя" для элемента управления <xref:System.Windows.Forms.TextBox> и текст "Сохранение изменений" для элемента управления <xref:System.Windows.Forms.Button>.  
  
 Основные методы компонента <xref:System.Windows.Forms.ToolTip> – <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> и <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>.  Метод <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> используется для задания компонентов ToolTips, отображающихся для элементов управления.  Дополнительные сведения см. в разделе [Практическое руководство. Определение всплывающих подсказок для элементов управления в Windows Forms во время разработки](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md).  Основными свойствами являются свойство <xref:System.Windows.Forms.ToolTip.Active%2A>, для которого необходимо задать значение `true`, чтобы компонент ToolTip отображался, и свойство <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, которое определяет, как долго отображается строка ToolTip, как долго необходимо указывать на элемент управления, чтобы компонент ToolTip появился, и спустя какое время появятся последующие окна ToolTip.  Дополнительные сведения см. в разделе [Практическое руководство. Изменение значения задержки для компонента ToolTip в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md).  
  
## См. также  
 <xref:System.Windows.Forms.ToolTip>   
 [Практическое руководство. Определение всплывающих подсказок для элементов управления в Windows Forms во время разработки](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)   
 [Практическое руководство. Изменение значения задержки для компонента ToolTip в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)