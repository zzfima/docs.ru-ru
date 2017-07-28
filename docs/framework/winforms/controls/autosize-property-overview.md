---
title: "Свойство AutoSize | Microsoft Docs"
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
  - "AutoSize - свойство"
  - "AutoSizeMode - свойство"
  - "макет [Windows Forms], AutoSize"
  - "установка размеров, автоматическая"
ms.assetid: 62fd82a2-9565-4f65-925b-9d1e66dc4e7d
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Свойство AutoSize
Свойство <xref:System.Windows.Forms.Control.AutoSize%2A> позволяет при необходимости изменять размеры элемента управления в соответствии со значением свойства <xref:System.Windows.Forms.Control.PreferredSize%2A>.  Способ изменения размера для определенного элемента управления настраивается с помощью свойства `AutoSizeMode`.  
  
## Автоматическое изменение размеров  
 Свойство <xref:System.Windows.Forms.Control.AutoSize%2A> поддерживается только некоторыми элементами управления.  Кроме того, некоторые элементы управления, поддерживающие свойство <xref:System.Windows.Forms.Control.AutoSize%2A>, также поддерживают свойство `AutoSizeMode`.  
  
 Свойство <xref:System.Windows.Forms.Control.AutoSize%2A> может работать несколько по\-разному в зависимости от типа элемента управления и значения свойства `AutoSizeMode`, если оно существует.  В следующей таблице приводятся обязательные особенности данного свойства с кратким описанием каждого из них.  
  
|Обязательные особенности|Описание|  
|------------------------------|--------------|  
|Автоматическое изменение размеров — это функция времени выполнения.|Это значит, что она не может использоваться для увеличения или уменьшения размеров элемента управления без последующих изменений.|  
|При изменении размеров элемента управления значение его свойства <xref:System.Windows.Forms.Control.Location%2A> всегда остается постоянным.|Если размеры элемента управления изменяются в соответствии с содержимым, он растягивается вправо и вниз.  Элементы управления не могут растягиваться влево.|  
|Если свойство <xref:System.Windows.Forms.Control.AutoSize%2A> имеет значение `true`, учитываются значения свойств <xref:System.Windows.Forms.Control.Dock%2A> и <xref:System.Windows.Forms.Control.Anchor%2A>.|Значение свойства <xref:System.Windows.Forms.Control.Location%2A> элемента управления корректируется.<br /><br /> **Note** Элемент управления <xref:System.Windows.Forms.Label> является исключением из этого правила.  При присвоении свойству <xref:System.Windows.Forms.Control.AutoSize%2A> закрепленного элемента управления <xref:System.Windows.Forms.Label> значения `true` элемент управления <xref:System.Windows.Forms.Label> не растягивается.|  
|Свойства <xref:System.Windows.Forms.Control.MaximumSize%2A> и <xref:System.Windows.Forms.Control.MinimumSize%2A> элемента управления учитываются вне зависимости от значения его свойства <xref:System.Windows.Forms.Control.AutoSize%2A>.|Свойство <xref:System.Windows.Forms.Control.AutoSize%2A> не оказывает влияния на значения свойств <xref:System.Windows.Forms.Control.MaximumSize%2A> и <xref:System.Windows.Forms.Control.MinimumSize%2A>.|  
|Минимальный размер по умолчанию не устанавливается.|Это означает, что если в соответствии со свойством <xref:System.Windows.Forms.Control.AutoSize%2A> размеры элемента управления должны уменьшаться и в настоящий момент в нем нет содержимого, свойство <xref:System.Windows.Forms.Control.Size%2A> принимает значение 0,0.  В этом случае размеры элемента уменьшатся до точки, и он станет невидимым.|  
|Если в элементе управления не реализован метод <xref:System.Windows.Forms.Control.GetPreferredSize%2A>, метод <xref:System.Windows.Forms.Control.GetPreferredSize%2A> возвращает последнее значение, присвоенное свойству <xref:System.Windows.Forms.Control.Size%2A>.|Это означает, что присвоение свойству <xref:System.Windows.Forms.Control.AutoSize%2A> значения `true` не будет иметь никакого эффекта.|  
|Размеры элемента управления, размещенного в ячейке <xref:System.Windows.Forms.TableLayoutPanel>, всегда уменьшаются до размеров ячейки, пока не будет достигнуто значение свойства <xref:System.Windows.Forms.Control.MinimumSize%2A>.|Этот размер принудительно устанавливается как максимальный.  Это правило не распространяется на тот случай, когда ячейка является частью строки или столбца, для которого задано свойство <xref:System.Windows.Forms.SizeType>.|  
  
