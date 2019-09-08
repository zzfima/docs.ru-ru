---
title: Привязка данных и LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 310bff4a-32dd-4f20-a271-6dbd82912631
ms.openlocfilehash: 563d57249daa3aa720da1d9654866727f770afb3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786700"
---
# <a name="data-binding-and-linq-to-dataset"></a>Привязка данных и LINQ to DataSet
*Привязка данных* — это процесс, который устанавливает соединение между пользовательским интерфейсом приложения и бизнес-логикой. Если для привязки заданы правильные настройки, а изменения значений данных сопровождаются правильными уведомлениями, привязанные к данным элементы автоматически отражают изменения. Объект <xref:System.Data.DataSet> - это находящееся в памяти представление данных, обеспечивающее согласованную реляционную программную модель, независимо от источника содержащихся в нем данных. Объект <xref:System.Data.DataView> в ADO.NET 2.0 позволяет сортировать и фильтровать данные, хранящиеся в таблице <xref:System.Data.DataTable>. Эта функциональность часто используется в приложениях привязки данных. С помощью объекта <xref:System.Data.DataView> можно представлять данные в таблице с различными порядками сортировки, а также фильтровать данные по состоянию строки или на основе критерия фильтра. Дополнительные сведения об объекте см <xref:System.Data.DataView> . в разделе " [представления](./dataset-datatable-dataview/dataviews.md)данных".  
  
 LINQ to DataSet позволяет разработчикам создавать сложные, эффективные запросы <xref:System.Data.DataSet> с помощью. [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] Однако запрос LINQ to DataSet возвращает перечисление <xref:System.Data.DataRow> объектов, которое несложно использовать в сценарии привязки. Чтобы упростить привязку, можно создать <xref:System.Data.DataView> запрос из LINQ to DataSet запроса. При <xref:System.Data.DataView> этом используется фильтрация и сортировка, указанные в запросе, но лучше подходят для привязки данных. LINQ to DataSet расширяет функциональные возможности, <xref:System.Data.DataView> предоставляя [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] фильтрацию и сортировку на основе выражений, что позволяет выполнять гораздо более сложные и эффективные операции фильтрации и сортировки по сравнению с фильтрацией и сортировкой на основе строк.  
  
 Обратите внимание, что объект <xref:System.Data.DataView> представляет непосредственно запрос, а не представление на основе запроса. Объект <xref:System.Data.DataView> привязывается к элементу управления в пользовательском интерфейсе, так же как и <xref:System.Windows.Forms.DataGrid> или <xref:System.Windows.Forms.DataGridView>, обеспечивая простую модель привязки данных. Объект <xref:System.Data.DataView> можно также создать на основе объекта <xref:System.Data.DataTable>, задав представление таблицы по умолчанию.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Создание объекта DataView](creating-a-dataview-object-linq-to-dataset.md)  
 Содержит сведения о создании объекта <xref:System.Data.DataView>.  
  
 [Фильтрация с использованием объекта DataView](filtering-with-dataview-linq-to-dataset.md)  
 Описывает фильтрацию с помощью объекта <xref:System.Data.DataView>.  
  
 [Сортировка с использованием объекта DataView](sorting-with-dataview-linq-to-dataset.md)  
 Описывает сортировку с помощью объекта <xref:System.Data.DataView>.  
  
 [Запрос к коллекции DataRowView в объекте DataView](querying-the-datarowview-collection-in-a-dataview.md)  
 Содержит сведения о запросах к коллекции <xref:System.Data.DataRowView>, предоставляемой объектом <xref:System.Data.DataView>.  
  
 [Производительность объекта DataView](dataview-performance.md)  
 Содержит сведения об объекте <xref:System.Data.DataView> и производительности.  
  
 [Практическое руководство. Привязка объекта DataView к элементу управления Windows Forms DataGridView](how-to-bind-a-dataview-object-to-a-winforms-datagridview-control.md)  
 Содержит описание процесса привязки объекта <xref:System.Data.DataView> к элементу управления <xref:System.Windows.Forms.DataGridView>.  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию](programming-guide-linq-to-dataset.md)
