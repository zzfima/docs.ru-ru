---
title: "Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms"
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
- icons [Windows Forms], displaying on tabs
- TabControl control [Windows Forms], changing page appearance
- tabs [Windows Forms], controlling appearance
- buttons [Windows Forms], displaying tabs as
ms.assetid: 7c6cc443-ed62-4d26-b94d-b8913b44f773
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61fb11b79459da14384af974dbc403024faa377f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-tabcontrol"></a>Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms
Можно изменить внешний вид вкладок в формах Windows Forms с помощью свойства <xref:System.Windows.Forms.TabControl> и <xref:System.Windows.Forms.TabPage> объекты, составляющие отдельные вкладки в элементе управления. Настройка этих свойств, можно отображать рисунки на вкладках, отображение вкладок вертикально, отображения нескольких рядов и также включить или отключить вкладки программными средствами.  
  
### <a name="to-display-an-icon-on-the-label-part-of-a-tab"></a>Для отображения значка Метка части вкладки  
  
1.  Добавить <xref:System.Windows.Forms.ImageList> на форму элемент управления.  
  
2.  Добавление изображений в списке изображений.  
  
     Дополнительные сведения о списках изображений см. в разделе [компонент ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) и [как: Добавление и удаление изображений с помощью компонента ImageList в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
3.  Задать <xref:System.Windows.Forms.TabControl.ImageList%2A> свойство <xref:System.Windows.Forms.TabControl> для <xref:System.Windows.Forms.ImageList> элемента управления.  
  
4.  Задать <xref:System.Windows.Forms.TabPage.ImageIndex%2A> свойство <xref:System.Windows.Forms.TabPage> индекс соответствующего рисунка в списке.  
  
### <a name="to-create-multiple-rows-of-tabs"></a>Чтобы создать несколько рядов вкладок  
  
1.  Добавление номера страниц вкладок, которые нужно.  
  
2.  Задать <xref:System.Windows.Forms.TabControl.Multiline%2A> свойство <xref:System.Windows.Forms.TabControl> для `true`.  
  
3.  Если вкладки не отображается в несколько строк, задайте <xref:System.Windows.Forms.Control.Width%2A> свойство <xref:System.Windows.Forms.TabControl> быть уже, чем все вкладки.  
  
### <a name="to-arrange-tabs-on-the-side-of-the-control"></a>Расположение вкладок вдоль края элемента управления  
  
-   Задать <xref:System.Windows.Forms.TabControl.Alignment%2A> свойство <xref:System.Windows.Forms.TabControl> для <xref:System.Windows.Forms.TabAlignment.Left> или <xref:System.Windows.Forms.TabAlignment.Right>.  
  
### <a name="to-programmatically-enable-or-disable-all-controls-on-a-tab"></a>Чтобы включить или отключить все элементы управления на вкладке  
  
1.  Задать <xref:System.Windows.Forms.TabPage.Enabled%2A> свойство <xref:System.Windows.Forms.TabPage> для `true` или `false`.  
  
    ```vb  
    TabPage1.Enabled = False  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### <a name="to-display-tabs-as-buttons"></a>Отображение вкладок как кнопки  
  
-   Задать <xref:System.Windows.Forms.TabControl.Appearance%2A> свойство <xref:System.Windows.Forms.TabControl> для <xref:System.Windows.Forms.TabAppearance.Buttons> или <xref:System.Windows.Forms.TabAppearance.FlatButtons>.  
  
## <a name="see-also"></a>См. также  
 [Элемент управления TabControl](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [Общие сведения об элементе управления TabControl](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [Практическое руководство. Добавление элемента управления на вкладку](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [Практическое руководство. Блокировка доступа ко вкладкам](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [Практическое руководство. Добавление и удаление вкладок с помощью элемента управления TabControl в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