## Свойство AutoSizeMode  
 Свойство `AutoSizeMode` позволяет производить более тонкую настройку поведения свойства <xref:System.Windows.Forms.Control.AutoSize%2A> по умолчанию.  Свойство `AutoSizeMode` определяет способ изменения размера элемента управления в соответствии с содержимым.  Содержимое может представлять собой, например, текст в элементе управления <xref:System.Windows.Forms.Button> или дочерние элементы управления контейнера.  
  
 В следующей таблице приведены возможные параметры свойства <xref:System.Windows.Forms.AutoSizeMode> и соответствующее им поведение.  
  
|Значение свойства AutoSizeMode|Поведение|  
|------------------------------------|---------------|  
|GrowAndShrink|Размеры элемента управления увеличиваются или уменьшаются так, чтобы помещалось все содержимое.<br /><br /> Значения свойств <xref:System.Windows.Forms.Control.MinimumSize%2A> и <xref:System.Windows.Forms.Control.MaximumSize%2A> учитываются, но текущее значение свойства <xref:System.Windows.Forms.Control.Size%2A> игнорируется.<br /><br /> Поведение аналогично поведению элементов управления, имеющих свойство <xref:System.Windows.Forms.Control.AutoSize%2A>, но не имеющих свойства `AutoSizeMode`.|  
|GrowOnly|Размеры элемента управления могут увеличиваться так, чтобы помещалось все содержимое, однако уменьшаться могут только до значения, заданного свойством <xref:System.Windows.Forms.Control.Size%2A>.<br /><br /> Это значение по умолчанию для свойства `AutoSizeMode`.|  
  
## Элементы управления, поддерживающие свойство AutoSize  
 В следующей таблице перечислены элементы управления, поддерживающие свойства <xref:System.Windows.Forms.Control.AutoSize%2A> и `AutoSizeMode`.  
  
|Поддержка AutoSize|Тип элемента управления|  
|------------------------|-----------------------------|  
|-   Свойство <xref:System.Windows.Forms.Control.AutoSize%2A> поддерживается.<br />-   Свойство `AutoSizeMode` отсутствует.|<xref:System.Windows.Forms.CheckBox><br /><br /> <xref:System.Windows.Forms.DomainUpDown><br /><br /> <xref:System.Windows.Forms.Label><br /><br /> <xref:System.Windows.Forms.LinkLabel><br /><br /> <xref:System.Windows.Forms.MaskedTextBox> \(базовый класс <xref:System.Windows.Forms.TextBox>\)<br /><br /> <xref:System.Windows.Forms.NumericUpDown><br /><br /> <xref:System.Windows.Forms.RadioButton><br /><br /> <xref:System.Windows.Forms.TextBox><br /><br /> <xref:System.Windows.Forms.TrackBar>|  
|-   Свойство <xref:System.Windows.Forms.Control.AutoSize%2A> поддерживается.<br />-   Свойство `AutoSizeMode` поддерживается.|<xref:System.Windows.Forms.Button><br /><br /> <xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.FlowLayoutPanel><br /><br /> <xref:System.Windows.Forms.Form><br /><br /> <xref:System.Windows.Forms.GroupBox><br /><br /> <xref:System.Windows.Forms.Panel><br /><br /> <xref:System.Windows.Forms.TableLayoutPanel>|  
|-   Свойство <xref:System.Windows.Forms.Control.AutoSize%2A> отсутствует.|<xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.ComboBox><br /><br /> <xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DateTimePicker><br /><br /> <xref:System.Windows.Forms.ListBox><br /><br /> <xref:System.Windows.Forms.ListView><br /><br /> <xref:System.Windows.Forms.MaskedTextBox><br /><br /> <xref:System.Windows.Forms.MonthCalendar><br /><br /> <xref:System.Windows.Forms.ProgressBar><br /><br /> <xref:System.Windows.Forms.PropertyGrid><br /><br /> <xref:System.Windows.Forms.RichTextBox><br /><br /> <xref:System.Windows.Forms.SplitContainer><br /><br /> <xref:System.Windows.Forms.TabControl><br /><br /> <xref:System.Windows.Forms.TabPage><br /><br /> <xref:System.Windows.Forms.TreeView><br /><br /> <xref:System.Windows.Forms.WebBrowser><br /><br /> <xref:System.Windows.Forms.ScrollBar>|  
  
