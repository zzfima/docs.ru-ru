---
title: Пошаговое руководство. Запрещение возможности добавления и удаления элементов DataRepeater (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, disabling delete
- DataRepeater, disabling add
ms.assetid: 298d8f60-ddfe-4361-ab66-cf76d0df5220
ms.openlocfilehash: e3d0d2a8d422054e269ee92df1fdfcb5acb96eac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590814"
---
# <a name="how-to-disable-adding-and-deleting-datarepeater-items-visual-studio"></a>Пошаговое руководство. Запрещение возможности добавления и удаления элементов DataRepeater (Visual Studio)
По умолчанию пользователи могут добавлять и удалять элементы в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления. Пользователи могут добавлять новый элемент, нажав клавиши CTRL + N при <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> находится в фокусе или щелкнув **AddNewItem** кнопку <xref:System.Windows.Forms.BindingNavigator> элемента управления. Удалить элемент, нажав клавишу DELETE, когда <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> находится в фокусе или щелкнув **DeleteItem** кнопку на <xref:System.Windows.Forms.BindingNavigator> элемента управления.  
  
 Можно отключить, добавив или удалив во время разработки или во время выполнения.  
  
### <a name="to-disable-adding-and-deleting-at-design-time"></a>Чтобы отключить добавление и удаление во время разработки  
  
1.  В конструкторе Windows Forms выберите <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.  
  
    > [!NOTE]
    >  Необходимо выбрать нижней части элемента управления. При выборе области шаблона элемента, отображается другой набор свойств.  
  
2.  В окне свойств задайте <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToAddItems%2A> свойства **False**.  
  
3.  Задать <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToDeleteItems%2A> свойства **False**.  
  
4.  В конструкторе Windows Forms выберите <xref:System.Windows.Forms.BindingNavigator> управления и нажмите кнопку **AddNewItem** (кнопка со знаком плюс на нем).  
  
5.  В окне свойств задайте <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> свойства **False**.  
  
6.  В конструкторе Windows Forms выберите <xref:System.Windows.Forms.BindingNavigator> управления и нажмите кнопку **DeleteItem** (кнопка с красным крестом на нем).  
  
7.  В окне свойств задайте <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> свойства **False**.  
  
8.  В области компонентов, выберите <xref:System.Windows.Forms.BindingSource> к которому <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> привязан.  
  
9. В окне свойств задайте <xref:System.Windows.Forms.BindingSource.AllowNew%2A> свойства **False**.  
  
10. В конструкторе Windows Forms дважды щелкните **DeleteItem** кнопку, чтобы открыть редактор кода.  
  
11. Выберите в раскрывающемся списке события `BindingNavigatorDeleteItem_EnabledChanged` событий.  
  
12. Добавьте следующий код в обработчик событий `BindingNavigatorDeleteItem_EnabledChanged` .  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  Этот шаг необходим, так как <xref:System.Windows.Forms.BindingSource> будет активировать кнопку **DeleteItem** при каждом изменении текущей записи.  
  
### <a name="to-disable-adding-and-deleting-at-run-time"></a>Чтобы отключить добавление и удаление во время выполнения  
  
1.  В конструкторе Windows Forms дважды щелкните форму, чтобы открыть редактор кода.  
  
2.  Добавьте следующий код в событие `Form_Load` :  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.vb)]  
  
3.  Добавьте следующий код в обработчик событий `BindingNavigatorDeleteItem_EnabledChanged` .  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  Этот шаг необходим, так как <xref:System.Windows.Forms.BindingSource> будет активировать кнопку **DeleteItem** при каждом изменении текущей записи.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
