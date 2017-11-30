---
title: "Виртуальные режим в элементе управления DataRepeater (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- virtual data binding [Visual Basic]
- DataRepeater
- DataRepeater, virtual mode
ms.assetid: 5fb805dc-2d8b-4139-b1e3-86e4c2667221
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4c85ce4541e32991bfa09b1436385281d27ad355
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="virtual-mode-in-the-datarepeater-control-visual-studio"></a>Виртуальные режим в элементе управления DataRepeater (Visual Studio)
При необходимости для отображения табличных данных в больших объемах <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления, можно повысить производительность, задав <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> свойства `True` и явным образом Управление взаимодействием элемента управления с источником данных. <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Управления предоставляет несколько событий, которые можно обрабатывать при взаимодействии с источником данных и отображения данных, при необходимости во время выполнения.  
  
## <a name="how-virtual-mode-works"></a>Как работает виртуальный режим  
 Наиболее распространенным сценарием для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> является привязка дочерние элементы управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> данных источника во время разработки и разрешить <xref:System.Windows.Forms.BindingSource> для передачи данных туда и обратно при необходимости. При использовании виртуального режима для элементов управления не привязаны к источнику данных и данные передаются назад и вперед в базовом источнике данных во время выполнения.  
  
 При <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> свойству `True`, создайте пользовательский интерфейс, добавив элементы управления из **элементов** вместо добавления связанных элементов управления из **источники данных** окна.  
  
 События вызываются по принципу управления, и необходимо добавить код для управления отображением данных. При создании нового <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> в области просмотра, <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> событие происходит один раз для каждого элемента управления и необходимо указать значения для каждого элемента управления в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> обработчика событий.  
  
 При изменении данных в одном из элементов управления пользователем, <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> событие, и необходимо проверить данные и сохраните его в источник данных.  
  
 Если пользователь добавляет новый элемент <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded> события. Используйте этот обработчик событий для создания новой записи в источнике данных. Чтобы предотвратить ненамеренное изменение, необходимо отслеживать <xref:System.Windows.Forms.Control.KeyDown> событий для каждого элемента управления и вызвать <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A> при нажатии клавиши ESC.  
  
 Если изменения источника данных, можно обновить <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления путем вызова <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> и <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> методы. Оба метода должны вызываться в порядке.  
  
 Наконец, необходимо реализовать обработчики событий для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved> событие, возникающее при удалении элемента и при необходимости для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletingItems> и <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletedItems> событий, которые происходят каждый раз, когда пользователь удаляет элемент, нажав клавишу DELETE.  
  
## <a name="implementing-virtual-mode"></a>Реализация виртуального режима  
 Ниже приведены шаги, необходимые для реализации виртуального режима.  
  
#### <a name="to-implement-virtual-mode"></a>Чтобы реализовать виртуальный режим  
  
1.  Перетащите <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления из **Visual Basic PowerPacks** вкладке **элементов** форму или контейнерный элемент управления. Задайте для свойства <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> значение `True`.  
  
2.  Перетащите элементы управления из **элементов** область шаблона элемента (верхняя область) из <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления. Потребуется один элемент управления для каждого поля в источнике данных, который требуется отобразить.  
  
3.  Реализуйте обработчик <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> событий для предоставления значений для каждого элемента управления. Это событие возникает при создании нового <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> в области просмотра. Код будет выглядеть примерно так, предназначенная для источника данных с именем `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_1.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_1.cs)]  
  
4.  Реализуйте обработчик <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> событий для хранения данных. Это событие возникает, когда пользователь вносит изменения в дочерний элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>. Код будет выглядеть примерно так, предназначенная для источника данных с именем `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_2.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_2.cs)]  
  
5.  Реализуйте обработчик для каждого дочернего элемента управления <xref:System.Windows.Forms.Control.KeyDown> событий и монитор клавиши ESC. Вызовите <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A> метод, чтобы запретить <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> возникновения события. Код будет выглядеть примерно так.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_3.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_3.cs)]  
  
6.  Реализуйте обработчик <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded> событий. Это событие возникает, когда пользователь добавляет новый элемент в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления. Код будет выглядеть примерно так, предназначенная для источника данных с именем `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_4.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_4.cs)]  
  
7.  Реализуйте обработчик <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved> событий. Это событие возникает, когда пользователь удаляет существующий элемент. Код будет выглядеть примерно так, предназначенная для источника данных с именем `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_5.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_5.cs)]  
  
8.  Для проверки на уровне элемента управления, при необходимости реализовать обработчики для <xref:System.Windows.Forms.Control.Validating> события дочерних элементов управления. Код будет выглядеть примерно так.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#6](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_6.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#6](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_6.cs)]  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>  
 [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
