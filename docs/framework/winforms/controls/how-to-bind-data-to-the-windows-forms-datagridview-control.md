---
title: Связать данные с управлением DataGridView
ms.date: 02/08/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
ms.openlocfilehash: 643dcd37cd1bb3f8b5938fedff66c67cd68278ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182277"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a>Как: Привязать данные к управлению Data Forms DataGridView

Элемент <xref:System.Windows.Forms.DataGridView> управления поддерживает стандартную модель связывания данных Windows Forms, поэтому он может связываться с различными источниками данных. Обычно вы привязываетесь к <xref:System.Windows.Forms.BindingSource> тому, кто управляет взаимодействием с источником данных. Это <xref:System.Windows.Forms.BindingSource> может быть любой источник данных Windows Forms, который дает вам большую гибкость при выборе или изменении местоположения данных. Для получения дополнительной информации об источниках данных, <xref:System.Windows.Forms.DataGridView> которые поддерживает элемент управления, см. [DataGridView control overview](datagridview-control-overview-windows-forms.md)  

Visual Studio имеет широкую поддержку связывания данных с управлением DataGridView. Для получения дополнительной информации [см. Как: Привязать данные к управлению Data Forms DataGridView с помощью designer.](bind-data-to-the-datagrid-using-the-designer.md)  

Чтобы подключить элемент управления DataGridView к данным:

1. Реализация метода обработки деталей получения данных. Следующий пример кода `GetData` реализует <xref:System.Data.SqlClient.SqlDataAdapter>метод, который инициализирует, <xref:System.Data.DataTable>и использует его для заполнения . Затем он связывает <xref:System.Data.DataTable> к <xref:System.Windows.Forms.BindingSource>.

2. В <xref:System.Windows.Forms.Form.Load> обработчике событий в <xref:System.Windows.Forms.DataGridView> форме <xref:System.Windows.Forms.BindingSource>свяжите элемент `GetData` управления с методом для извлечения данных.  

## <a name="example"></a>Пример

Этот полный пример кода извлекает данные из базы данных для заполнения элемента управления DataGridView в форме Windows. Форма также имеет кнопки для перезагрузки данных и представления изменений в базу данных.  

Для этого примера требуются:

- Доступ к выборочной базе данных Northwind S'L Server. Для получения дополнительной информации об установке базы данных образца Northwind см [ADO.NET.](../../data/adonet/sql/linq/downloading-sample-databases.md)

- Ссылки на сборки системы, System.Windows.Forms, System.Data и System.Xml.  

Чтобы создать и запустить этот пример, вставьте код в файл кода *Form1* в новом проекте Форм Windows. Для получения информации о здании из командной строки C или Visual Basic [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) [см.](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
  
Заполните `connectionString` переменную в примере значениями для подключения к базе данных Northwind s'L Server. Проверка подлинности Windows, также называемая интегрированной безопасностью, является более безопасным способом подключения к базе данных, чем хранение пароля в строке соединения. Для получения дополнительной информации о безопасности соединения [см.](../../data/adonet/protecting-connection-information.md)  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [Отображение данных в управлении DataFormsGridView](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Защита информации о подключении](../../data/adonet/protecting-connection-information.md)
