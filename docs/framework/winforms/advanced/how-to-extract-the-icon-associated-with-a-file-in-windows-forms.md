---
title: Практическое руководство. Извлечение связанного с файлом значка в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
ms.openlocfilehash: c3173a3fa756a3294154217f5cf0a13dbc8721f3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645401"
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a>Практическое руководство. Извлечение связанного с файлом значка в Windows Forms
Большое количество файлов с внедренными значки, которые обеспечивают визуальное представление сопоставленного типа файлов. Например документы Microsoft Word содержит значок, который определяет их как документы Word. При отображении файлов в список элементов управления, или таблицы, можно отобразить значок, представляющий тип файла рядом с именами файлов. Вы можете сделать это с помощью <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> метод.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как извлекать значок, связанный с файлом и отобразить имя файла и его значок в <xref:System.Windows.Forms.ListView> элемента управления.  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы скомпилировать этот пример:  
  
- Вставьте приведенный выше код в форму Windows и вызовите `ExtractAssociatedIconExample` метод из конструктора формы или <xref:System.Windows.Forms.Form.Load> метод обработки событий.  
  
     Необходимо убедиться, что форма импортирует <xref:System.IO> пространства имен.  
  
## <a name="see-also"></a>См. также

- [Изображения, точечные рисунки и метафайлы](images-bitmaps-and-metafiles.md)
- [Элемент управления ListView](../controls/listview-control-windows-forms.md)
