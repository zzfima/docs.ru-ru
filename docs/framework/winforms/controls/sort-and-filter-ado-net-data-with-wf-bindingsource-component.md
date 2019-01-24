---
title: Как выполнить Сортировка и фильтрация данных ADO.NET с помощью Windows Forms посредством компонента BindingSource
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting data
- data sorting [Windows Forms], ADO.NET
- data [Windows Forms], filtering
- BindingSource component [Windows Forms], sorting and filtering data
- filtering [Windows Forms], ADO.NET
- data [Windows Forms], sorting
- ADO.NET [Windows Forms]
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
ms.openlocfilehash: edb639f25970c6946eb33c68dd5a99cad566d4a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584783"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a>Как выполнить Сортировка и фильтрация данных ADO.NET с помощью Windows Forms посредством компонента BindingSource
Можно предоставить возможность фильтрации и сортировки <xref:System.Windows.Forms.BindingSource> управлять через <xref:System.Windows.Forms.BindingSource.Sort%2A> и <xref:System.Windows.Forms.BindingSource.Filter%2A> свойства. Можно применить простую сортировку, когда в источнике данных <xref:System.ComponentModel.IBindingList>, и можно применить фильтрацию и если источником данных является <xref:System.ComponentModel.IBindingListView>. <xref:System.Windows.Forms.BindingSource.Sort%2A> Свойства требуется стандартный [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] синтаксис: строка, представляющая имя столбца данных в источнике данных, за которым следует `ASC` или `DESC` для указания ли списка должны быть отсортированы в порядке возрастания или убывания. Можно задать дополнительные возможности сортировки или несколько столбцов сортировки, каждый столбец отделяется разделителем запятой. <xref:System.Windows.Forms.BindingSource.Filter%2A> Свойство принимает строковое выражение.  
  
> [!NOTE]
>  Хранение конфиденциальных сведений (например, пароля) в строке подключения может повлиять на безопасность приложения. Использование проверки подлинности Windows (также называемой встроенными средствами безопасности) — более безопасный способ управления доступом к базе данных. Дополнительные сведения см. в разделе [Защита сведений о подключении](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
### <a name="to-filter-data-with-the-bindingsource"></a>Для фильтрации данных с использованием компонента BindingSource  
  
-   Задать <xref:System.Windows.Forms.BindingSource.Filter%2A> свойства необходимое выражение.  
  
     В следующем примере выражение является именем столбца, за которым следует значение для столбца.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a>Для сортировки данных с использованием компонента BindingSource  
  
1.  Задайте <xref:System.Windows.Forms.BindingSource.Sort%2A> свойства к имени столбца, который будет следуют `ASC` или `DESC` для указания по возрастанию или убыванию.  
  
2.  Несколько столбцов разделяются запятыми.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a>Пример  
 В следующем примере кода загружает данные из образца базы данных "Борей" в таблице Customers <xref:System.Windows.Forms.DataGridView> и фильтрует и сортирует отображаемых данных.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы выполнить этот пример, вставьте код в форму, содержащую <xref:System.Windows.Forms.BindingSource> с именем `BindingSource1` и <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`. Обрабатывать <xref:System.Windows.Forms.Form.Load> событие для форму и вызовите `InitializeSortedFilteredBindingSource` в методе обработчика событий загрузки.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- [Практическое руководство. Установка образцов баз данных](https://msdn.microsoft.com/library/ed1291f6-604c-4972-ae22-0345c6dea12e)
- [Компонент BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)
