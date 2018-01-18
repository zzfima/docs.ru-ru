---
title: "Объекты DataTableReader"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: b5160f5a2c68cab798dde154275c062e2bf31739
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="datatablereaders"></a>Объекты DataTableReader
<xref:System.Data.DataTableReader> представляет содержимое объекта <xref:System.Data.DataTable> или <xref:System.Data.DataSet> в виде одного или нескольких результирующих наборов, предназначенных только для чтения и только для перенаправления.  
  
 При создании **DataTableReader** из **DataTable**, итоговый **DataTableReader** объект содержит один результирующий набор с теми же данными, как  **DataTable** из которой он был создан, за исключением любых строк, которые были помечены как удаленные. Столбцы отображаются в том же порядке, как и в исходном **DataTable**.  
  
 Объект **DataTableReader** может содержать несколько результирующих наборов, если он был создан путем вызова <xref:System.Data.DataSet.CreateDataReader%2A>. Результаты возвращаются в том же порядке, что **DataTables** в **DataSet** объекта <xref:System.Data.DataSet.Tables%2A> коллекции.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Создание объекта DataReader](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datareader.md)  
 Описывает создание **DataTableReader** объекта.  
  
 [Навигация в объектах DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datatables.md)  
 Описывает использование **чтения** метод для перемещения по содержимое **DataTableReader**.  
  
## <a name="see-also"></a>См. также  
 [Извлечение и изменение данных в ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
