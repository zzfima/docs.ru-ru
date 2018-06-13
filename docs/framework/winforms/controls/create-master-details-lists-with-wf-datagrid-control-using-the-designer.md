---
title: Практическое руководство. Создание списков основных сведений с использованием элемента управления DataGrid в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
ms.openlocfilehash: 20a6f059efab5469879d3c3a45f4005020414316
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529981"
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a>Практическое руководство. Создание списков основных сведений с использованием элемента управления DataGrid в формах Windows Forms с помощью конструктора
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Если ваш <xref:System.Data.DataSet> содержит набор связанных таблиц, можно использовать два <xref:System.Windows.Forms.DataGrid> элементы управления для отображения данных в формате основной подробности. Один <xref:System.Windows.Forms.DataGrid> назначен в качестве основной сетки, а второй для сетки сведений. При выборе элемента в главном списке все связанные дочерние записи отображаются в списке сведений. Например если ваш <xref:System.Data.DataSet> содержит таблицу Customers и связанную таблицу Orders, можно указать таблицу Customers основной сетки, а таблицу Orders, чтобы быть в таблице сведений. При выборе клиента в основной сетке все заказы, относящиеся к этому клиенту в таблице Orders будет отображаться в таблице сведений.  
  
 В следующей процедуре требуется **приложение Windows** проекта. Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-a-master-details-list-in-the-designer"></a>Чтобы создать список основных сведений в конструкторе  
  
1.  Добавление двух <xref:System.Windows.Forms.DataGrid> элементов управления в форму. Дополнительные сведения см. в разделе [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md). В [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], <xref:System.Windows.Forms.DataGrid> управления не находится в **элементов** по умолчанию. Дополнительные сведения см. в разделе [как: Добавление элементов в область элементов](http://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0).  
  
    > [!NOTE]
    >  Следующие шаги не применимы к [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], которая использует **источники данных** окна для привязки данных во время разработки. Дополнительные сведения см. в разделе [привязки элементов управления к данным в Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) и [как: отображение связанных данных в приложении Windows Forms](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd).  
  
2.  Перетащите несколько таблиц из **обозревателя серверов** в форму.  
  
3.  Из **данные** последовательно выберите пункты **создать набор данных**.  
  
4.  Установите связи между таблицами в конструкторе XML. Дополнительные сведения см. в разделе «как: создайте один ко многим связей в XML-схемы и наборы данных» в библиотеке MSDN.  
  
5.  Сохраните отношения, выбрав **сохранить все** из **файл** меню.  
  
6.  Настройка <xref:System.Windows.Forms.DataGrid> элемент управления, который требуется назначить основной сеткой следующим образом:  
  
    1.  Выберите <xref:System.Data.DataSet> из раскрывающегося списка в <xref:System.Windows.Forms.DataGrid.DataSource%2A> свойство.  
  
    2.  Выберите основную таблицу (например, «заказчики») из раскрывающегося списка в <xref:System.Windows.Forms.DataGrid.DataMember%2A> свойство.  
  
7.  Настройка <xref:System.Windows.Forms.DataGrid> элемент управления, который требуется назначить сеткой сведений, следующим образом:  
  
    1.  Выберите <xref:System.Data.DataSet> из раскрывающегося списка в <xref:System.Windows.Forms.DataGrid.DataSource%2A> свойство.  
  
    2.  Выберите связь (например, «Customers.CustOrd») между таблицами master и сведений из раскрывающегося списка в <xref:System.Windows.Forms.DataGrid.DataMember%2A> свойство. Чтобы просмотреть связь, разверните узел, щелкнув знак плюс (**+**) рядом с основной таблицей в раскрывающемся списке.  
  
## <a name="see-also"></a>См. также  
 [Элемент управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Общие сведения об элементе управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
 [Привязка элементов управления к данным в Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
