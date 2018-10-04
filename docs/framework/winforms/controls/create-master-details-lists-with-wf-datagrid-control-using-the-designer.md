---
title: Практическое руководство. Создание списков основных сведений с использованием элемента управления DataGrid в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
ms.openlocfilehash: aec02e38fbe80302108397543144b1cc9c3ea346
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48266792"
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a>Практическое руководство. Создание списков основных сведений с использованием элемента управления DataGrid в формах Windows Forms с помощью конструктора

> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Если ваш <xref:System.Data.DataSet> содержит ряд связанных таблиц, можно использовать два <xref:System.Windows.Forms.DataGrid> элементы управления для отображения данных в формате «основной-подробности». Один <xref:System.Windows.Forms.DataGrid> назначен в качестве основной сеткой, а второй для сетки сведений. При выборе записи в главном списке все связанные дочерние записи отображаются в списке сведений. Например если ваш <xref:System.Data.DataSet> содержит таблицу "Клиенты" и связанную таблицу Orders, нужно указать таблицы клиентов на основной сетки и таблицу Orders, чтобы быть в таблице сведений. При выборе клиента в основной сетке все заказы, связанные с клиентом в таблице Orders будет отображаться в таблице сведений.  
  
 Следующая процедура требуется **приложения Windows** проекта (**файл** > **New** > **проекта**  >  **Visual C#** или **Visual Basic** > **классический рабочий стол** > **Windows Forms Приложение**).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-a-master-details-list-in-the-designer"></a>Чтобы создать список основных сведений в конструкторе  
  
1.  Добавьте два <xref:System.Windows.Forms.DataGrid> элементов управления в форму. Дополнительные сведения см. в разделе [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md). В Visual Studio 2005 <xref:System.Windows.Forms.DataGrid> элемент управления отсутствует в **элементов** по умолчанию. Дополнительные сведения см. в разделе [как: Добавление элементов на панель инструментов](https://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0).  
  
    > [!NOTE]
    >  Следующие действия не применяются к Visual Studio 2005, который использует **источников данных** окно для привязки данных во время разработки. Дополнительные сведения см. в разделе [привязка элементов управления к данным в Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) и [как: отображение связанных данные в приложении Windows Forms](https://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd).  
  
2.  Перетащите несколько таблиц из **обозревателя серверов** в форму.  
  
3.  Из **данных** меню, выберите **создать набор данных**.  
  
4.  Установите связи между таблицами, с помощью конструктора XML. Дополнительные сведения см. в разделе «Практическое: создайте один ко многим связей в XML-схемы и наборы данных» на сайте MSDN.  
  
5.  Сохраните отношения, выбрав **сохранить все** из **файл** меню.  
  
6.  Настройка <xref:System.Windows.Forms.DataGrid> элемент управления, который вы хотите назначить основной сеткой, следующим образом:  
  
    1.  Выберите <xref:System.Data.DataSet> из раскрывающегося списка в <xref:System.Windows.Forms.DataGrid.DataSource%2A> свойство.  
  
    2.  Выберите основную таблицу (например, «Customers») из раскрывающегося списка в <xref:System.Windows.Forms.DataGrid.DataMember%2A> свойство.  
  
7.  Настройка <xref:System.Windows.Forms.DataGrid> элемент управления, который вы хотите назначить сеткой сведений, следующим образом:  
  
    1.  Выберите <xref:System.Data.DataSet> из раскрывающегося списка в <xref:System.Windows.Forms.DataGrid.DataSource%2A> свойство.  
  
    2.  Выберите связь (например, «Customers.CustOrd») между основными и подробными стрелку раскрывающегося списка в <xref:System.Windows.Forms.DataGrid.DataMember%2A> свойство. Чтобы просмотреть связь, разверните узел, щелкнув знак "плюс" (**+**) рядом с основной таблицей в раскрывающемся списке.  
  
## <a name="see-also"></a>См. также  
 [Элемент управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Общие сведения об элементе управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
 [Привязка элементов управления к данным в Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
