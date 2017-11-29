---
title: "Свойство AutoSize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- sizing [Windows Forms], automatic
- layout [Windows Forms], AutoSize
- automatic sizing
- AutoSizeMode property
ms.assetid: 62fd82a2-9565-4f65-925b-9d1e66dc4e7d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c8216880ebdede03bbd01fe53b622c14ca8c514d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="autosize-property-overview"></a>Свойство AutoSize
<xref:System.Windows.Forms.Control.AutoSize%2A> Свойство включает элемент управления изменить его размер, при необходимости для достижения значения, указанного в <xref:System.Windows.Forms.Control.PreferredSize%2A> свойство. Настроить поведение при изменении размера для определенного элемента управления, задав `AutoSizeMode` свойство.  
  
## <a name="autosize-behavior"></a>Автоматическое изменение размеров  
 Некоторые элементы управления поддерживают <xref:System.Windows.Forms.Control.AutoSize%2A> свойство. Кроме того, некоторые элементы управления, которые поддерживают <xref:System.Windows.Forms.Control.AutoSize%2A> свойство также поддерживает `AutoSizeMode` свойство.  
  
 <xref:System.Windows.Forms.Control.AutoSize%2A> Свойство выводятся немного по-разному в зависимости от типа элемента управления и значение `AutoSizeMode` свойства, если свойство существует. В следующей таблице описывается поведение, которые всегда имеют значение true и предоставляет краткое описание каждого из них:  
  
|Поведение всегда имеет значение true|Описание|  
|--------------------------|-----------------|  
|Автоматическое изменение размеров — это функция времени выполнения.|Это означает, что он никогда не увеличивается или уменьшения размеров элемента управления и затем имеет без последующих изменений.|  
|Если элемент управления изменяет свой размер значение его <xref:System.Windows.Forms.Control.Location%2A> свойства всегда остается постоянным.|Если содержимое элемента управления приводит к его увеличиваться, размеры элемента управления, направо и сверху вниз. Элементы управления не увеличиваются слева.|  
|<xref:System.Windows.Forms.Control.Dock%2A> И <xref:System.Windows.Forms.Control.Anchor%2A> свойства соблюдаются, когда <xref:System.Windows.Forms.Control.AutoSize%2A> — `true`.|Значение элемента управления <xref:System.Windows.Forms.Control.Location%2A> настройки свойства правильное значение.<br /><br /> **Примечание** <xref:System.Windows.Forms.Label> управления является исключением из этого правила. Если задано значение закрепленного <xref:System.Windows.Forms.Label> элемента управления <xref:System.Windows.Forms.Control.AutoSize%2A> свойства `true`, <xref:System.Windows.Forms.Label> элемент управления не будет растягиваться.|  
|Элемент управления <xref:System.Windows.Forms.Control.MaximumSize%2A> и <xref:System.Windows.Forms.Control.MinimumSize%2A> свойства учитываются всегда, независимо от значения его <xref:System.Windows.Forms.Control.AutoSize%2A> свойство.|<xref:System.Windows.Forms.Control.MaximumSize%2A> И <xref:System.Windows.Forms.Control.MinimumSize%2A> свойства не подвержены <xref:System.Windows.Forms.Control.AutoSize%2A> свойство.|  
|Минимальный размер, значение по умолчанию не установлен.|Это означает, что если сжать в группе управления <xref:System.Windows.Forms.Control.AutoSize%2A> и он не имеет содержимого, значение его <xref:System.Windows.Forms.Control.Size%2A> свойство — 0,0. В этом случае элемент управления будет сжат до точки, и он не будет невидимым.|  
|Если элемент управления не реализует <xref:System.Windows.Forms.Control.GetPreferredSize%2A> метода <xref:System.Windows.Forms.Control.GetPreferredSize%2A> метод возвращает последнее значение, присвоенное <xref:System.Windows.Forms.Control.Size%2A> свойство.|Это означает, что установка <xref:System.Windows.Forms.Control.AutoSize%2A> для `true` не будет действовать.|  
|Элемент управления в <xref:System.Windows.Forms.TableLayoutPanel> ячейки всегда уменьшаются до размеров ячейки до его <xref:System.Windows.Forms.Control.MinimumSize%2A> достигается.|Этот размер принудительно устанавливается как максимальный размер. Это не так, если ячейка является частью <xref:System.Windows.Forms.SizeType.AutoSize> строк или столбцов.|  
  
## <a name="autosizemode-property"></a>AutoSizeMode-свойство  
 `AutoSizeMode` Свойство обеспечивает более точное управление по умолчанию <xref:System.Windows.Forms.Control.AutoSize%2A> поведение. `AutoSizeMode` Свойство указывает, каким образом размера элемента управления на его содержимое. Содержимое, например, может представлять собой текст для <xref:System.Windows.Forms.Button> управления или дочерние элементы управления для контейнера.  
  
 В следующей таблице показаны <xref:System.Windows.Forms.AutoSizeMode> elicits параметры и описание поведения каждого параметра.  
  
|Параметр AutoSizeMode|Поведение|  
|--------------------------|--------------|  
|GrowAndShrink|Элемент управления увеличиваются или уменьшаются в помещалось все содержимое.<br /><br /> <xref:System.Windows.Forms.Control.MinimumSize%2A> И <xref:System.Windows.Forms.Control.MaximumSize%2A> значения учитываются, но текущее значение <xref:System.Windows.Forms.Control.Size%2A> свойство игнорируется.<br /><br /> Такое же поведение элементов управления, имеющих <xref:System.Windows.Forms.Control.AutoSize%2A> свойство и нет `AutoSizeMode` свойство.|  
|GrowOnly|Размеры элемента управления, насколько необходимо, чтобы помещалось все содержимое, но он будет уменьшаются до значения, указанного в его <xref:System.Windows.Forms.Control.Size%2A> свойство.<br /><br /> Это значение по умолчанию для `AutoSizeMode`.|  
  
