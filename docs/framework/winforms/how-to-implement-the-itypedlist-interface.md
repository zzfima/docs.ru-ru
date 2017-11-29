---
title: "Практическое руководство. Реализация интерфейса ITypedList"
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
- ITypedList interface
- BindingList(Of T) class
- data binding [Windows Forms], implementing
- IBindingList interface
ms.assetid: 834cc15c-50bc-4a8b-a610-313d6a217357
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 95888fc5c0df31529db429ead0e7d3e342f9a6e5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-the-itypedlist-interface"></a>Практическое руководство. Реализация интерфейса ITypedList
Реализуйте <xref:System.ComponentModel.ITypedList> интерфейс, чтобы включить обнаружение схемы для связываемого списка.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как реализовать <xref:System.ComponentModel.ITypedList> интерфейса. Универсальный тип с именем `SortableBindingList` является производным от <xref:System.ComponentModel.BindingList%601> класс и реализует <xref:System.ComponentModel.ITypedList> интерфейса. Простой класс с именем `Customer` предоставляет данные, которые привязаны к заголовку <xref:System.Windows.Forms.DataGridView> элемента управления.  
  
 [!code-csharp[System.ComponentModel.ITypedList#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/SortableBindingList.cs#1)]
 [!code-vb[System.ComponentModel.ITypedList#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/SortableBindingList.vb#1)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Customer.cs#10)]
 [!code-vb[System.ComponentModel.ITypedList#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Customer.vb#10)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#100](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Form1.cs#100)]
 [!code-vb[System.ComponentModel.ITypedList#100](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Form1.vb#100)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System.Drawing и System.Windows.Forms.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ComponentModel.ITypedList>  
 <xref:System.ComponentModel.BindingList%601>  
 <xref:System.ComponentModel.IBindingList>  
 [Привязка данных и Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
