---
title: "Практическое руководство. Извлечение связанного с файлом значка в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "отображение имени файла и значка типа файла в элементе управления ListView [Windows Forms]"
  - "извлечение значков, связанных с типом файла [Windows Forms]"
  - "значки расширений типов файлов [Windows Forms], отображение в ListView"
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Извлечение связанного с файлом значка в Windows Forms
У многих файлов имеются внедренные значки, которые служат для визуального представления соответствующего типа файла.  Например, документы Microsoft Word содержат значок, который указывает на то, что эти файлы являются документами Word.  При отображении файлов в таких элементах управления, как список или таблица, может потребоваться поместить рядом с именем файла значок, обозначающий тип этого файла.  Для этого достаточно вызвать метод <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A>.  
  
## Пример  
 В следующем примере показано, как извлечь связанный с файлом значок и вывести его на экран рядом именем файла в элементе управления <xref:System.Windows.Forms.ListView>.  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## Компиляция кода  
 Чтобы скомпилировать этот пример, выполните следующие действия.  
  
-   Вставьте предыдущий код в форму Windows Form и вызовите метод `ExtractAssociatedIconExample` из конструктора или метода обработки события формы <xref:System.Windows.Forms.Form.Load>.  
  
     Необходимо проверить, что форма импортирует пространство имен <xref:System.IO>.  
  
## См. также  
 [Работа с растровыми и векторными изображениями с использованием классов Image, Bitmap и Metafile](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [Элемент управления ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)