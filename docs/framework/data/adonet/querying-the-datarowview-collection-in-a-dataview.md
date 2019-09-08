---
title: Запрос к коллекции DataRowView в объекте DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b9070a12-1094-44d6-bb87-a23b50bcb0af
ms.openlocfilehash: 17fab6e4c178eee6b5135045fb953267db810898
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794464"
---
# <a name="querying-the-datarowview-collection-in-a-dataview"></a>Запрос к коллекции DataRowView в объекте DataView
Представление <xref:System.Data.DataView> обеспечивает доступ к перечисляемой коллекции объектов <xref:System.Data.DataRowView>. Объект <xref:System.Data.DataRowView> предоставляет пользовательское представление объекта <xref:System.Data.DataRow> и отображает конкретную версию этого объекта <xref:System.Data.DataRow> в элементе управления. В элементе управления, например <xref:System.Data.DataRow>, можно отобразить только одну версию объекта <xref:System.Windows.Forms.DataGridView>. Доступ к объекту <xref:System.Data.DataRow>, представляемому объектом <xref:System.Data.DataRowView>, можно получить через свойство <xref:System.Data.DataRowView.Row%2A> объекта <xref:System.Data.DataRowView>. При просмотре значений с помощью объекта <xref:System.Data.DataRowView> свойство <xref:System.Data.DataView.RowStateFilter%2A> определяет, какая версия строки базового объекта <xref:System.Data.DataRow> отображается. Сведения о доступе к различным версиям строк <xref:System.Data.DataRow>с помощью см. в разделе [состояния строк и версии строк](./dataset-datatable-dataview/row-states-and-row-versions.md). Поскольку коллекция <xref:System.Data.DataRowView> объектов, предоставляемых <xref:System.Data.DataView> объектом, является перечислимой, можно использовать LINQ to DataSet для запроса.  
  
 В следующем примере выполняется запрос к таблице `Product` для вывода продуктов красного цвета и на основе этого запроса создается таблица. Объект <xref:System.Data.DataView> создается из этой таблицы, а свойство <xref:System.Data.DataView.RowStateFilter%2A> задается для фильтрации удаленных и измененных строк. Затем объект <xref:System.Data.DataView> используется в качестве источника для запроса LINQ, а объекты <xref:System.Data.DataRowView>, которые были изменены и удалены, привязываются к элементу управления <xref:System.Windows.Forms.DataGridView>.  
  
 [!code-csharp[DP DataView Samples#QueryDataView2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#querydataview2)]
 [!code-vb[DP DataView Samples#QueryDataView2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#querydataview2)]  
  
 В следующем примере таблица продуктов создается из представления, привязанного к элементу управления <xref:System.Windows.Forms.DataGridView>. К объекту <xref:System.Data.DataView> выполняется запрос на получение продуктов красного цвета, а упорядоченные результаты привязываются к элементу управления <xref:System.Windows.Forms.DataGridView>.  
  
 [!code-csharp[DP DataView Samples#QueryDataView1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#querydataview1)]
 [!code-vb[DP DataView Samples#QueryDataView1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#querydataview1)]  
  
## <a name="see-also"></a>См. также

- [Привязка данных и LINQ to DataSet](data-binding-and-linq-to-dataset.md)
