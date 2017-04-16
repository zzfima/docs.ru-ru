---
title: "Практическое руководство. Определение действий, выполняемых в случае переполнения элемента управления ToolStrip, в Windows Forms | Microsoft Docs"
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
  - "CanOverflow - свойство"
  - "примеры [Windows Forms], панели инструментов"
  - "Overflow - свойство"
  - "панели инструментов [Windows Forms], обработка переполнения"
  - "ToolStrip - элемент управления [Windows Forms], обработка переполнения"
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Определение действий, выполняемых в случае переполнения элемента управления ToolStrip, в Windows Forms
Если в элементе управления <xref:System.Windows.Forms.ToolStrip> не хватает места для размещения всех элементов, можно разрешить возможность переполнения для элемента управления <xref:System.Windows.Forms.ToolStrip> и определить поведение этой функции для конкретных элементов <xref:System.Windows.Forms.ToolStripItem>.  
  
 При добавлении элементов <xref:System.Windows.Forms.ToolStripItem>, для размещения которых недостаточно места, выделенного элементу управления <xref:System.Windows.Forms.ToolStrip> с учетом текущего размер формы, на элементе управления <xref:System.Windows.Forms.ToolStrip> автоматически появляется кнопка <xref:System.Windows.Forms.ToolStripOverflowButton>.  После появления кнопки <xref:System.Windows.Forms.ToolStripOverflowButton> элементы, для которых разрешено переполнение, переносятся в раскрывающееся меню переполнения.  Это позволяет производить настройку и устанавливать приоритеты при отображении элементов <xref:System.Windows.Forms.ToolStrip> в соответствии с изменением размеров формы.  Кроме того, существует возможность изменения внешнего вида элементов, переносимых в меню переполнения, с помощью свойств <xref:System.Windows.Forms.ToolStripItem.Placement%2A> и <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=fullName> и события <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>.  Увеличение размеров формы на этапе разработки или во время выполнения позволяет отображаться большему количеству элементов <xref:System.Windows.Forms.ToolStripItem> в главном элементе управления <xref:System.Windows.Forms.ToolStrip>, и кнопка <xref:System.Windows.Forms.ToolStripOverflowButton> может даже исчезнуть до тех пор, пока размеры формы снова не уменьшатся.  
  
### Включение переполнения для элемента управления ToolStrip  
  
-   Проверьте, чтобы свойству <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> элемента управления <xref:System.Windows.Forms.ToolStrip> не было присвоено значение `false`.  Значение по умолчанию — `True`.  
  
     Если свойство <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> имеет значение `True` \(устанавливается по умолчанию\), элемент <xref:System.Windows.Forms.ToolStripItem> переносится в раскрывающееся меню переполнения, если содержимое элемента <xref:System.Windows.Forms.ToolStripItem> превышает ширину горизонтального элемента управления <xref:System.Windows.Forms.ToolStrip> или  высоту вертикального элемента управления <xref:System.Windows.Forms.ToolStrip>.  
  
### Определение поведения отдельного элемента ToolStripItem при переполнении  
  
-   Присвойте свойству <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> элемента <xref:System.Windows.Forms.ToolStripItem> требуемое значение.  Возможные значения — `Never`, `AsNeeded` и `Always`.  Значение по умолчаниюсуществует  `AsNeeded`.  
  
    ```vb  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never  
  
    ```  
  
    ```csharp  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never;  
  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStripOverflowButton>   
 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>   
 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>   
 [Общие сведения об элементе управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [Архитектура элемента управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [Технологии, положенные в основу работы элемента управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)