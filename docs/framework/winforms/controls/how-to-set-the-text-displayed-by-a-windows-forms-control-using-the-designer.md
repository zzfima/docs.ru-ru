---
title: "Практическое руководство. Установка текста, отображаемого элементом управления Windows Forms, с помощью конструктора"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], setting caption
- Windows Forms, setting the text displayed
ms.assetid: 9d18e0e0-f17f-4074-837d-e67ceeeaa89d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b6d49466e5dd25bbe9e97262d68f2c3fb2f8ba1a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer"></a>Практическое руководство. Установка текста, отображаемого элементом управления Windows Forms, с помощью конструктора
Элементы управления Windows Forms обычно отображается текст, связанный с основной функцией элемента управления. Например <xref:System.Windows.Forms.Button> управления обычно отображается заголовок, указывающее, какое действие будет выполняться при нажатии кнопки. С помощью свойства <xref:System.Windows.Forms.Control.Text%2A> можно задавать или получать текст для всех элементов управления. Шрифт можно менять с помощью свойства <xref:System.Windows.Forms.Control.Font%2A>.  
  
### <a name="to-set-the-text-and-font-with-the-designer"></a>Чтобы задать текст и шрифт в конструкторе  
  
1.  В окне свойств задайте <xref:System.Windows.Forms.Control.Text%2A> свойства элемента управления в соответствующую строку.  
  
     Чтобы создать сочетание клавиш, включающие амперсанд (&) перед буквой, которая будет использоваться сочетание клавиш.  
  
2.  В окне свойств нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) рядом с <xref:System.Windows.Forms.Control.Font%2A> свойство.  
  
     В диалоговом окне стандартного шрифта выберите шрифт, начертание шрифта, размер, эффекты (например, зачеркивание или подчеркивание) и скрипт нужные.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Определение текста, отображаемого элементом управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [Работами со шрифтами и текстом](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
