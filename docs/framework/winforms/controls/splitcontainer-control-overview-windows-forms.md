---
title: "Общие сведения об элементе управления SplitContainer (Windows Forms) | Microsoft Docs"
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
  - "SplitContainer"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "SplitContainer - элемент управления [Windows Forms], сведения об элементе управления SplitContainer"
ms.assetid: 6de5a5f7-97a5-402d-be6d-7e2785483db5
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Общие сведения об элементе управления SplitContainer (Windows Forms)
Элемент управления Windows Forms <xref:System.Windows.Forms.SplitContainer> состоит из двух панелей, разделенных подвижной полосой.  При наведении указателя мыши на строку, форма курсора изменяется, чтобы показать, что строка является перемещаемой.  
  
> [!IMPORTANT]
>  В **Панели инструментов** элемент управления <xref:System.Windows.Forms.SplitContainer> заменяет элемент <xref:System.Windows.Forms.Splitter>, присутствующий в предыдущей версии [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  Элемент управления <xref:System.Windows.Forms.SplitContainer> является намного более предпочтительным, чем <xref:System.Windows.Forms.Splitter>.  Класс <xref:System.Windows.Forms.Splitter> по\-прежнему присутствует в [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для обеспечения совместимости с существующими приложениями, но для новых проектов настоятельно рекомендуется использовать элемент управления <xref:System.Windows.Forms.SplitContainer>.  
  
 При помощи элемента управления <xref:System.Windows.Forms.SplitContainer> можно создавать сложные пользовательские интерфейсы. Часто, выбор в одной панели определяет объекты, отображаемые в другой панели.  Это сочетание является весьма эффективным для отображения и просмотра информации.  Две панели для сбора информации в областях, а также строка или разделитель упрощают изменение размера панелей.  
  
 Кроме того, допускается вложение более чем одного элемента управления <xref:System.Windows.Forms.SplitContainer>, причем для второго элемента управления <xref:System.Windows.Forms.SplitContainer> может устанавливаться ориентация по горизонтали, что позволяет создать верхнюю и нижнюю панель.  
  
 Обратите внимание, что по умолчанию управление элементом <xref:System.Windows.Forms.SplitContainer> осуществляется с клавиатуры. Пользователь может использовать клавиши со стрелками для перемещения разделителя, если свойству <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> присвоено значение `false`.  
  
 Свойство <xref:System.Windows.Forms.SplitContainer.Orientation%2A> элемента управления <xref:System.Windows.Forms.SplitContainer> определяет направление разделителя, а не самого элемента управления.  Соответственно, если этому свойству присвоено значение <xref:System.Windows.Forms.Orientation>, разделитель будет направлен сверху вниз, разделяя область на левую и правую панели.  
  
 Кроме того, обратите внимание, что значение свойства <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> изменяется в зависимости от значения свойства <xref:System.Windows.Forms.SplitContainer.Orientation%2A>.  Дополнительные сведения см. в описании свойства <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A>.  
  
 Можно также ограничить размер и перемещение элемента управления <xref:System.Windows.Forms.SplitContainer>.  Свойство <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> определяет, какая из панелей будет сохранять размер при изменении размера элемента управления <xref:System.Windows.Forms.SplitContainer>, в то время как свойство <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> определяет возможность перемещения разделителя с помощью клавиатуры или мыши.  
  
> [!NOTE]
>  Даже если свойство <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> имеет значение `true`, разделитель можно перемещать программным способом, например с помощью свойства <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>.  
  
 Наконец, каждая панель элемента управления <xref:System.Windows.Forms.SplitContainer> имеет свойства, определяющие размер соответствующей панели.  
  
## Часто используемые свойства, методы и события  
  
|Имя|Описание|  
|---------|--------------|  
|Свойство <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A>|Определяет, какая из панелей будет сохранять размер при изменении размера элемента управления <xref:System.Windows.Forms.SplitContainer>.|  
|Свойство <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>|Определяет возможность перемещения разделителя при помощи клавиатуры или мыши.|  
|Свойство <xref:System.Windows.Forms.SplitContainer.Orientation%2A>|Определяет расположение разделителя по вертикали или по горизонтали.|  
|Свойство <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>|Определяет расстояние от левой или верхней границы до перемещаемой полосы\-разделителя в пикселях.|  
|Свойство <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>|Определяет минимальное расстояние, на которое разделитель может быть перемещен пользователем, в пикселях.|  
|Свойство <xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A>|Определяет толщину разделителя в пикселях.|  
|Событие <xref:System.Windows.Forms.SplitContainer.SplitterMoving>|Происходит при перемещении разделителя.|  
|Событие <xref:System.Windows.Forms.SplitContainer.SplitterMoved>|Происходит по завершении перемещения разделителя.|  
  
## См. также  
 <xref:System.Windows.Forms.SplitContainer>   
 [Элемент управления SplitContainer](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)   
 [SplitContainer Control Sample](http://msdn.microsoft.com/ru-ru/9015fad0-7108-4d85-a83a-a72d038c4f65)