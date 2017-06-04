---
title: "Практическое руководство. Изменение внешнего вида компонента ColorDialog в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Цвет - диалоговое окно, настройка внешнего вида"
  - "ColorDialog - компонент, примеры"
  - "ColorDialog - компонент, настройка внешнего вида"
ms.assetid: bba4e262-1cd7-4f63-89cf-330a36f7b539
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Изменение внешнего вида компонента ColorDialog в Windows Forms
Внешний вид компонента Windows Forms <xref:System.Windows.Forms.ColorDialog> можно настроить с помощью набора его свойств.  В этом диалоговом окне два раздела: в первом представлены основные цвета, во втором — средства для настройки цветов пользователем.  
  
 Большинство свойств ограничивают набор цветов, которые пользователь может выбрать в этом диалоговом окне.  Если для свойства <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> задано значение `true`, пользователь может задавать собственные цвета.  Для свойства <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> задано значение `true`, если диалоговое окно развертывается для определения пользовательских цветов; в противном случае пользователь должен нажать кнопку "Определить цвет".  Если для свойства <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> задано значение `true`, в диалоговом окне отображаются все доступные цвета в наборе основных цветов.  Если для свойства <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> задано значение `true`, пользователь не может выбрать полутона; для выбора доступны только чистые цвета.  
  
 Если для свойства <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> задано значение `true`, в диалоговом окне появляется кнопка "Справка".  При нажатии кнопки "Справка" возникает событие <xref:System.Windows.Forms.CommonDialog.HelpRequest> компонента <xref:System.Windows.Forms.ColorDialog>  
  
### Чтобы настроить внешний вид диалогового окна цветов, выполните следующие действия:  
  
1.  Задайте нужные значения для свойств <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> и <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A>.  
  
    ```vb  
    ColorDialog1.AllowFullOpen = True  
    ColorDialog1.AnyColor = True  
    ColorDialog1.SolidColorOnly = False  
    ColorDialog1.ShowHelp = True  
  
    ```  
  
    ```csharp  
    colorDialog1.AllowFullOpen = true;  
    colorDialog1.AnyColor = true;  
    colorDialog1.SolidColorOnly = false;  
    colorDialog1.ShowHelp = true;  
  
    ```  
  
    ```cpp  
    colorDialog1->AllowFullOpen = true;  
    colorDialog1->AnyColor = true;  
    colorDialog1->SolidColorOnly = false;  
    colorDialog1->ShowHelp = true;  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.ColorDialog>   
 [Компонент ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)   
 [Общие сведения о компоненте ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md)