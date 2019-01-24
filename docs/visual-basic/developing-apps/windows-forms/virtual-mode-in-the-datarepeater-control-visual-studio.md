---
title: Виртуальные режим в элементе управления DataRepeater (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- virtual data binding [Visual Basic]
- DataRepeater
- DataRepeater, virtual mode
ms.assetid: 5fb805dc-2d8b-4139-b1e3-86e4c2667221
ms.openlocfilehash: 3988c16746606de9f20f9a66b87539b6cea04758
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700810"
---
# <a name="virtual-mode-in-the-datarepeater-control-visual-studio"></a>Виртуальные режим в элементе управления DataRepeater (Visual Studio)
При необходимости отображать большие объемы табличные данные в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления, можно повысить производительность, задав <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> свойства `True` и явного управления элемента управления взаимодействия со своим источником данных. <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Управления предусмотрено несколько событий, которые можно обрабатывать при взаимодействии с источником данных и отображения данных во время выполнения.  
  
## <a name="how-virtual-mode-works"></a>Как работает виртуальный режим  
 Наиболее распространенным сценарием для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления является привязка дочерних элементов управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> в данных источника во время разработки и разрешить <xref:System.Windows.Forms.BindingSource> для передачи данных туда и обратно при необходимости. При использовании виртуального режима, эти элементы управления не привязаны к источнику данных и данные передаются назад и вперед в базовом источнике данных во время выполнения.  
  
 При <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> свойству `True`, создать пользовательский интерфейс, добавив элементы управления из **элементов** вместо добавления привязанные элементы управления из **источников данных** окна.  
  
 События создаются на основе элемента управления, и необходимо добавить код для обработки данных. При создании нового <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> прокручена в представление, <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> событие возникает один раз для каждого элемента управления, и вы должны предоставить значения для каждого элемента управления в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> обработчик событий.  
  
 При изменении данных в одном из элементов управления пользователем, <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> событие, и необходимо проверить данные и сохраните его в источник данных.  
  
 Если пользователь добавляет новый элемент, <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded> события. Используйте этот обработчик событий для создания новой записи в источнике данных. Во избежание экспорта непреднамеренных изменений, необходимо также отслеживать <xref:System.Windows.Forms.Control.KeyDown> событие для каждого элемента управления и вызвать <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A> при нажатии клавиши ESC.  
  
 Если изменения источника данных, можно обновить <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления, используя <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> и <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> методы. Оба метода должен вызываться в порядке.  
  
 Наконец, необходимо реализовать обработчики событий для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved> событие, возникающее при удалении элемента и при необходимости для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletingItems> и <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletedItems> событий, которые происходят каждый раз, когда пользователь удаляет элемент с помощью клавиши DELETE.  
  
## <a name="implementing-virtual-mode"></a>Реализация виртуального режима  
 Ниже перечислены шаги, которые необходимы для реализации виртуальный режим.  
  
#### <a name="to-implement-virtual-mode"></a>Реализация виртуального режима  
  
1.  Перетащите <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления из **Visual Basic PowerPacks** вкладке **элементов** в форму или контейнерный элемент управления. Задайте для свойства <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> значение `True`.  
  
2.  Перетаскивайте элементы управления из **элементов** область шаблона элемента (верхняя область) из <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления. Вам потребуется один элемент управления для каждого поля в источнике данных, который вы хотите отобразить.  
  
3.  Реализуйте обработчик <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> событий для предоставления значений для каждого элемента управления. Это событие возникает при создании нового <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> прокручена в представление. Код будет выглядеть примерно так, что для источника данных с именем `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_1.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_1.cs)]  
  
4.  Реализуйте обработчик <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> событий для хранения данных. Это событие возникает, когда пользователь фиксирует изменения для дочернего элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>. Код будет выглядеть примерно так, что для источника данных с именем `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_2.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_2.cs)]  
  
5.  Реализовать обработчик для каждого дочернего элемента управления <xref:System.Windows.Forms.Control.KeyDown> событий и монитор клавишу ESC. Вызовите <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A> метод, чтобы запретить <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> возникновения события. Код будет выглядеть следующим образом.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_3.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_3.cs)]  
  
6.  Реализовать обработчик для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded> событий. Это событие возникает, когда пользователь добавляет новый элемент для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления. Код будет выглядеть примерно так, что для источника данных с именем `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_4.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_4.cs)]  
  
7.  Реализовать обработчик для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved> событий. Это событие возникает, когда пользователь удаляет существующий элемент. Код будет выглядеть примерно так, что для источника данных с именем `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_5.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_5.cs)]  
  
8.  Для проверки на уровне элемента управления при необходимости реализовать обработчики для <xref:System.Windows.Forms.Control.Validating> события дочерних элементов управления. Код будет выглядеть следующим образом.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#6](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_6.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#6](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_6.cs)]  
  
## <a name="see-also"></a>См. также
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>
- [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
