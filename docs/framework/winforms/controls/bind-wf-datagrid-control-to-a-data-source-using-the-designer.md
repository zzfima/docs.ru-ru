---
title: "Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных с помощью конструктора"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- Windows Forms controls, data binding
- bound controls [Windows Forms]
ms.assetid: 4e96e3d0-b1cc-4de1-8774-bc9970ec4554
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3913ffe046bb55e31d8be223061af61371a47418
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a>Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных с помощью конструктора
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Windows Forms <xref:System.Windows.Forms.DataGrid> управления разработан специально для отображения сведений из источника данных. Привязки элемента управления во время разработки, задав <xref:System.Windows.Forms.DataGrid.DataSource%2A> и <xref:System.Windows.Forms.DataGrid.DataMember%2A> свойства, или во время выполнения путем вызова <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> метод. Несмотря на то, что может отображать данные из различных источников данных, типичных причин являются наборы данных и представления данных.  
  
 Если источник данных доступен во время разработки — например, если форма содержит экземпляр набора данных или представление данных, сетку можно привязать к источнику данных во время разработки. Затем можно просмотреть, как будет выглядеть данные в сетке.  
  
 Можно также привязать сетки программным образом, во время выполнения. Это полезно в том случае, если вы хотите задать источник данных, на основе сведений, получаемых во время выполнения. Например приложение может быть реализована возможность указания имени таблицы для просмотра. Также в некоторых ситуациях, где источник данных не существует во время разработки. Это включает источники данных, таких как массивы, коллекции, нетипизированные наборы данных и модули чтения данных.  
  
 В следующей процедуре требуется **приложение Windows** проекта с формой, содержащей <xref:System.Windows.Forms.DataGrid> элемента управления. Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md). В [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], <xref:System.Windows.Forms.DataGrid> управления не находится в **элементов** по умолчанию. Сведения о его добавлении см. в разделе [как: Добавление элементов в область элементов](http://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0). Кроме того, в [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], можно использовать **источники данных** окна для привязки данных во время разработки. Дополнительные сведения см. [привязки элементов управления к данным в Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a>Чтобы выполнить привязку данных элемента управления DataGrid к одной таблице в конструкторе  
  
1.  Задайте в качестве <xref:System.Windows.Forms.DataGrid.DataSource%2A> объект, содержащий элементы данных, необходимо выполнить привязку к свойству.  
  
2.  Если источник данных представляет собой набор данных, задайте <xref:System.Windows.Forms.DataGrid.DataMember%2A> на имя таблицы для привязки.  
  
3.  Если источником данных является набор данных или представление данных, основанное на таблице набора данных, добавьте код в форму для заполнения набора данных.  
  
     Точный код, который вы используете зависит от того, где поступают в набор данных. Если набор данных заполняется непосредственно из базы данных, обычно вызывается `Fill` метод адаптера данных, как показано в следующем примере кода, который заполняет набор данных с именем `DsCategories1`:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
4.  (Необязательно) Добавьте требуемые стили таблиц и столбцов в сетке.  
  
     Если стили таблиц отсутствуют, появится таблица с минимальным форматированием и при этом все столбцы видимым.  
  
### <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a>Чтобы выполнить привязку данных элемента управления DataGrid к нескольким таблицам в наборе данных в конструкторе  
  
1.  Задайте в качестве <xref:System.Windows.Forms.DataGrid.DataSource%2A> объект, содержащий элементы данных, необходимо выполнить привязку к свойству.  
  
2.  Если набор данных содержит связанные таблицы (если имеется объект связи), установите <xref:System.Windows.Forms.DataGrid.DataMember%2A> на имя родительской таблицы.  
  
3.  Напишите код для заполнения набора данных.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об элементе управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [Элемент управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Привязка данных Windows Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [Доступ к данным в Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio)
