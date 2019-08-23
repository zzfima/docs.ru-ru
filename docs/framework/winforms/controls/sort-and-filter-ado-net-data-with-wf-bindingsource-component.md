---
title: Практическое руководство. Сортировка и фильтрация данных ADO.NET с помощью компонента BindingSource в Windows Forms
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
ms.openlocfilehash: ae331ca9e3fd2aed654659e11434454874eff8fa
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960434"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a>Практическое руководство. Сортировка и фильтрация данных ADO.NET с помощью компонента BindingSource в Windows Forms
Можно предоставить возможность <xref:System.Windows.Forms.BindingSource> сортировки и фильтрации элементов управления с <xref:System.Windows.Forms.BindingSource.Sort%2A> помощью свойств и <xref:System.Windows.Forms.BindingSource.Filter%2A> . Можно применить простую сортировку <xref:System.ComponentModel.IBindingList>, если базовый источник данных является, и можно применить фильтрацию и расширенную сортировку, если источником данных <xref:System.ComponentModel.IBindingListView>является. Для свойства требуется стандартный синтаксис ADO.NET: строка, представляющая имя столбца данных в источнике данных, `ASC` за которым следует или `DESC` , чтобы указать, должен ли список быть отсортирован в порядке возрастания или убывания. <xref:System.Windows.Forms.BindingSource.Sort%2A> Можно задать расширенную сортировку или сортировку по нескольким столбцам, разделив каждый столбец разделителями-запятыми. <xref:System.Windows.Forms.BindingSource.Filter%2A> Свойство принимает строковое выражение.  
  
> [!NOTE]
> Хранение конфиденциальных сведений (например, пароля) в строке подключения может повлиять на безопасность приложения. Использование проверки подлинности Windows (также называемой встроенными средствами безопасности) — более безопасный способ управления доступом к базе данных. Дополнительные сведения см. в разделе [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md).  
  
### <a name="to-filter-data-with-the-bindingsource"></a>Фильтрация данных с помощью BindingSource  
  
- Задайте для <xref:System.Windows.Forms.BindingSource.Filter%2A> свойства нужное выражение.  
  
     В следующем примере кода выражение представляет собой имя столбца, за которым следует значение, которое требуется для столбца.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a>Сортировка данных с помощью BindingSource  
  
1. Присвойте `ASC` `DESC` свойству имя нужного столбца, а затем укажите порядок сортировки по возрастанию или убыванию. <xref:System.Windows.Forms.BindingSource.Sort%2A>  
  
2. Несколько столбцов разделяются запятыми.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a>Пример  
 Следующий пример кода загружает данные из таблицы Customers образца базы данных Northwind в <xref:System.Windows.Forms.DataGridView> элемент управления, а затем фильтрует и сортирует отображаемые данные.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы выполнить этот пример, вставьте код в форму, <xref:System.Windows.Forms.BindingSource> содержащую именованный `BindingSource1` и <xref:System.Windows.Forms.DataGridView> именованный `dataGridView1`. Обработайте `InitializeSortedFilteredBindingSource`событиедля формы и вызовите метод обработчика событий Load. <xref:System.Windows.Forms.Form.Load>  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- [Практическое руководство. Установка образцов баз данных](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))
- [Компонент BindingSource](bindingsource-component.md)
