---
title: Устранение неполадок при использовании элемента управления DataRepeater (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, troubleshooting
ms.assetid: c0ab9469-eced-4f52-aa18-4bd8dd4f1a9a
ms.openlocfilehash: 7b045e1c45221cbde82c88286da8e698a763d844
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580607"
---
# <a name="troubleshooting-the-datarepeater-control-visual-studio"></a>Устранение неполадок при использовании элемента управления DataRepeater (Visual Studio)
В этом разделе перечислены распространенные проблемы, которые могут возникнуть при работе с <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.  
  
## <a name="datarepeater-keyboard-and-mouse-events-are-not-raised"></a>Не вызываются события DataRepeater клавиатуры и мыши  
 Некоторые <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> события элементов управления, таких как события клавиатуры и мыши, не вызываются. Это сделано намеренно. <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Сам элемент управления является контейнером для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> объектов и не может использоваться во время выполнения. <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> Не предоставляет события во время разработки. Таким образом Если щелкнуть элемент или нажатие клавиши, когда элемент имеет фокус не вызывают событие.  
  
 Чтобы это исключение возникает, когда <xref:System.Windows.Forms.Control.Padding%2A> свойству большой достаточно значение для предоставления края <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления. Таким образом щелкнув в предоставленном поле вызывает события мыши.  
  
 Чтобы устранить эту проблему, добавьте <xref:System.Windows.Forms.Panel> управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> раздел <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления, а затем добавьте остальные элементы управления для <xref:System.Windows.Forms.Panel>. Затем можно добавить код для <xref:System.Windows.Forms.Panel> элемента управления обработчики событий для события клавиатуры и мыши.  
  
## <a name="the-datarepeater-is-partially-hidden-behind-the-binding-navigator"></a>Элемент управления DataRepeater частично скрыт навигатором привязки  
 При первом добавлении <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления в форму, а затем добавьте элементы управления с привязкой к данным из **источников данных** окне <xref:System.Windows.Forms.BindingNavigator> может отображаться элемент управления на основе <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления. Это известное ограничение **источников данных** окна и согласуется с поведением других элементов управления, такие как <xref:System.Windows.Forms.DataGridView> элемента управления.  
  
 Вы можете поместить <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> ниже, чем <xref:System.Windows.Forms.BindingNavigator> управления во время разработки, или добавьте код, аналогичный следующему в `Load` обработчик событий.  
  
```vb  
DataRepeater1.Top = ProductsBindingNavigator.Height  
```  
  
```csharp  
dataRepeater1.Top = productsBindingNavigator.Height;  
```  
  
## <a name="controls-are-not-displayed-correctly-at-run-time"></a>Элементы управления не отображаются правильно во время выполнения  
 Некоторые элементы управления в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> ожидаемым образом во время выполнения элемент управления может не отображаться. Процесс, используемый для копирования элементов управления из <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> не всегда могут определить все свойства всех элементов управления. Например, если добавить несвязанный <xref:System.Windows.Forms.ListBox> управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления во время разработки и заполнить его <xref:System.Windows.Forms.ListBox.Items%2A> коллекцию строк, со списком <xref:System.Windows.Forms.ListBox> будет пустым во время выполнения. Это обусловлено процесса клонирования не может учитывать <xref:System.Windows.Forms.ListBox.Items%2A> свойство.  
  
 Таких проблем можно исправить, восстановив отсутствующие свойства в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned> событие, которое происходит после завершения клонирования по умолчанию. В следующем примере показано, как восстановить <xref:System.Windows.Forms.ListBox.Items%2A> коллекцию <xref:System.Windows.Forms.ListBox> контролировать <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned> обработчик событий.  
  
 [!code-csharp[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/troubleshooting-the-datarepeater-control-visual-studio_1.cs)]
 [!code-vb[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/troubleshooting-the-datarepeater-control-visual-studio_1.vb)]  
  
## <a name="the-selection-symbol-on-the-item-header-is-missing"></a>Отсутствует символ выделения в заголовке элемента  
 При изменении <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> свойство заголовка элемента в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления, некоторые цветов может вызвать исчезновение символа выделения. Изменение <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> свойство также может вызывать символа выделения.  
  
 Невозможно изменить цвет и размер символа выделения.  
  
-   Если задать <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> для <xref:System.Drawing.Color.White%2A>, при первоначальном выборе элемента символ выделения не будут видны.  
  
-   Если задать <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> для <xref:System.Drawing.Color.Black%2A>, символ выделения не будут видны при выборе элемента управления и карандаша не будут видны, когда элемент управления находится в режиме редактирования.  
  
-   Если <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> свойству присваивается значение, которое меньше 11, не будут отображаться значки индикатора в заголовке элемента.  
  
 Можно предоставить собственный символ заголовка и Выбор элемента с помощью <xref:System.Windows.Forms.PictureBox> управление и мониторинг <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A> свойство <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> событие <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления. Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>.  
  
## <a name="see-also"></a>См. также
- [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [Практическое руководство. Отображение связанных данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)
- [Практическое руководство. Отображение несвязанных элементов управления в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)
- [Практическое руководство. Изменение макета элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)
- [Практическое руководство. Изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
- [Практическое руководство. Отображение заголовков элементов в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)
- [Практическое руководство. Запрещение возможности добавления и удаления элементов DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)
- [Практическое руководство. Поиск данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)
- [Практическое руководство. Создать форму «основной/подробности» с помощью двух элементов управления DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)
