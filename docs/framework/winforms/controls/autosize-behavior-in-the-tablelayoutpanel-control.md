---
title: "Автоматическое изменение размеров элемента управления TableLayoutPanel | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "автоматическое изменение размеров"
  - "AutoSize - свойство, TableLayoutPanel - элемент управления"
  - "AutoSizeMode - свойство"
  - "элементы управления [Windows Forms], установка размеров"
  - "макет [Windows Forms], AutoSize"
  - "локализация форм"
  - "установка размеров, автоматическая"
  - "TableLayoutPanel - элемент управления [Windows Forms], поведение AutoSize"
ms.assetid: 9233e0c3-2fa6-405e-8701-959479b1250e
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Автоматическое изменение размеров элемента управления TableLayoutPanel
## Различные поведения AutoSize  
 Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> поддерживает автоматическое изменение размеров посредством следующих способов.  
  
-   С помощью свойства <xref:System.Windows.Forms.Control.AutoSize%2A>;  
  
-   С помощью свойства <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> стилей столбцов и строк элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.  
  
### Свойство AutoSize со стилями столбцов и строк  
 В следующей таблице описано взаимодействие между свойством <xref:System.Windows.Forms.Control.AutoSize%2A> и стилями столбцов и строк элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.  
  
|Значение свойства AutoSize|Взаимодействие со стилем|  
|--------------------------------|------------------------------|  
|`false`|Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> располагается слева направо и выделяет место для столбцов и строк или в следующем порядке.<br /><br /> 1.  Если свойство <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> имеет значение <xref:System.Windows.Forms.SizeType>, выделяется количество пикселей, заданное <xref:System.Windows.Forms.ColumnStyle.Width%2A> или <xref:System.Windows.Forms.RowStyle.Height%2A>.<br />2.  Если свойство <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> имеет значение <xref:System.Windows.Forms.SizeType>, выделяется количество пикселей, возвращенное методом <xref:System.Windows.Forms.Control.GetPreferredSize%2A> дочернего элемента управления.<br />3.  После выделения места для всех столбцов или строк <xref:System.Windows.Forms.SizeType> и <xref:System.Windows.Forms.SizeType>, любые столбцы или строки со свойством <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> равным <xref:System.Windows.Forms.SizeType> используются для пропорционального выделения оставшегося свободного пространства.|  
|`true`|Подобно описанному взаимодействию, но с тем исключением, что столбцы или строки <xref:System.Windows.Forms.SizeType> приобретают возможность автоматического изменения размеров.<br /><br /> Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> расширяет столбец или строку для создания достаточного свободного пространства, так чтобы содержимое в какой\-либо строке или столбце со стилями <xref:System.Windows.Forms.SizeType> не перекрывалось.  Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> выделяет новое пространство пропорционально в зависимости от свойства <xref:System.Windows.Forms.ColumnStyle.Width%2A> или <xref:System.Windows.Forms.RowStyle.Height%2A>.|  
  
## См. также  
 <xref:System.Windows.Forms.TableLayoutPanel>   
 [Общие сведения об элементе управления TableLayoutPanel](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-overview.md)