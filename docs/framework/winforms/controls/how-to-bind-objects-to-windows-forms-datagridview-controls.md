---
title: Связывание объектов с элементами управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], object binding
- data grids [Windows Forms], object binding
- object binding [Windows Forms], DataGridView control
ms.assetid: cb8f29fa-577e-4e2b-883f-3a01c6189b9c
ms.openlocfilehash: d5aa5cb64c7fb2b82d69d6c87134ee901b84f5c1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746698"
---
# <a name="how-to-bind-objects-to-windows-forms-datagridview-controls"></a>Практическое руководство. Связывание объектов с элементами управления DataGridView в Windows Forms
В следующем примере кода показано, как связать коллекцию объектов с элементом управления <xref:System.Windows.Forms.DataGridView>, чтобы каждый объект отображался отдельной строкой. В этом примере также показано, как отобразить свойство с типом перечисления в <xref:System.Windows.Forms.DataGridViewComboBoxColumn>, чтобы в раскрывающемся списке для поля со списком содержались значения перечисления.  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Windows.Forms.DataGridView._CollectionBound#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/CS/collectionbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView._CollectionBound#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/VB/collectionbound.vb#00)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- ссылки на сборки System и System.Windows.Forms.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- [Отображение данных с помощью элемента управления DataGridView в Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Практическое руководство. Доступ к связанным объектам в строках DataGridView в Windows Forms](how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)
