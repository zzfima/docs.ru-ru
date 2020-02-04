---
title: Изменение внешнего вида элемента TabControl
ms.date: 03/30/2017
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
ms.openlocfilehash: 056070177e6bbaba0c93c7b94f5adfd7887be6a8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746608"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-tabcontrol"></a>Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms
Внешний вид вкладок в Windows Forms можно изменить с помощью свойств <xref:System.Windows.Forms.TabControl> и объектов <xref:System.Windows.Forms.TabPage>, которые составляют отдельные вкладки в элементе управления. Устанавливая эти свойства, можно отображать изображения на вкладках, отображать вкладки вертикально, а не горизонтально, отображать несколько строк вкладок, а также включать и отключать вкладки программным способом.  
  
### <a name="to-display-an-icon-on-the-label-part-of-a-tab"></a>Отображение значка в части метки вкладки  
  
1. Добавьте в форму элемент управления <xref:System.Windows.Forms.ImageList>.  
  
2. Добавление изображений в список изображений.  
  
     Дополнительные сведения о списках изображений см. в разделе [ImageList Component](imagelist-component-windows-forms.md) и [инструкции по добавлению или удалению изображений с помощью компонента Windows Forms ImageList](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
3. Задайте для свойства <xref:System.Windows.Forms.TabControl.ImageList%2A> <xref:System.Windows.Forms.TabControl> элемент управления <xref:System.Windows.Forms.ImageList>.  
  
4. Задайте для свойства <xref:System.Windows.Forms.TabPage.ImageIndex%2A> <xref:System.Windows.Forms.TabPage> индекс соответствующего изображения в списке.  
  
### <a name="to-create-multiple-rows-of-tabs"></a>Создание нескольких строк вкладок  
  
1. Добавьте нужное число страниц вкладок.  
  
2. Задайте для свойства <xref:System.Windows.Forms.TabControl.Multiline%2A> <xref:System.Windows.Forms.TabControl> значение `true`.  
  
3. Если вкладки еще не отображаются в нескольких строках, установите свойство <xref:System.Windows.Forms.Control.Width%2A> <xref:System.Windows.Forms.TabControl>, чтобы оно было более узким, чем все вкладки.  
  
### <a name="to-arrange-tabs-on-the-side-of-the-control"></a>Размещение вкладок на стороне элемента управления  
  
- Задайте для свойства <xref:System.Windows.Forms.TabControl.Alignment%2A> <xref:System.Windows.Forms.TabControl> значение <xref:System.Windows.Forms.TabAlignment.Left> или <xref:System.Windows.Forms.TabAlignment.Right>.  
  
### <a name="to-programmatically-enable-or-disable-all-controls-on-a-tab"></a>Программное включение или отключение всех элементов управления на вкладке  
  
1. Задайте для свойства <xref:System.Windows.Forms.TabPage.Enabled%2A> <xref:System.Windows.Forms.TabPage> значение `true` или `false`.  
  
    ```vb  
    TabPage1.Enabled = False  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### <a name="to-display-tabs-as-buttons"></a>Отображение вкладок в виде кнопок  
  
- Задайте для свойства <xref:System.Windows.Forms.TabControl.Appearance%2A> <xref:System.Windows.Forms.TabControl> значение <xref:System.Windows.Forms.TabAppearance.Buttons> или <xref:System.Windows.Forms.TabAppearance.FlatButtons>.  
  
## <a name="see-also"></a>См. также раздел

- [Элемент управления TabControl](tabcontrol-control-windows-forms.md)
- [Общие сведения об элементе управления TabControl](tabcontrol-control-overview-windows-forms.md)
- [Практическое руководство. Добавление элемента управления на вкладку](how-to-add-a-control-to-a-tab-page.md)
- [Практическое руководство. Блокировка доступа ко вкладкам](how-to-disable-tab-pages.md)
- [Практическое руководство. Добавление и удаление вкладок с помощью элемента управления TabControl в Windows Forms](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
