---
title: "Виртуальный режим в элементе управления DataRepeater (Visual Studio) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- virtual data binding
- DataRepeater
- DataRepeater, virtual mode
ms.assetid: 5fb805dc-2d8b-4139-b1e3-86e4c2667221
caps.latest.revision: 13
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 85f7e250c57a507e891eb30756c0550098cce9e0
ms.lasthandoff: 03/13/2017

---
# <a name="virtual-mode-in-the-datarepeater-control-visual-studio"></a>Виртуальные режим в элементе управления DataRepeater (Visual Studio)
Если требуется отобразить большой объем табличных данных в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления, может повысить производительность, задав <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>Свойства `True` и явно Управление взаимодействием элемента управления с источником данных.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Управления предусмотрено несколько событий, которые можно обрабатывать при взаимодействии с источником данных и отображения данных, при необходимости во время выполнения.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
## <a name="how-virtual-mode-works"></a>Как работает виртуальный режим  
 Наиболее распространенный сценарий для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>является привязка дочерние элементы управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>данных источника во время разработки и разрешить <xref:System.Windows.Forms.BindingSource>для передачи данных туда и обратно при необходимости.</xref:System.Windows.Forms.BindingSource> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> При использовании виртуального режима, эти элементы управления не привязаны к источнику данных и данные передаются назад и вперед к базовому источнику данных во время выполнения.  
  
 При <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>свойству `True`, создайте пользовательский интерфейс, добавив элементы управления из **элементов** вместо добавления связанных элементов управления из **источников данных** окно.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>  
  
 События на основе элемента управления, и необходимо добавить код для управления отображением данных. При создании нового <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>в области просмотра, <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>событие вызывается один раз для каждого элемента управления и необходимо предоставить значения для каждого элемента управления в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>обработчик события.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>  
  
 При изменении данных в одном из элементов управления пользователем, <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>событие, и необходимо проверить данные и сохраните его в источник данных.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>  
  
 При добавлении нового элемента, <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>событие.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded> Используйте этот обработчик событий для создания новой записи в источнике данных. Для предотвращения непреднамеренного изменения, необходимо отслеживать <xref:System.Windows.Forms.Control.KeyDown>событий для каждого элемента управления и вызвать <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A>при нажатии клавиши ESC.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A> </xref:System.Windows.Forms.Control.KeyDown>  
  
 Если изменения источника данных, можно обновить <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления путем вызова <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A>и <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A>методы.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Оба метода должны вызываться в порядке.  
  
 Наконец, необходимо реализовать обработчики событий для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved>событие, возникающее при удалении элемента и при необходимости для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletingItems>и <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletedItems>событий, которые происходят, когда пользователь удаляет элемент с помощью клавиши DELETE.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletedItems> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletingItems> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved>  
  
## <a name="implementing-virtual-mode"></a>Реализация виртуального режима  
 Ниже приведены шаги, которые необходимо реализовать виртуальный режим.  
  
#### <a name="to-implement-virtual-mode"></a>Чтобы реализовать виртуальный режим  
  
1.  Перетащите <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления из **Visual Basic PowerPacks** вкладке **элементов** форму или контейнерный элемент управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Задать <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>Свойства `True`.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>  
  
2.  Перетащите элементы управления из **элементов** область шаблона элемента (верхняя область) элемента <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Потребуется один элемент управления для каждого поля в источнике данных, который вы хотите отобразить.  
  
3.  Реализуйте обработчик <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>событий для предоставления значений для каждого элемента управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> Это событие возникает при добавлении нового <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>в области просмотра.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> Код будет выглядеть примерно так, для источника данных с именем `Employees`.  
  
     [!code-vb[#1 VbPowerPacksDataRepeaterVirtualMode](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_1.vb) ] 
     [!code-cs [VbPowerPacksDataRepeaterVirtualMode&#1;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_1.cs)]  
  
4.  Реализуйте обработчик <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>событий для хранения данных.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> Это событие возникает, когда пользователь вносит изменения в дочернем элементе управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> Код будет выглядеть примерно так, для источника данных с именем `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode&2;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_2.vb) ] 
     [!code-cs [VbPowerPacksDataRepeaterVirtualMode&#2;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_2.cs)]  
  
5.  Реализуйте обработчик для каждого дочернего элемента управления <xref:System.Windows.Forms.Control.KeyDown>событий и монитор клавишей ESC.</xref:System.Windows.Forms.Control.KeyDown> Вызов <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A>метод для предотвращения <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>возникновения события.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A> Код будет выглядеть примерно так.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode&3;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_3.vb) ] 
     [!code-cs [VbPowerPacksDataRepeaterVirtualMode&#3;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_3.cs)]  
  
6.  Реализуйте обработчик <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>событий.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded> Это событие возникает, когда пользователь добавляет новый элемент в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Код будет выглядеть примерно так, для источника данных с именем `Employees`.  
  
     [!code-vb[#4 VbPowerPacksDataRepeaterVirtualMode](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_4.vb) ] 
     [!code-cs [VbPowerPacksDataRepeaterVirtualMode&#4;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_4.cs)]  
  
7.  Реализуйте обработчик <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved>событий.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved> Это событие происходит, когда пользователь удаляет существующий элемент. Код будет выглядеть примерно так, для источника данных с именем `Employees`.  
  
     [!code-vb[#5 VbPowerPacksDataRepeaterVirtualMode](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_5.vb) ] 
     [!code-cs [VbPowerPacksDataRepeaterVirtualMode&#5;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_5.cs)]  
  
8.  Для проверки на уровне элемента управления, при необходимости реализовать обработчики для <xref:System.Windows.Forms.Control.Validating>события дочерних элементов управления.</xref:System.Windows.Forms.Control.Validating> Код будет выглядеть примерно так.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode&6;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_6.vb) ] 
     [!code-cs [VbPowerPacksDataRepeaterVirtualMode&6;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_6.cs)]  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed></xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded></xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded></xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>   
 [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
