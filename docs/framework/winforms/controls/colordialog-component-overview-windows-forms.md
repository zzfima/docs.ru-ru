---
title: "Общие сведения о компоненте ColorDialog (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ColorDialog
helpviewer_keywords:
- color dialog box [Windows Forms], about color dialog box
- ColorDialog component [Windows Forms], about ColorDialog
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7f3a25c601e46c18a30755a15131bba03669a2ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="colordialog-component-overview-windows-forms"></a>Общие сведения о компоненте ColorDialog (Windows Forms)
Windows Forms <xref:System.Windows.Forms.ColorDialog> компонент является стандартным диалоговым окном, который позволяет пользователю выбрать цвет из палитры и добавления в нее пользовательских цветов. Это то же диалоговое окно, которое вы видите в других приложениях Windows для выбора цветов. Он используется в приложении Windows в качестве простого решения вместо настройки собственного диалогового окна.  
  
 Цвет, выбранный в диалоговом окне, возвращается в <xref:System.Windows.Forms.ColorDialog.Color%2A> свойство. Если <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> свойству `false`, кнопка «Определить цвет» становится недоступной, и пользователь будет ограничен стандартных цветов в палитре. Если <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> свойству `true`, пользователь может выбрать сглаженный цвет. Чтобы открыть диалоговое окно, необходимо вызвать его <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ColorDialog>  
 [Компонент ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)  
 [Элементы управления и компоненты диалоговых окон](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)  
 [Практическое руководство. Изменение внешнего вида компонента ColorDialog в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)
