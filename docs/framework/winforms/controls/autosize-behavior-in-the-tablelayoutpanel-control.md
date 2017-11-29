---
title: "Автоматическое изменение размеров элемента управления TableLayoutPanel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- localizing forms
- layout [Windows Forms], AutoSize
- sizing [Windows Forms], automatic
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- automatic sizing
- AutoSizeMode property
ms.assetid: 9233e0c3-2fa6-405e-8701-959479b1250e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3d4813b7bd37c0c5bd9b04b37cb825067b35ce3d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="autosize-behavior-in-the-tablelayoutpanel-control"></a>Автоматическое изменение размеров элемента управления TableLayoutPanel
## <a name="distinct-autosize-behaviors"></a>Поведение различных AutoSize  
 <xref:System.Windows.Forms.TableLayoutPanel> Элемент управления поддерживает автоматическое изменение размеров одним из следующих способов:  
  
-   Через <xref:System.Windows.Forms.Control.AutoSize%2A> свойства;  
  
-   Через <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> свойство <xref:System.Windows.Forms.TableLayoutPanel> стили столбцов и строк элемента управления.  
  
### <a name="the-autosize-property-with-row-and-column-styles"></a>Свойство AutoSize со стилями столбцов и строк  
 В следующей таблице описаны взаимодействие между <xref:System.Windows.Forms.Control.AutoSize%2A> свойство и <xref:System.Windows.Forms.TableLayoutPanel> стили столбцов и строк элемента управления.  
  
|Параметр AutoSize|Взаимодействие со стилем|  
|----------------------|-----------------------|  
|`false`|<xref:System.Windows.Forms.TableLayoutPanel> Управления выполняется слева направо и выделяет место для столбца или строки или в следующем порядке.<br /><br /> 1.  Если <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> свойству <xref:System.Windows.Forms.SizeType.Absolute>, количество пикселей, заданное <xref:System.Windows.Forms.ColumnStyle.Width%2A> или <xref:System.Windows.Forms.RowStyle.Height%2A> выделяется.<br />2.  Если <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> свойству <xref:System.Windows.Forms.SizeType.AutoSize>, возвращенных дочернего элемента управления в точках <xref:System.Windows.Forms.Control.GetPreferredSize%2A> метод выделяется.<br />3.  После ввода всех <xref:System.Windows.Forms.SizeType.Absolute> и <xref:System.Windows.Forms.SizeType.AutoSize> столбцы или строки выделяется, любые столбцы или строки с <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> значение <xref:System.Windows.Forms.SizeType.Percent> используются для пропорционального выделения оставшегося свободного пространства|  
|`true`|Аналогично описанному взаимодействию, за исключением того, <xref:System.Windows.Forms.SizeType.Percent> столбцы или строки получения автоматического изменения размеров.<br /><br /> <xref:System.Windows.Forms.TableLayoutPanel> Управления расширяет столбец или строку для создания достаточного свободного пространства, чтобы не столбца или строки с <xref:System.Windows.Forms.SizeType.Percent> перекрывалось его содержимое. <xref:System.Windows.Forms.TableLayoutPanel> Управления выделяет новое пространство пропорционально в зависимости <xref:System.Windows.Forms.ColumnStyle.Width%2A> или <xref:System.Windows.Forms.RowStyle.Height%2A> свойства.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [Общие сведения об элементе управления TableLayoutPanel](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-overview.md)
