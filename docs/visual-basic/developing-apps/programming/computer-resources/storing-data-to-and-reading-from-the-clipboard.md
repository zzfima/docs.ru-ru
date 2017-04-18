---
title: "Запись данных в буфер обмена и чтение их оттуда (Visual Basic) | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Clipboard, storing data to (My.Computer.Clipboard)
- Clipboard, reading from (My.Computer.Clipboard)
- Clipboard
- My.Computer.Clipboard object, tasks
- data [Visual Basic], Clipboard
- reading data, from Clipboard
ms.assetid: f690119a-4378-4f7d-b20e-d9377ef49496
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a8580acf6fd23f9de264d3fed47d268898d498a6
ms.lasthandoff: 03/13/2017

---
# <a name="storing-data-to-and-reading-from-the-clipboard-visual-basic"></a>Запись данных в буфер обмена и чтение их оттуда (Visual Basic)
Буфер обмена можно использовать для хранения данных, таких как текст и изображения. Поскольку буфер обмена используется всеми активными процессами, с его помощью можно передавать данные из одного процесса в другой. Объект `My.Computer.Clipboard` позволяет легко обращаться к буферу обмена, считывать из него данные и выполнять в него запись.  
  
## <a name="reading-from-the-clipboard"></a>Чтение из буфера обмена  
 Чтобы прочитать текст из буфера обмена, используйте метод <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A>. Код в следующем примере считывает текст и отображает его в окне сообщения. Для правильной работы этого кода буфер обмена должен содержать какой-либо текст.  
  
 [!code-vb[VbVbcnMyClipboard#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_1.vb)]  
  
 Этот пример кода также доступен в качестве фрагмента кода IntelliSense. В средстве выбора фрагмента кода он расположен в разделе **Приложения Windows Forms > Буфер обмена**. Дополнительные сведения см. в статье [Фрагменты кода](https://docs.microsoft.com/visualstudio/ide/code-snippets).  
  
 Чтобы извлечь изображение из буфера обмена, используйте метод <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A>. Код в этом примере проверяет наличие изображения в буфере обмена, прежде чем извлекать его и назначать `PictureBox1`.  
  
 [!code-vb[VbResourceTasks#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_2.vb)]  
  
 Этот пример кода также доступен в качестве фрагмента кода IntelliSense. В средстве выбора фрагмента кода он расположен в разделе **Приложения Windows Forms > Буфер обмена**. Дополнительные сведения см. в разделе [Фрагменты кода](https://docs.microsoft.com/visualstudio/ide/code-snippets).  
  
 Элементы, добавленные в буфер обмена, сохраняются даже после того, как работа приложения завершается.  
  
## <a name="determining-the-type-of-file-stored-in-the-clipboard"></a>Определение типа файла, хранящегося в буфере обмена  
 В буфере обмена могут храниться данные в различных форматах, включая тексты, звуковые файлы и изображения. Чтобы определить, какого рода файл находится в буфере обмена, можно использовать методы <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A> и <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A>. Метод <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A> позволяет проверить наличие файла пользовательского формата.  
  
 Функция `ContainsImage` позволяет определить, являются ли данные в буфере обмена изображением. Следующий код проверяет, являются ли данные изображением, и выдает соответствующий отчет.  
  
 [!code-vb[VbResourceTasks#13](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_3.vb)]  
  
## <a name="clearing-the-clipboard"></a>Очистка буфера обмена  
 Метод <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A> очищает буфер. Поскольку буфер обмена используют и другие процессы, очищение буфера может плохо на них повлиять.  
  
 В следующем примере кода демонстрируется применение метода `Clear`.  
  
 [!code-vb[VbVbcnMyClipboard#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_4.vb)]  
  
## <a name="writing-to-the-clipboard"></a>Запись в буфер обмена  
 Чтобы записать текст в буфер обмена, используйте метод <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A>. Следующий код записывает в буфер обмена строку "This is a test string" (Это — тестовая строка).  
  
 [!code-vb[VbVbcnMyClipboard#1](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_5.vb)]  
  
 Метод `SetText` может принимать параметр формата, содержащий тип <xref:System.Windows.Forms.TextDataFormat>. Следующий код записывает строку "This is a test string" (Это — тестовая строка) в буфер обмена в формате RTF.  
  
 [!code-vb[VbVbcnMyClipboard#2](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_6.vb)]  
  
 Чтобы записать данные в буфер обмена, используйте метод <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A>. Код в этом примере записывает `DataObject``dataChunk` в буфер обмена в пользовательском формате `specialFormat`.  
  
 [!code-vb[VbVbcnMyClipboard#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_7.vb)]  
  
 Чтобы записать звуковые данные в буфер обмена, используйте метод <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A>. Код в этом примере создает массив байтов `musicReader`, считывает в него файл `cool.wav` и записывает его в буфер обмена.  
  
 [!code-vb[VbResourceTasks#5](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_8.vb)]  
  
> [!IMPORTANT]
>  Поскольку к буферу обмена могут обращаться другие пользователи, не храните в нем конфиденциальные данные, включая пароли.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>   
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetAudioStream%2A>   
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetDataObject%2A>   
 [Практическое руководство. Чтение данных объекта из XML-файла](../../../programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)   
 [Практическое руководство. Запись данных объекта в XML-файл](../../../programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)
