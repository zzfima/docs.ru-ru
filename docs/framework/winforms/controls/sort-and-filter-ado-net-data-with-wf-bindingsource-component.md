---
title: Сортировка и фильтрация данных ADO.NET с помощью компонента BindingSource
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
ms.openlocfilehash: cf1da3bb94b26449eb72b0e4930b262236487acc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742973"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a>Практическое руководство. Сортировка и фильтрация данных ADO.NET с помощью компонента BindingSource в Windows Forms
Можно предоставить возможность сортировки и фильтрации <xref:System.Windows.Forms.BindingSource> управления с помощью свойств <xref:System.Windows.Forms.BindingSource.Sort%2A> и <xref:System.Windows.Forms.BindingSource.Filter%2A>. Можно применить простую сортировку, если базовый источник данных является <xref:System.ComponentModel.IBindingList>ом, и можно применить фильтрацию и расширенную сортировку, если источником данных является <xref:System.ComponentModel.IBindingListView>. Для свойства <xref:System.Windows.Forms.BindingSource.Sort%2A> требуется стандартный синтаксис ADO.NET: строка, представляющая имя столбца данных в источнике данных, за которым следует `ASC` или `DESC`, чтобы указать, должен ли список быть отсортирован в порядке возрастания или убывания. Можно задать расширенную сортировку или сортировку по нескольким столбцам, разделив каждый столбец разделителями-запятыми. Свойство <xref:System.Windows.Forms.BindingSource.Filter%2A> принимает строковое выражение.  
  
> [!NOTE]
> Хранение конфиденциальных сведений (например, пароля) в строке подключения может повлиять на безопасность приложения. Использование проверки подлинности Windows (также называемой встроенными средствами безопасности) — более безопасный способ управления доступом к базе данных. Дополнительные сведения см. в разделе [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md).  
  
### <a name="to-filter-data-with-the-bindingsource"></a>Фильтрация данных с помощью BindingSource  
  
- Задайте для свойства <xref:System.Windows.Forms.BindingSource.Filter%2A> нужное выражение.  
  
     В следующем примере кода выражение представляет собой имя столбца, за которым следует значение, которое требуется для столбца.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a>Сортировка данных с помощью BindingSource  
  
1. Задайте для свойства <xref:System.Windows.Forms.BindingSource.Sort%2A> имя нужного столбца, а затем `ASC` или `DESC`, чтобы указать порядок по возрастанию или по убыванию.  
  
2. Несколько столбцов разделяются запятыми.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a>Пример  
 Следующий пример кода загружает данные из таблицы Customers образца базы данных Northwind в элемент управления <xref:System.Windows.Forms.DataGridView>, а также фильтрует и сортирует отображаемые данные.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы выполнить этот пример, вставьте код в форму, содержащую <xref:System.Windows.Forms.BindingSource> с именем `BindingSource1` и <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`. Обработайте событие <xref:System.Windows.Forms.Form.Load> для формы и вызовите `InitializeSortedFilteredBindingSource` в методе обработчика событий Load.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- [Практическое руководство. Установка образцов баз данных](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))
- [Компонент BindingSource](bindingsource-component.md)
