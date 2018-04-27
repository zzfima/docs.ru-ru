---
title: Общие сведения об элементе управления SplitContainer (Windows Forms)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SplitContainer
helpviewer_keywords:
- SplitContainer control [Windows Forms], about SplitContainer control
ms.assetid: 6de5a5f7-97a5-402d-be6d-7e2785483db5
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a553ea1b6dae24b4a0c3bd169edccbd9b52c5203
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="splitcontainer-control-overview-windows-forms"></a>Общие сведения об элементе управления SplitContainer (Windows Forms)
Элемент управления Windows Forms <xref:System.Windows.Forms.SplitContainer> состоит из двух панелей, разделенных подвижной полосой. При наведении указателя мыши на полосу его форма изменяется, показывая, что полоса является перемещаемой.  
  
> [!IMPORTANT]
>  В **элементов**, <xref:System.Windows.Forms.SplitContainer> элемент управления заменяет <xref:System.Windows.Forms.Splitter> , присутствующий в предыдущей версии Visual Studio. Элемент управления <xref:System.Windows.Forms.SplitContainer> намного предпочтительнее, чем элемент управления <xref:System.Windows.Forms.Splitter>. <xref:System.Windows.Forms.Splitter> Класс по-прежнему включен в [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для обеспечения совместимости с существующими приложениями, но настоятельно рекомендуется использовать <xref:System.Windows.Forms.SplitContainer> управления для новых проектов.  
  
 С <xref:System.Windows.Forms.SplitContainer> элемента управления, можно создавать сложные пользовательские интерфейсы; часто выбор на одной панели определяет объекты, отображаемые на панели «». Такой подход является весьма эффективным для отображения и просмотра информации. Две панели для сбора информации в областях и панель или «, «разделитель упрощают изменение размера панелей.  
  
 Существует несколько <xref:System.Windows.Forms.SplitContainer> управления могут быть вложенными, со вторым <xref:System.Windows.Forms.SplitContainer> элемента управления, имеет горизонтальную ориентацию, создание верхней и нижней панелях.  
  
 Имейте в виду, что <xref:System.Windows.Forms.SplitContainer> управления клавиатуры по умолчанию, пользователи могут используйте клавиши со стрелками для перемещения разделителя, если <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> свойству `false`.  
  
 <xref:System.Windows.Forms.SplitContainer.Orientation%2A> Свойство <xref:System.Windows.Forms.SplitContainer> управления определяет направление разделителя, а не самого элемента управления. Таким образом, если это свойство имеет значение <xref:System.Windows.Forms.Orientation.Vertical>, выполняется разделителя сверху вниз, создание левой и правой панели.  
  
 Кроме того, имейте в виду, значение <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> свойство изменяется в зависимости от значения <xref:System.Windows.Forms.SplitContainer.Orientation%2A> свойство. Дополнительные сведения см. в разделе <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> свойство.  
  
 Также можно ограничить размер и перемещение <xref:System.Windows.Forms.SplitContainer> элемента управления. <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> Свойство определяет, какая панель останется один и тот же размер после <xref:System.Windows.Forms.SplitContainer> размера элемента управления и <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> свойство определяет, является ли разделитель перемещаемым, клавиатуры или мыши.  
  
> [!NOTE]
>  Даже если <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> свойству `true`, разделителя может по-прежнему переместить программными средствами, например с помощью <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> свойство.  
  
 Наконец, каждая панель <xref:System.Windows.Forms.SplitContainer> элемент управления имеет свойства, чтобы определить его размер отдельных.  
  
## <a name="commonly-used-properties-methods-and-events"></a>Часто используемые свойства, методы и события  
  
|name|Описание|  
|----------|-----------------|  
|Свойство <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A>|Определяет, какая панель останется тем же размером после <xref:System.Windows.Forms.SplitContainer> размер элемента управления.|  
|Свойство <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>|Определяет, если разделитель может быть перемещен с помощью клавиатуры или мыши.|  
|Свойство <xref:System.Windows.Forms.SplitContainer.Orientation%2A>|Определяет, если расположение разделителя вертикально или горизонтально.|  
|Свойство <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>|Определяет расстояние в пикселях от левой или верхней границы для перемещаемой полосы-разделителя.|  
|Свойство <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>|Определяет минимальное расстояние в пикселях, что разделитель может быть перемещен пользователем.|  
|Свойство <xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A>|Определяет ширину в пикселях от разделителя.|  
|Событие <xref:System.Windows.Forms.SplitContainer.SplitterMoving>|Происходит при перемещении разделителя.|  
|Событие <xref:System.Windows.Forms.SplitContainer.SplitterMoved>|Происходит, когда перемещения разделителя.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.SplitContainer>  
 [Элемент управления SplitContainer](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)  
 [Пример элемента управления SplitContainer](http://msdn.microsoft.com/library/9015fad0-7108-4d85-a83a-a72d038c4f65)
