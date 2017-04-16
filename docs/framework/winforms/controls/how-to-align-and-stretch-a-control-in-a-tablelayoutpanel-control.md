---
title: "Практическое руководство. Выравнивание и растягивание элемента управления в элементе управления TableLayoutPanel | Microsoft Docs"
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
  - "net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "элементы управления [Windows Forms], выравнивание"
  - "элементы управления [Windows Forms], растяжение"
  - "TableLayoutPanel - элемент управления [Windows Forms], растяжение элементов управления"
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Выравнивание и растягивание элемента управления в элементе управления TableLayoutPanel
Можно выравнивать и растягивать элементы управления в элементе управления <xref:System.Windows.Forms.TableLayoutPanel>, используя свойства <xref:System.Windows.Forms.Control.Anchor%2A> и <xref:System.Windows.Forms.Control.Dock%2A>.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы выровнять и растянуть элемент управления, выполните следующие действия:  
  
1.  Перетащите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> из **панели элементов** в форму.  
  
2.  Перетащите элемент управления <xref:System.Windows.Forms.Button> из **панели элементов** в верхнюю левую ячейку элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.  Элемент управления <xref:System.Windows.Forms.Button> выравнивается по центру ячейки.  
  
3.  Присвойте свойству <xref:System.Windows.Forms.Control.Anchor%2A> элемента управления <xref:System.Windows.Forms.Button> значение `Left,Right`.  Элемент управления <xref:System.Windows.Forms.Button> растягивается в соответствии с шириной ячейки.  
  
4.  Присвойте свойству <xref:System.Windows.Forms.Control.Anchor%2A> элемента управления <xref:System.Windows.Forms.Button> значение `Top,Bottom`.  Элемент управления <xref:System.Windows.Forms.Button> растягивается в соответствии с высотой ячейки.  
  
5.  Присвойте свойству <xref:System.Windows.Forms.Control.Dock%2A> элемента управления <xref:System.Windows.Forms.Button> значение <xref:System.Windows.Forms.DockStyle>.  Элемент управления <xref:System.Windows.Forms.Button> разворачивается, чтобы заполнить ячейку.  
  
6.  Присвойте свойству <xref:System.Windows.Forms.Control.Dock%2A> элемента управления <xref:System.Windows.Forms.Button> значение <xref:System.Windows.Forms.DockStyle>.  Элемент управления <xref:System.Windows.Forms.Button> возвращается к исходному размеру и перемещается в верхний левый угол ячейки.  Конструктор **Windows Forms** установил для свойства <xref:System.Windows.Forms.Control.Anchor%2A> значение `Top, Left`.  
  
7.  Присвойте свойству <xref:System.Windows.Forms.Control.Anchor%2A> элемента управления <xref:System.Windows.Forms.Button> значение `Bottom,Right`.  Элемент управления <xref:System.Windows.Forms.Button> перемещается в правый нижний угол ячейки.  
  
8.  Присвойте свойству <xref:System.Windows.Forms.Control.Anchor%2A> элемента управления <xref:System.Windows.Forms.Button> значение <xref:System.Windows.Forms.AnchorStyles>.  Элемент управления <xref:System.Windows.Forms.Button> перемещается в центр ячейки.  
  
## См. также  
 [Элемент управления TableLayoutPanel](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)