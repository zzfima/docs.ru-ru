---
title: "Практическое руководство. Привязка элементов управления в формах Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Anchor property [Windows Forms], enabling resizable forms
- Windows Forms controls, screen resolutions
- resizing forms [Windows Forms]
- Windows Forms controls, size
- screen resolution and control display
- controls [Windows Forms], anchoring
- forms [Windows Forms], resizing
- Windows Forms, resizing
- controls [Windows Forms], positioning
ms.assetid: 59ea914f-fbd3-427a-80fe-decd02f7ae6d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7fcc672dea63bc74980b4829129f530de9cc72ec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-anchor-controls-on-windows-forms"></a>Практическое руководство. Привязка элементов управления в формах Windows Forms
При разработке формы, пользователь может сделать во время выполнения, элементы управления формы следует изменять размер и положение должным образом. Чтобы изменить размер элементов управления, динамически с формой, можно использовать <xref:System.Windows.Forms.Control.Anchor%2A> свойства элементов управления Windows Forms. <xref:System.Windows.Forms.Control.Anchor%2A> Свойство определяет положение прикрепления для элемента управления. Если элемент управления привязан к форме и изменении размера формы, элемент управления поддерживает расстояние между элементом управления и положениями прикрепления. Например, если у вас есть <xref:System.Windows.Forms.TextBox> управления, привязанный к левое, правое и нижней границ формы как формы изменяется, <xref:System.Windows.Forms.TextBox> элемент управления по горизонтали таким образом, чтобы сохранить одинаковое расстояние до правой и левой сторон формы. Кроме того элемент управления размещает сам по вертикали, чтобы ее расположение всегда такое же расстояние от нижнего края формы. Если элемент управления не привязан и изменении размера формы, изменяется положение элемента управления относительно края формы.  
  
 <xref:System.Windows.Forms.Control.Anchor%2A> Свойство взаимодействует с <xref:System.Windows.Forms.Control.AutoSize%2A> свойство. Дополнительные сведения см. в разделе [Общие](../../../../docs/framework/winforms/controls/autosize-property-overview.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-anchor-a-control-on-a-form"></a>Чтобы привязать элемент управления на форме  
  
1.  Выберите элемент управления, который нужно закрепить.  
  
    > [!NOTE]
    >  Можно прикрепить несколько элементов одновременно, при нажатой клавише CTRL, щелкните каждый элемент управления, чтобы выбрать его и выполнив оставшуюся часть этой процедуры.  
  
2.  В **свойства** окно, щелкните стрелку справа от <xref:System.Windows.Forms.Control.Anchor%2A> свойство.  
  
     Откроется редактор покажет крестик.  
  
3.  Чтобы задать элемент привязки, щелкните сверху, слева, справа или нижнюю часть крестика.  
  
     Элементы управления привязаны к верхней и оставить по умолчанию.  
  
4.  Чтобы очистить стороны элемента управления, была привязана, щелкните соответствующую часть крестика.  
  
5.  Чтобы закрыть <xref:System.Windows.Forms.Control.Anchor%2A> редактор свойств, нажмите кнопку <xref:System.Windows.Forms.Control.Anchor%2A> снова имя свойства.  
  
 При отображении формы во время выполнения элемент управления меняет размер, оставаясь на одинаковом расстоянии от края формы. Расстояние от прикрепленного края всегда остается равным расстоянию, определенному при расположении элемента управления в конструкторе Windows Forms.  
  
> [!NOTE]
>  Некоторые элементы управления, такие как <xref:System.Windows.Forms.ComboBox> контроля, ограничен по высоте. Прикреплением элемента управления в нижней части формы или контейнера нельзя к превышению ограничения высоты.  
  
 Наследуемые элементы управления должны быть `Protected` могли быть прикреплены. Чтобы изменить уровень доступа элемента управления, установите его `Modifiers` свойство в **свойства** окна.  
  
## <a name="see-also"></a>См. также  
 [Элементы управления Windows Forms](../../../../docs/framework/winforms/controls/index.md)  
 [Упорядочение элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Свойство AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [Практическое руководство. Закрепление элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)  
 [Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [Пошаговое руководство. Создание структуры элементов управления Windows Forms с помощью свойств Padding, Margins и AutoSize](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)
