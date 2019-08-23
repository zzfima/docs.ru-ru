---
title: Общие сведения об элементе управления SplitContainer (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- SplitContainer
helpviewer_keywords:
- SplitContainer control [Windows Forms], about SplitContainer control
ms.assetid: 6de5a5f7-97a5-402d-be6d-7e2785483db5
ms.openlocfilehash: 76299d9bbd2b3eac4e765dfacf579c9979721fff
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963209"
---
# <a name="splitcontainer-control-overview-windows-forms"></a>Общие сведения об элементе управления SplitContainer (Windows Forms)
Элемент управления Windows Forms <xref:System.Windows.Forms.SplitContainer> состоит из двух панелей, разделенных подвижной полосой. При наведении указателя мыши на полосу его форма изменяется, показывая, что полоса является перемещаемой.  
  
> [!IMPORTANT]
> На **панели элементов** <xref:System.Windows.Forms.SplitContainer> элемент управления заменяет <xref:System.Windows.Forms.Splitter> элемент управления, который был в предыдущей версии Visual Studio. Элемент управления <xref:System.Windows.Forms.SplitContainer> намного предпочтительнее, чем элемент управления <xref:System.Windows.Forms.Splitter>. Класс <xref:System.Windows.Forms.Splitter> по-прежнему имеется в .NET Framework для обеспечения совместимости с существующими приложениями, но для новых проектов настоятельно рекомендуется использовать элемент управления <xref:System.Windows.Forms.SplitContainer>.  
  
 С помощью <xref:System.Windows.Forms.SplitContainer> элемента управления можно создавать сложные пользовательские интерфейсы; часто выбор на одной панели определяет, какие объекты отображаются на другой панели. Такой подход является весьма эффективным для отображения и просмотра информации. Наличие двух панелей позволяет объединять информацию в областях, а линейчатые или разделители облегчают пользователям изменение размера панелей.  
  
 Можно также вложить несколько <xref:System.Windows.Forms.SplitContainer> элементовуправленияспомощьювторогоэлементауправления,ориентированногопогоризонтали,длясозданияверхнихинижнихпанелей.<xref:System.Windows.Forms.SplitContainer>  
  
 Имейте в виду, <xref:System.Windows.Forms.SplitContainer> что по умолчанию элемент управления доступен по клавиатуре; пользователи могут нажимать клавиши со стрелками для <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> перемещения разделителя, если `false`свойство имеет значение.  
  
 <xref:System.Windows.Forms.SplitContainer.Orientation%2A> Свойство<xref:System.Windows.Forms.SplitContainer> элемента управления определяет направление разделителя, а не сам элемент управления. Таким образом, если для <xref:System.Windows.Forms.Orientation.Vertical>этого свойства задано значение, разделитель выполняется сверху вниз, создавая левую и правую панели.  
  
 Кроме того, имейте в виду, что значение <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> свойства зависит от значения <xref:System.Windows.Forms.SplitContainer.Orientation%2A> свойства. Дополнительные сведения см. в <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> разделе свойство.  
  
 Можно также ограничить размер и перемещение <xref:System.Windows.Forms.SplitContainer> элемента управления. Свойство определяет, какая панель будет иметь тот же размер <xref:System.Windows.Forms.SplitContainer> после <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> изменения размера элемента управления, а свойство определяет, является ли разделитель перемещаемым с помощью клавиатуры или мыши. <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A>  
  
> [!NOTE]
> Даже если <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> свойство имеет `true`значение, разделитель может быть перемещен программно, например с помощью <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> свойства.  
  
 Наконец, каждая панель <xref:System.Windows.Forms.SplitContainer> элемента управления имеет свойства для определения его отдельного размера.  
  
## <a name="commonly-used-properties-methods-and-events"></a>Часто используемые свойства, методы и события  
  
|name|Описание|  
|----------|-----------------|  
|Свойство <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A>|Определяет, какая панель будет иметь тот же размер после <xref:System.Windows.Forms.SplitContainer> изменения размера элемента управления.|  
|Свойство <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>|Определяет, можно ли перемещать разделитель с помощью клавиатуры или мыши.|  
|Свойство <xref:System.Windows.Forms.SplitContainer.Orientation%2A>|Определяет, расположен ли разделитель вертикально или горизонтально.|  
|Свойство <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>|Определяет расстояние в пикселях от левого или верхнего края до перемещаемой полосы разделения.|  
|Свойство <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>|Определяет минимальное расстояние (в пикселях), в течение которого разделитель может быть перемещен пользователем.|  
|Свойство <xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A>|Определяет толщину (в пикселях) разделителя.|  
|Событие<xref:System.Windows.Forms.SplitContainer.SplitterMoving>|Происходит при перемещении разделителя.|  
|Событие<xref:System.Windows.Forms.SplitContainer.SplitterMoved>|Происходит при перемещении разделителя.|  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.SplitContainer>
- [Элемент управления SplitContainer](splitcontainer-control-windows-forms.md)
- [Пример элемента управления SplitContainer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/0ffz7d1b(v=vs.90))