## <a name="controls-that-support-the-autosize-property"></a>Элементы управления, поддерживающие свойство AutoSize  
 В следующей таблице перечислены элементы управления, поддерживающие <xref:System.Windows.Forms.Control.AutoSize%2A> и `AutoSizeMode` свойства.  
  
|Поддержка AutoSize|Тип элемента управления|  
|----------------------|------------------|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A>свойство поддерживается.<br />-Не `AutoSizeMode` свойство.|<xref:System.Windows.Forms.CheckBox><br /><br /> <xref:System.Windows.Forms.DomainUpDown><br /><br /> <xref:System.Windows.Forms.Label><br /><br /> <xref:System.Windows.Forms.LinkLabel><br /><br /> <xref:System.Windows.Forms.MaskedTextBox>(<xref:System.Windows.Forms.TextBox> базовый)<br /><br /> <xref:System.Windows.Forms.NumericUpDown><br /><br /> <xref:System.Windows.Forms.RadioButton><br /><br /> <xref:System.Windows.Forms.TextBox><br /><br /> <xref:System.Windows.Forms.TrackBar>|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A>свойство поддерживается.<br />-   `AutoSizeMode`свойство поддерживается.|<xref:System.Windows.Forms.Button><br /><br /> <xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.FlowLayoutPanel><br /><br /> <xref:System.Windows.Forms.Form><br /><br /> <xref:System.Windows.Forms.GroupBox><br /><br /> <xref:System.Windows.Forms.Panel><br /><br /> <xref:System.Windows.Forms.TableLayoutPanel>|  
|-Не <xref:System.Windows.Forms.Control.AutoSize%2A> свойство.|<xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.ComboBox><br /><br /> <xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DateTimePicker><br /><br /> <xref:System.Windows.Forms.ListBox><br /><br /> <xref:System.Windows.Forms.ListView><br /><br /> <xref:System.Windows.Forms.MaskedTextBox><br /><br /> <xref:System.Windows.Forms.MonthCalendar><br /><br /> <xref:System.Windows.Forms.ProgressBar><br /><br /> <xref:System.Windows.Forms.PropertyGrid><br /><br /> <xref:System.Windows.Forms.RichTextBox><br /><br /> <xref:System.Windows.Forms.SplitContainer><br /><br /> <xref:System.Windows.Forms.TabControl><br /><br /> <xref:System.Windows.Forms.TabPage><br /><br /> <xref:System.Windows.Forms.TreeView><br /><br /> <xref:System.Windows.Forms.WebBrowser><br /><br /> <xref:System.Windows.Forms.ScrollBar>|  
  
## <a name="autosize-in-the-design-environment"></a>AutoSize в среде разработки  
 В следующей таблице описаны поведение при изменении размера элемента управления во время разработки на основе значения из его <xref:System.Windows.Forms.Control.AutoSize%2A> и `AutoSizeMode` свойства.  
  
 Переопределить <xref:System.Windows.Forms.Design.ControlDesigner.SelectionRules%2A> свойства, чтобы определить, является ли данный элемент управления находится в состоянии, пользователь изменять размер. В таблице ниже «не может» означает <xref:System.Windows.Forms.Design.SelectionRules.Moveable> только «может» означает <xref:System.Windows.Forms.Design.SelectionRules.AllSizeable> и <xref:System.Windows.Forms.Design.SelectionRules.Moveable>.  
  
|Параметры AutoSize|Операция изменения размера во время разработки|  
|-----------------------|---------------------------------|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-Не `AutoSizeMode` свойство.|Пользователь не может изменять размеры элемента управления во время разработки, за исключением следующих элементов управления:<br /><br /> -   <xref:System.Windows.Forms.TextBox><br />-   <xref:System.Windows.Forms.MaskedTextBox><br />-   <xref:System.Windows.Forms.RichTextBox><br />-   <xref:System.Windows.Forms.TrackBar>|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-   `AutoSizeMode` = <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>|Пользователь не может изменять размеры элемента управления во время разработки.|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-   `AutoSizeMode` = <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>|Пользователь может изменить размер элемента управления во время разработки. Когда <xref:System.Windows.Forms.Control.Size%2A> свойство задано, пользователь может только увеличивать размер элемента управления.|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `false`, или <xref:System.Windows.Forms.Control.AutoSize%2A> свойство скрыто.|Пользователь может изменять размеры элемента управления во время разработки.|  
  
> [!NOTE]
>  Для достижения максимальной производительности, конструктор Windows Forms скрывает <xref:System.Windows.Forms.Control.AutoSize%2A> свойство <xref:System.Windows.Forms.Form> класса. Во время разработки формы ведет себя так, будто <xref:System.Windows.Forms.Control.AutoSize%2A> свойству `false`, независимо от фактической настройки. Во время выполнения, оптимизация не производится и <xref:System.Windows.Forms.Control.AutoSize%2A> свойство применяется, заданные значения свойства.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Control.AutoSize%2A>  
 <xref:System.Windows.Forms.Control.PreferredSize%2A>  
 <xref:System.Windows.Forms.Control.GetPreferredSize%2A>