## AutoSize в среде разработки  
 В следующей таблице описываются способы изменения размеров элемента управления во время разработки в соответствии со значениями свойств <xref:System.Windows.Forms.Control.AutoSize%2A> и `AutoSizeMode`.  
  
 Чтобы определить, может ли пользователь изменять размер данного элемента управления, следует переопределить свойство <xref:System.Windows.Forms.Design.ControlDesigner.SelectionRules%2A>.  В следующей таблице выражение "не может" означает только <xref:System.Windows.Forms.Design.SelectionRules>, выражение "может" означает <xref:System.Windows.Forms.Design.SelectionRules> и <xref:System.Windows.Forms.Design.SelectionRules>.  
  
|Параметры свойства AutoSize|Операция изменения размера во время разработки|  
|---------------------------------|----------------------------------------------------|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> \= `true`<br />-   Свойство `AutoSizeMode` отсутствует.|Пользователь не может изменять размеры элемента управления во время разработки за исключением следующих элементов управления.<br /><br /> -   <xref:System.Windows.Forms.TextBox><br />-   <xref:System.Windows.Forms.MaskedTextBox><br />-   <xref:System.Windows.Forms.RichTextBox><br />-   <xref:System.Windows.Forms.TrackBar>|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> \= `true`<br />-   `AutoSizeMode` \= <xref:System.Windows.Forms.AutoSizeMode>|Пользователь не может изменять размеры элемента управления во время разработки.|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> \= `true`<br />-   `AutoSizeMode` \= <xref:System.Windows.Forms.AutoSizeMode>|Пользователь может изменять размеры элемента управления во время разработки.  Если задано значение свойства <xref:System.Windows.Forms.Control.Size%2A>, пользователь может только увеличивать размеры элемента управления.|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> \= `false`, либо свойство <xref:System.Windows.Forms.Control.AutoSize%2A> скрыто.|Пользователь может изменять размеры элемента управления во время разработки.|  
  
> [!NOTE]
>  В целях повышения производительности конструктор Windows Forms скрывает свойство <xref:System.Windows.Forms.Control.AutoSize%2A> класса <xref:System.Windows.Forms.Form>.  Во время разработки поведение формы соответствует значению свойства <xref:System.Windows.Forms.Control.AutoSize%2A> \= `false` вне зависимости от фактической настройки.  Во время выполнения оптимизация не производится, и свойство <xref:System.Windows.Forms.Control.AutoSize%2A> применяется в соответствии с фактическим значением.  
  
## См. также  
 <xref:System.Windows.Forms.Control.AutoSize%2A>   
 <xref:System.Windows.Forms.Control.PreferredSize%2A>   
 <xref:System.Windows.Forms.Control.GetPreferredSize%2A>