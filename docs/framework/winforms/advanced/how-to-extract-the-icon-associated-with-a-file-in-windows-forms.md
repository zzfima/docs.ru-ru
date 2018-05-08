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
ms.openlocfilehash: 21bce2f630649afb59272362a7f40055855ed512
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a>Практическое руководство. Извлечение связанного с файлом значка в Windows Forms
Число файлов с внедренными значки, которые предоставляют визуальное представление типа связанного файла. Например документы Microsoft Word содержат значок, который определяет их как документы Word. При отображении файлов в списке элементов управления, или таблицы, может потребоваться отображать значок, представляющий тип файла рядом с каждым именем файла. Легко сделать это с помощью <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> метод.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как извлекать значок, связанный с файлом и отобразить имя файла и его значок в <xref:System.Windows.Forms.ListView> элемента управления.  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы скомпилировать этот пример:  
  
-   Вставьте приведенный выше код в форму Windows Forms и вызовите `ExtractAssociatedIconExample` метод из конструктора формы или <xref:System.Windows.Forms.Form.Load> метод обработки события.  
  
     Необходимо убедиться, что форма импортирует <xref:System.IO> пространства имен.  
  
## <a name="see-also"></a>См. также  
 [Изображения, точечные рисунки и метафайлы](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Элемент управления ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)
