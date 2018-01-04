---
title: "Практическое руководство. Синхронизация элементов управления, связанных с одним источником данных"
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
helpviewer_keywords:
- controls [Windows Forms], binding multiple
- controls [Windows Forms], synchronizing with data source
ms.assetid: c2f0ecc6-11e6-4c2c-a1ca-0759630c451e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 227ad36e87c3deceb7fefe3cd19013fc8e76c686
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-ensure-multiple-controls-bound-to-the-same-data-source-remain-synchronized"></a>Практическое руководство. Синхронизация элементов управления, связанных с одним источником данных
Зачастую при работе с привязкой к данным в формах Windows Forms, несколько элементов управления привязаны к одному источнику данных. В некоторых случаях может потребоваться выполнить дополнительные действия для обеспечения синхронизация друг с другом и с источником данных связанных свойств элементов управления. Эти шаги необходимы в двух случаях:  
  
-   Если источник данных не реализует <xref:System.ComponentModel.IBindingList>и поэтому вызывает <xref:System.ComponentModel.IBindingList.ListChanged> события типа <xref:System.ComponentModel.ListChangedType.ItemChanged>.  
  
-   Если источник данных реализует <xref:System.ComponentModel.IEditableObject>.  
  
 В первом случае можно использовать <xref:System.Windows.Forms.BindingSource> для привязки источника данных к элементам управления. В последнем случае используется <xref:System.Windows.Forms.BindingSource> и обрабатывать <xref:System.Windows.Forms.BindingSource.BindingComplete> событий и вызовов <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> в связанном <xref:System.Windows.Forms.BindingManagerBase>.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как привязать три элемента управления — два элемента управления текстового поля и <xref:System.Windows.Forms.DataGridView> управления — в том же столбце в <xref:System.Data.DataSet> с помощью <xref:System.Windows.Forms.BindingSource> компонента. В этом примере показан способ обработки <xref:System.Windows.Forms.BindingSource.BindingComplete> событий и убедитесь, что при изменении одного текстового поля текстовое значение текстового поля и <xref:System.Windows.Forms.DataGridView> обновление с правильным значением элемента управления.  
  
 В этом примере <xref:System.Windows.Forms.BindingSource> для привязки источника данных и элементов управления. Кроме того, можно привязать элементы управления напрямую к источнику данных и извлечь <xref:System.Windows.Forms.BindingManagerBase> для привязки из формы <xref:System.Windows.Forms.Control.BindingContext%2A> и затем обрабатывать <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> событий для <xref:System.Windows.Forms.BindingManagerBase>. Пример того, как это сделать, см. на странице справки <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> событие <xref:System.Windows.Forms.BindingManagerBase>.  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
-   Для этого примера кода требуются  
  
-   ссылки на сборки <xref:System>, <xref:System.Windows.Forms> и <xref:System.Drawing>.  
  
-   Форма с <xref:System.Windows.Forms.Form.Load> событие как обработанное и вызов `InitializeControlsAndDataSource` метод в примере из формы <xref:System.Windows.Forms.Form.Load> обработчика событий.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Совместное использование одних и тех же данных в нескольких формах посредством компонента BindingSource](../../../docs/framework/winforms/controls/how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)  
 [Уведомления об изменениях в привязке данных Windows Forms](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [Интерфейсы, относящиеся к привязке данных](../../../docs/framework/winforms/interfaces-related-to-data-binding.md)  
 [Привязка данных Windows Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)
