---
title: "Практическое руководство. Изменение внешнего вида компонента ColorDialog в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ColorDialog component [Windows Forms], examples
- ColorDialog component [Windows Forms], formatting appearance
- color dialog box [Windows Forms], configuring appearance
ms.assetid: bba4e262-1cd7-4f63-89cf-330a36f7b539
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 11edb1019b8fedde368d712ab27dd0954a2de50a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-colordialog-component"></a>Практическое руководство. Изменение внешнего вида компонента ColorDialog в Windows Forms
Можно настроить внешний вид Windows Forms <xref:System.Windows.Forms.ColorDialog> компонент с номером его свойства. Диалоговое окно имеет две части — один из них базовые цвета, а второй позволяет пользователю определять собственные цвета.  
  
 Большинство свойств ограничивают набор цветов, пользователь может выбрать в диалоговом окне. Если <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> свойству `true`, пользователь может определять собственные цвета. <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> Свойство `true` Если диалоговое окно развертывается для определения пользовательских цветов; в противном случае пользователь должен нажать кнопку «Определить цвет». Когда <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> свойству `true`, диалоговое окно отображает все доступные цвета в наборе основных цветов. Если <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> свойству `true`, пользователь может выбрать сглаженный цвет; для выбора доступны только сплошными цветами.  
  
 Если <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> свойству `true`, в диалоговом окне отображается кнопка справки. Когда пользователь нажимает кнопку "Справка" <xref:System.Windows.Forms.ColorDialog> компонента <xref:System.Windows.Forms.CommonDialog.HelpRequest> события.  
  
### <a name="to-configure-the-appearance-of-the-color-dialog-box"></a>Чтобы настроить внешний вид диалогового окна "цвета"  
  
1.  Задать <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>, и <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> нужные значения для свойств.  
  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ColorDialog>  
 [Компонент ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)  
 [Общие сведения о компоненте ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md)
