---
title: Устранение неполадок при использовании элемента управления DataRepeater (Visual Studio)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, troubleshooting
ms.assetid: c0ab9469-eced-4f52-aa18-4bd8dd4f1a9a
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2d630dbf8601eeddd5ce3ea02696891a1087f71f
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/10/2018
---
# <a name="troubleshooting-the-datarepeater-control-visual-studio"></a>Устранение неполадок при использовании элемента управления DataRepeater (Visual Studio)
В этом разделе перечислены распространенные проблемы, которые могут возникнуть при работе с <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.  
  
## <a name="datarepeater-keyboard-and-mouse-events-are-not-raised"></a>Не формируются событий мыши и клавиатуры DataRepeater  
 Некоторые <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> события элементов управления, таких как события клавиатуры и мыши, не вызываются. Это сделано намеренно. <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Сам элемент управления является контейнером для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> объектов и не доступен во время выполнения. <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> Не предоставляет события во время разработки. Таким образом при выборе пункта меню или нажатие клавиши, когда элемент получает фокус не вызывают событие.  
  
 Чтобы это исключение возникает, когда <xref:System.Windows.Forms.Control.Padding%2A> свойство имеет значение большого достаточно значение для предоставления края <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления. Таким образом щелкнув в предоставленном поле вызывает события мыши.  
  
 Чтобы устранить эту проблему, добавьте <xref:System.Windows.Forms.Panel> управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> раздел <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления, а затем добавьте остальные элементы управления, <xref:System.Windows.Forms.Panel>. Затем можно добавить код для <xref:System.Windows.Forms.Panel> элемента управления обработчики событий для события клавиатуры и мыши.  
  
## <a name="the-datarepeater-is-partially-hidden-behind-the-binding-navigator"></a>Элемент управления DataRepeater частично скрыт навигатором привязки  
 При первом добавлении <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления в форму, а затем добавьте элементы управления с привязкой к данным из **источники данных** окна, <xref:System.Windows.Forms.BindingNavigator> управления могут отображаться поверх <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления. Это известное ограничение **источники данных** окна и согласуется с поведением других элементов управления, таких как <xref:System.Windows.Forms.DataGridView> элемента управления.  
  
 Можно либо переместить <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> ниже, чем <xref:System.Windows.Forms.BindingNavigator> во время разработки, или же добавьте код, аналогичный следующему в `Load` обработчика событий.  
  
```vb  
DataRepeater1.Top = ProductsBindingNavigator.Height  
```  
  
```csharp  
dataRepeater1.Top = productsBindingNavigator.Height;  
```  
  
## <a name="controls-are-not-displayed-correctly-at-run-time"></a>Элементы управления отображаются правильно во время выполнения  
 Некоторые элементы управления в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемент управления может не отображаться должным образом во время выполнения. Процесс, используемый для копирования элементов управления из <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> не всегда можно определить все свойства всех элементов управления. Например, если добавить несвязанный <xref:System.Windows.Forms.ListBox> управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления во время разработки и заполнить его <xref:System.Windows.Forms.ListBox.Items%2A> набор со списком строк, <xref:System.Windows.Forms.ListBox> будет пустым во время выполнения. Это, поскольку процесс клонирования не может учитывать <xref:System.Windows.Forms.ListBox.Items%2A> свойство.  
  
 Проблемы, например, это можно исправить, восстановив потерянные свойства в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned> событие, возникающее после завершения клонирования по умолчанию. Ниже приведен пример, как исправить <xref:System.Windows.Forms.ListBox.Items%2A> коллекцию <xref:System.Windows.Forms.ListBox> управления в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned> обработчика событий.  
  
 [!code-csharp[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/troubleshooting-the-datarepeater-control-visual-studio_1.cs)]
 [!code-vb[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/troubleshooting-the-datarepeater-control-visual-studio_1.vb)]  
  
## <a name="the-selection-symbol-on-the-item-header-is-missing"></a>Отсутствует символ выделения заголовка элемента  
 При изменении <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> свойство элемента заголовка в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления, некоторые цветов может вызвать исчезновение символа выделения. Изменение <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> свойство также может вызвать исчезновение символа выделения.  
  
 Нельзя изменить цвет и размер символа выделения.  
  
-   Если задать <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> для <xref:System.Drawing.Color.White%2A>, при первоначальном выборе элемента символ выделения не будут видны.  
  
-   Если задать <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> для <xref:System.Drawing.Color.Black%2A>, символ выделения не будут видны при выборе элемента управления, и если элемент управления находится в режиме редактирования символ карандаша не будут видны.  
  
-   Если <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> свойству присвоено значение, которое меньше 11, не будут отображаться значки индикатора в заголовке элементов.  
  
 Можно предоставить собственную символ заголовок "и" Выбор элемента с помощью <xref:System.Windows.Forms.PictureBox> управление и мониторинг <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A> свойство <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> событие <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления. Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Пошаговое руководство. Отображение связанных данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [Пошаговое руководство. Отображение несвязанных элементов управления в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [Практическое руководство. Изменение структуры элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)  
 [Практическое руководство. Изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [Пошаговое руководство. Отображение заголовков элементов в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)  
 [Пошаговое руководство. Запрещение возможности добавления и удаления элементов DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)  
 [Практическое руководство. Поиск данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)  
 [Как: создать Главная и подчиненная формы с помощью двух элементов управления DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)
