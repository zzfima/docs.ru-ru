---
title: Общие сведения о компоненте SplitContainer
ms.date: 03/30/2017
f1_keywords:
- SplitContainer
helpviewer_keywords:
- SplitContainer control [Windows Forms], about SplitContainer control
ms.assetid: 6de5a5f7-97a5-402d-be6d-7e2785483db5
ms.openlocfilehash: 5cb5240ed4ebe3e27c20844681068711c222e9a9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742920"
---
# <a name="splitcontainer-control-overview-windows-forms"></a>Общие сведения об элементе управления SplitContainer (Windows Forms)
Элемент управления Windows Forms <xref:System.Windows.Forms.SplitContainer> состоит из двух панелей, разделенных подвижной полосой. При наведении указателя мыши на полосу его форма изменяется, показывая, что полоса является перемещаемой.  
  
> [!IMPORTANT]
> В **панели элементов**элемент управления <xref:System.Windows.Forms.SplitContainer> заменяет элемент управления <xref:System.Windows.Forms.Splitter>, который был в предыдущей версии Visual Studio. Элемент управления <xref:System.Windows.Forms.SplitContainer> намного предпочтительнее, чем элемент управления <xref:System.Windows.Forms.Splitter>. Класс <xref:System.Windows.Forms.Splitter> по-прежнему имеется в .NET Framework для обеспечения совместимости с существующими приложениями, но для новых проектов настоятельно рекомендуется использовать элемент управления <xref:System.Windows.Forms.SplitContainer>.  
  
 С помощью элемента управления <xref:System.Windows.Forms.SplitContainer> можно создавать сложные пользовательские интерфейсы. часто выбор на одной панели определяет, какие объекты отображаются на другой панели. Такой подход является весьма эффективным для отображения и просмотра информации. Наличие двух панелей позволяет объединять информацию в областях, а линейчатые или разделители облегчают пользователям изменение размера панелей.  
  
 Более одного элемента управления <xref:System.Windows.Forms.SplitContainer> также может быть вложенным, второй <xref:System.Windows.Forms.SplitContainer> ориентирован горизонтально, для создания верхних и нижних панелей.  
  
 Помните, что элемент управления <xref:System.Windows.Forms.SplitContainer> доступен по умолчанию. Пользователи могут нажать клавиши со СТРЕЛКАми, чтобы переместить разделитель, если свойство <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> имеет значение `false`.  
  
 Свойство <xref:System.Windows.Forms.SplitContainer.Orientation%2A> элемента управления <xref:System.Windows.Forms.SplitContainer> определяет направление разделителя, а не сам элемент управления. Следовательно, если это свойство имеет значение <xref:System.Windows.Forms.Orientation.Vertical>, разделитель выполняется сверху вниз, создавая левую и правую панели.  
  
 Кроме того, имейте в виду, что значение свойства <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> зависит от значения свойства <xref:System.Windows.Forms.SplitContainer.Orientation%2A>. Дополнительные сведения см. в разделе <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> свойство.  
  
 Можно также ограничить размер и перемещение элемента управления <xref:System.Windows.Forms.SplitContainer>. Свойство <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> определяет, какая панель будет иметь тот же размер после изменения размера элемента управления <xref:System.Windows.Forms.SplitContainer>, а свойство <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> определяет, является ли разделитель перемещаемым с помощью клавиатуры или мыши.  
  
> [!NOTE]
> Даже если свойство <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> имеет значение `true`, разделитель может по-прежнему перемещаться программно; Например, с помощью свойства <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>.  
  
 Наконец, каждая панель элемента управления <xref:System.Windows.Forms.SplitContainer> имеет свойства для определения его отдельного размера.  
  
## <a name="commonly-used-properties-methods-and-events"></a>Часто используемые свойства, методы и события  
  
|Name|Описание|  
|----------|-----------------|  
|Свойство<xref:System.Windows.Forms.SplitContainer.FixedPanel%2A>|Определяет, какая панель будет иметь тот же размер после изменения размера элемента управления <xref:System.Windows.Forms.SplitContainer>.|  
|Свойство<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>|Определяет, можно ли перемещать разделитель с помощью клавиатуры или мыши.|  
|Свойство<xref:System.Windows.Forms.SplitContainer.Orientation%2A>|Определяет, расположен ли разделитель вертикально или горизонтально.|  
|Свойство<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>|Определяет расстояние в пикселях от левого или верхнего края до перемещаемой полосы разделения.|  
|Свойство<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>|Определяет минимальное расстояние (в пикселях), в течение которого разделитель может быть перемещен пользователем.|  
|Свойство<xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A>|Определяет толщину (в пикселях) разделителя.|  
|Событие<xref:System.Windows.Forms.SplitContainer.SplitterMoving>|Происходит при перемещении разделителя.|  
|Событие<xref:System.Windows.Forms.SplitContainer.SplitterMoved>|Происходит при перемещении разделителя.|  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.SplitContainer>
- [Элемент управления SplitContainer](splitcontainer-control-windows-forms.md)
- [Пример элемента управления SplitContainer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/0ffz7d1b(v=vs.90))
