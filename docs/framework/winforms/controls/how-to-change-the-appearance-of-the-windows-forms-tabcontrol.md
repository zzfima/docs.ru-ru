---
title: "Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms | Microsoft Docs"
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
  - "кнопки, отображение вкладок как"
  - "значки, отображение на вкладках"
  - "TabControl - элемент управления [Windows Forms], изменение внешнего вида страницы"
  - "вкладки, управление внешним видом"
ms.assetid: 7c6cc443-ed62-4d26-b94d-b8913b44f773
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms
Внешний вид вкладок в формах Windows Forms может быть изменен при помощи свойств элемента управления <xref:System.Windows.Forms.TabControl> и объектов <xref:System.Windows.Forms.TabPage>, представляющих отдельные вкладки в составе элемента управления.  Настройка этих свойств позволяет отображать рисунки на вкладках, располагать вкладки вертикально, размещать их в несколько рядов, а также включать и выключать вкладки программными средствами.  
  
### Отображение значка в области надписей на вкладке  
  
1.  Добавьте элемент управления <xref:System.Windows.Forms.ImageList> в форму.  
  
2.  Добавьте изображение в список изображений.  
  
     Дополнительные сведения о списках изображений см. в разделах [Компонент ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) и [Практическое руководство. Добавление и удаление изображений, выводимых с помощью компонента ImageList, в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
3.  Задайте для свойства <xref:System.Windows.Forms.TabControl.ImageList%2A> элемента управления <xref:System.Windows.Forms.TabControl> значение <xref:System.Windows.Forms.ImageList>.  
  
4.  Присвойте свойству <xref:System.Windows.Forms.TabPage.ImageIndex%2A> объекта <xref:System.Windows.Forms.TabPage> значение индекса соответствующего изображения из списка.  
  
### Создание нескольких рядов вкладок  
  
1.  Добавьте требуемое количество страниц вкладок.  
  
2.  Присвойте свойству <xref:System.Windows.Forms.TabControl.Multiline%2A> элемента <xref:System.Windows.Forms.TabControl> значение `true`.  
  
3.  Если вкладки еще не отображены в несколько рядов, уменьшите значение свойства <xref:System.Windows.Forms.Control.Width%2A> элемента управления <xref:System.Windows.Forms.TabControl> так, чтобы оно стало меньше общей ширины всех вкладок.  
  
### Расположение вкладок вдоль края элемента управления  
  
-   Присвойте свойству <xref:System.Windows.Forms.TabControl.Alignment%2A> объекта <xref:System.Windows.Forms.TabControl> значение <xref:System.Windows.Forms.TabAlignment> или <xref:System.Windows.Forms.TabAlignment>.  
  
### Включение и выключение всех элементов управления программными средствами  
  
1.  Присвойте свойству <xref:System.Windows.Forms.TabPage.Enabled%2A> объекта <xref:System.Windows.Forms.TabPage> значение `true` или `false`.  
  
    ```vb  
    TabPage1.Enabled = False  
  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### Отображение вкладок в виде кнопок  
  
-   Присвойте свойству <xref:System.Windows.Forms.TabControl.Appearance%2A> объекта <xref:System.Windows.Forms.TabControl> значение <xref:System.Windows.Forms.TabAppearance> или <xref:System.Windows.Forms.TabAppearance>.  
  
## См. также  
 [Элемент управления TabControl](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)   
 [Общие сведения об элементе управления TabControl](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)   
 [Практическое руководство. Добавление элемента управления на вкладку](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)   
 [Практическое руководство. Блокировка доступа ко вкладкам](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)   
 [Практическое руководство. Добавление и удаление вкладок с помощью элемента управления TabControl в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)