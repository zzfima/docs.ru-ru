---
title: "Практическое руководство. Привязка элемента управления Windows Forms к типу с помощью конструктора"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ee932e7cb4a3333ac56242e281ec64d3016746f9
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type-using-the-designer"></a>Практическое руководство. Привязка элемента управления Windows Forms к типу с помощью конструктора
При создании элементов управления, взаимодействующих с данными, иногда бывает нужно привязать элемент управления к типу, а не к объекту. Обычно подобная ситуация возникает на этапе разработки, когда данные недоступны, однако нужно, чтобы элементы управления с привязкой к данным отображали данные из открытого интерфейса типа. Ниже описано, как создать новый <xref:System.Windows.Forms.BindingSource> , связанного с типом, а затем связывание одного из свойств типа со <xref:System.Windows.Forms.TextBox.Text%2A> свойство <xref:System.Windows.Forms.TextBox>.  
  
### <a name="to-bind-the-bindingsource-to-a-type"></a>Привязка BindingSource к типу  
  
1.  Создайте проект Windows Forms.  
  
     Дополнительные сведения см. в разделе [Практическое руководство. Создание проекта приложения WPF](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  В **разработки** Просмотр, перетащите <xref:System.Windows.Forms.BindingSource> компонента в форму.  
  
3.  В **свойства** окно, щелкните стрелку, чтобы <xref:System.Windows.Forms.BindingSource.DataSource%2A> свойство.  
  
4.  В **редакторе типов пользовательского интерфейса DataSource** нажмите кнопку **Добавить источник данных проекта**.  
  
5.  На странице **Выбор типа источника данных** выберите тип **Объект** и нажмите кнопку **Далее**.  
  
6.  Выберите тип для привязки.  
  
    -   Если тип для привязки находится в текущем проекте либо сборка, содержащая этот тип, уже добавлена как ссылка, разверните узлы, а затем найдите и выберите желаемый тип.  
  
         - или -  
  
    -   Если тип для привязки находится в другой сборке, которой еще нет в списке ссылок, нажмите **Добавить ссылку** и выберите вкладку **Проекты**. Выберите проект, содержащий нужный вам бизнес-объект, и нажмите кнопку **ОК**. Этот проект будет отображаться в списке сборок, так что вы сможете развернуть узлы, а затем найти и выбрать желаемый тип.  
  
        > [!NOTE]
        >  Если тип, который нужно привязать, находится в инфраструктуре или сборке Майкрософт, снимите флажок **Скрыть сборки, начинающиеся с Microsoft или System**.  
  
7.  Щелкните **Далее**и затем нажмите кнопку **Готово**.  
  
### <a name="to-bind-the-control-to-the-bindingsource"></a>Привязка элемента управления к BindingSource  
  
1.  Добавьте на форму элемент <xref:System.Windows.Forms.TextBox>.  
  
2.  В окне **Свойства** разверните узел **(DataBindings)**.  
  
3.  Щелкните стрелку рядом с <xref:System.Windows.Forms.TextBox.Text%2A> свойство.  
  
4.  В **редактора источника**, разверните узел для <xref:System.Windows.Forms.BindingSource> добавлен ранее и выберите свойство связанного типа, необходимо выполнить привязку к <xref:System.Windows.Forms.TextBox.Text%2A> свойство <xref:System.Windows.Forms.TextBox>.  
  
## <a name="see-also"></a>См. также  
 [Компонент BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [Практическое руководство. Связывание элемента управления с типом в Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)  
 [Привязка элементов управления к данным в Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
