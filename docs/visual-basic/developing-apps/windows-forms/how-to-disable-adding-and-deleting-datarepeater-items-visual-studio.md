---
title: "Пошаговое руководство. Запрещение возможности добавления и удаления элементов DataRepeater (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater, отключение добавления"
  - "DataRepeater, отключение удаления"
ms.assetid: 298d8f60-ddfe-4361-ab66-cf76d0df5220
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Пошаговое руководство. Запрещение возможности добавления и удаления элементов DataRepeater (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

По умолчанию, пользователи могут добавлять и удалять элементы в\/из элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  Пользователи могут добавить новый элемент нажав CTRL\+N, когда на <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> находится в фокусе или нажав кнопку **AddNewItem** на элементе управления <xref:System.Windows.Forms.BindingNavigator>.  Пользователи могут удалить новый элемент нажав DELETE, когда на <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> находится в фокусе или нажав кнопку **DeleteItem** на элементе управления <xref:System.Windows.Forms.BindingNavigator>.  
  
 Можно отключить добавление и\/или удаление на этапе проектирования или во время выполнения.  
  
### Чтобы отключить добавление и удаление на этапе разработки  
  
1.  В конструкторе Windows Forms выберите элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
    > [!NOTE]
    >  Следует выбрать нижнюю часть элемента управления.  Если выбрать подраздел шаблона элемента, то можно просмотреть различные настройки свойств.  
  
2.  В окне "Свойства" присвойте свойству <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToAddItems%2A> значение **False**.  
  
3.  Присвойте свойству <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToDeleteItems%2A> значение  **False**.  
  
4.  В конструкторе Windows Forms, выберите элемент управления <xref:System.Windows.Forms.BindingNavigator> и затем нажмите кнопку **AddNewItem** \(кнопка со знаком плюса\).  
  
5.  В окне "Свойства" присвойте свойству <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> значение **False**.  
  
6.  В конструкторе Windows Forms, выберите элемент управления <xref:System.Windows.Forms.BindingNavigator> и затем нажмите кнопку **DeleteItem** \(кнопка с красным значком X\).  
  
7.  В окне "Свойства" присвойте свойству <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> значение **False**.  
  
8.  В области компонентов выберите источник данных <xref:System.Windows.Forms.BindingSource> к которому привязан элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
9. В окне "Свойства" присвойте свойству <xref:System.Windows.Forms.BindingSource.AllowNew%2A> значение **False**.  
  
10. В конструкторе Windows Forms, дважды нажмите кнопку **DeleteItem**, чтобы открыть редактор кода.  
  
11. Выберите событие `BindingNavigatorDeleteItem_EnabledChanged` из раскрывающегося списка событий.  
  
12. В обработчик событий `BindingNavigatorDeleteItem_EnabledChanged` добавьте следующий код:  
  
     [!code-cs[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  Это шаг является необходимым, поскольку <xref:System.Windows.Forms.BindingSource> включает кнопку **DeleteItem** каждый раз при изменении текущей записи.  
  
### Чтобы отключить добавление и удаление во время выполнения  
  
1.  В конструкторе Windows Forms, дважды щелкните форму, чтобы открыть редактор кода.  
  
2.  Добавьте следующий код в событие `Form_Load`:  
  
     [!code-cs[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.vb)]  
  
3.  В обработчик событий `BindingNavigatorDeleteItem_EnabledChanged` добавьте следующий код:  
  
     [!code-cs[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  Это шаг является необходимым, поскольку <xref:System.Windows.Forms.BindingSource> включает кнопку **DeleteItem** каждый раз при изменении текущей записи.  
  
## См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)