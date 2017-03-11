---
title: "Запись данных в буфер обмена и чтение их оттуда (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "буфер обмена"
  - "буфер обмена, чтение из (My.Computer.Clipboard)"
  - "буфер обмена, сохранение данных в (My.Computer.Clipboard)"
  - "данные [Visual Basic], буфер обмена"
  - "My.Computer.Clipboard - объект, задачи"
  - "чтение данных, из буфера"
ms.assetid: f690119a-4378-4f7d-b20e-d9377ef49496
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Запись данных в буфер обмена и чтение их оттуда (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Буфер обмена можно использовать для хранения данных, таких как текст и изображения.  Поскольку буфер обмена используется совместно всеми активными процессами, его можно использовать для передачи данных между ними.  Объект `My.Computer.Clipboard` позволяет легко получать доступ буфер обмена и чтения и записи в него.  
  
## Чтение из буфера обмена  
 Используйте метод <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A> для чтения текста в буфере обмена.  Следующий код читает текст и отображает его в окне сообщения.  Для правильной работы примера в буфере обмена должен храниться текст.  
  
 [!code-vb[VbVbcnMyClipboard#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/storing-data-to-and-read_1.vb)]  
  
 Данный пример кода доступен также в качестве фрагмента кода IntelliSense.  В окне выбора фрагмента кода он находится в разделе **Приложения Windows Forms \> Буфер обмена**.  Дополнительные сведения см. в разделе [Фрагменты кода](/visual-studio/ide/code-snippets).  
  
 Для извлечения изображения из буфера обмена используйте метод <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A>.  В этом примере проверяется, есть ли изображение в буфере обмена, а затем изображение извлекается и отображается в элементе управления  `PictureBox1`.  
  
 [!code-vb[VbResourceTasks#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/storing-data-to-and-read_2.vb)]  
  
 Данный пример кода доступен также в качестве фрагмента кода IntelliSense.  В окне выбора фрагмента кода он находится в разделе **Приложения Windows Forms \> Буфер обмена**.Дополнительные сведения см. в разделе [Фрагменты кода](/visual-studio/ide/code-snippets).  
  
 Элементы, помещенные в буфер обмена, сохранятся даже после завершения работы приложения.  
  
## Указание типа файла, хранящегося в буфере обмена  
 Данные в буфере обмена могут принимать множество различных форм, таких как текст, звуковой файл или изображение.  Для того, чтобы определить, какой вид файла находится в буфере обмена, можно использовать такие методы как <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A> <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A> и <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A>.  Если необходимо проверить наличие данных некоторого пользовательского формата, можно использовать метод <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A>.  
  
 Чтобы определить, являются ли данные, содержащиеся в буфере обмена, изображениями, используйте функцию `ContainsImage`.  Следующий код проверяет, являются ли данные изображением, и выдает соответствующий отчет.  
  
 [!code-vb[VbResourceTasks#13](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/storing-data-to-and-read_3.vb)]  
  
## Очистить буфер обмена  
 Метод <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A> используется для очистки буфера обмена.  Поскольку буфер обмена используется совместно с другими процессами, его очистка может повлиять на эти процессы.  
  
 В следующем примере кода демонстрируется применение метода `Clear`.  
  
 [!code-vb[VbVbcnMyClipboard#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/storing-data-to-and-read_4.vb)]  
  
## Запись в буфер обмена  
 Используйте метод <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A> для записи текста в буфер обмена.  Следующий код записывает в буфер обмена строку "This is a test string".  
  
 [!code-vb[VbVbcnMyClipboard#1](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/storing-data-to-and-read_5.vb)]  
  
 Метод `SetText` может принимать параметр формата, который содержит тип <xref:System.Windows.Forms.TextDataFormat>.  Следующий код записывает в буфер обмена строку "This is a test string" в формате RTF.  
  
 [!code-vb[VbVbcnMyClipboard#2](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/storing-data-to-and-read_6.vb)]  
  
 Используйте метод <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A> для записи данных в буфер обмена.  Этот пример записывает объект `DataObject` `dataChunk` в буфер обмена в пользовательском формате `specialFormat`.  
  
 [!code-vb[VbVbcnMyClipboard#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/storing-data-to-and-read_7.vb)]  
  
 Для записи звуковых данных в буфер обмена используйте метод <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A>.  В этом примере создается массив байтов `musicReader`, в него считывается файл `cool.wav`, а затем этот файл записывается в буфер обмена.  
  
 [!code-vb[VbResourceTasks#5](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/storing-data-to-and-read_8.vb)]  
  
> [!IMPORTANT]
>  Поскольку доступ к буферу обмена могут получать другие пользователи, не следует использовать его для хранения важных сведений, таких как пароли или конфиденциальные данные.  
  
## См. также  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>   
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetAudioStream%2A>   
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetDataObject%2A>   
 [Практическое руководство. Чтение данных объекта из XML\-файла](../Topic/How%20to:%20Read%20Object%20Data%20from%20an%20XML%20File%20\(C%23%20and%20Visual%20Basic\).md)   
 [Практическое руководство. Запись данных объекта в XML\-файл](../Topic/How%20to:%20Write%20Object%20Data%20to%20an%20XML%20File%20\(C%23%20and%20Visual%20Basic\).md)