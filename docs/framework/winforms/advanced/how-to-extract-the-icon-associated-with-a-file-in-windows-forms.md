---
title: Как извлечь значок, связанный с файлом
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
ms.openlocfilehash: 28769144b0e1c631a31c3c541747a6215f861d0e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742539"
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a>Практическое руководство. Извлечение связанного с файлом значка в Windows Forms
Многие файлы имеют встроенные значки, которые предоставляют визуальное представление связанного типа файлов. Например, документы Microsoft Word содержат значок, который идентифицирует их как документы Word. При отображении файлов в элементе управления "список" или "Таблица" может потребоваться отобразить значок, представляющий тип файла рядом с каждым именем файла. Это можно легко сделать с помощью метода <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A>.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как извлечь значок, связанный с файлом, и отобразить имя файла и связанный с ним значок в элементе управления <xref:System.Windows.Forms.ListView>.  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы скомпилировать пример:  
  
- Вставьте приведенный выше код в форму Windows Forms и вызовите метод `ExtractAssociatedIconExample` из конструктора формы или <xref:System.Windows.Forms.Form.Load> метода обработки событий.  
  
     Необходимо убедиться, что форма импортирует пространство имен <xref:System.IO>.  
  
## <a name="see-also"></a>См. также раздел

- [Изображения, точечные рисунки и метафайлы](images-bitmaps-and-metafiles.md)
- [Элемент управления ListView](../controls/listview-control-windows-forms.md)
