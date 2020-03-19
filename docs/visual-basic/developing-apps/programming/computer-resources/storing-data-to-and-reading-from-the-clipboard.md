---
title: Запись данных в буфер обмена и чтение их оттуда
ms.date: 07/20/2015
helpviewer_keywords:
- Clipboard, storing data to (My.Computer.Clipboard)
- Clipboard, reading from (My.Computer.Clipboard)
- Clipboard
- My.Computer.Clipboard object, tasks
- data [Visual Basic], Clipboard
- reading data, from Clipboard
ms.assetid: f690119a-4378-4f7d-b20e-d9377ef49496
ms.openlocfilehash: 243fb237f3f9ba53f8b29079df08531c102c78dd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74349730"
---
# <a name="storing-data-to-and-reading-from-the-clipboard-visual-basic"></a>Запись данных в буфер обмена и чтение их оттуда (Visual Basic)

Буфер обмена можно использовать для хранения данных, таких как текст и изображения. Поскольку буфер обмена используется всеми активными процессами, с его помощью можно передавать данные из одного процесса в другой. Объект `My.Computer.Clipboard` позволяет легко обращаться к буферу обмена, считывать из него данные и выполнять в него запись.  
  
## <a name="reading-from-the-clipboard"></a>Чтение из буфера обмена  

 Используйте метод <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A> для чтения текста из буфера обмена. Код в следующем примере считывает текст и отображает его в окне сообщения. Для правильной работы этого кода буфер обмена должен содержать какой-либо текст.  
  
 [!code-vb[VbVbcnMyClipboard#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#4)]  
  
 Этот пример кода также доступен в качестве фрагмента кода IntelliSense. В средстве выбора фрагмента кода он расположен в разделе **Приложения Windows Forms > Буфер обмена**. Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).  
  
 Используйте метод <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A> для извлечения изображения из буфера обмена. Код в этом примере проверяет наличие изображения в буфере обмена, прежде чем извлекать его и назначать `PictureBox1`.  
  
 [!code-vb[VbResourceTasks#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#16)]  
  
 Этот пример кода также доступен в качестве фрагмента кода IntelliSense. В средстве выбора фрагмента кода он расположен в разделе **Приложения Windows Forms > Буфер обмена**. Дополнительные сведения см. в разделе [Фрагменты кода](/visualstudio/ide/code-snippets).  
  
 Элементы, добавленные в буфер обмена, сохраняются даже после того, как работа приложения завершается.  
  
## <a name="determining-the-type-of-file-stored-in-the-clipboard"></a>Определение типа файла, хранящегося в буфере обмена  

 В буфере обмена могут храниться данные в различных форматах, включая тексты, звуковые файлы и изображения. Чтобы определить, файл какого типа содержится в буфере обмена, можно использовать такие методы как <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A> и <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A>. Если вы используете для проверки пользовательский формат файла, можно использовать метод <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A>.  
  
 Функция `ContainsImage` позволяет определить, являются ли данные в буфере обмена изображением. Следующий код проверяет, являются ли данные изображением, и выдает соответствующий отчет.  
  
 [!code-vb[VbResourceTasks#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#13)]  
  
## <a name="clearing-the-clipboard"></a>Очистка буфера обмена  

 Метод <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A> очищает буфер обмена. Поскольку буфер обмена используют и другие процессы, очищение буфера может плохо на них повлиять.  
  
 В следующем примере кода демонстрируется применение метода `Clear`.  
  
 [!code-vb[VbVbcnMyClipboard#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#3)]  
  
## <a name="writing-to-the-clipboard"></a>Запись в буфер обмена  

 Используйте метод <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A> для записи текста в буфер обмена. Следующий код записывает в буфер обмена строку "This is a test string" (Это — тестовая строка).  
  
 [!code-vb[VbVbcnMyClipboard#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#1)]  
  
 Метод `SetText` может принимать параметр формата, который содержит тип <xref:System.Windows.Forms.TextDataFormat>. Следующий код записывает строку "This is a test string" (Это — тестовая строка) в буфер обмена в формате RTF.  
  
 [!code-vb[VbVbcnMyClipboard#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#2)]  
  
 Используйте метод <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A> для записи данных в буфер обмена. Код в этом примере записывает `DataObject` `dataChunk` в буфер обмена в пользовательском формате `specialFormat`.  
  
 [!code-vb[VbVbcnMyClipboard#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#7)]  
  
 Используйте метод <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A> для записи звуковых данных в буфер обмена. Код в этом примере создает массив байтов `musicReader`, считывает в него файл `cool.wav` и записывает его в буфер обмена.  
  
 [!code-vb[VbResourceTasks#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#5)]  
  
> [!IMPORTANT]
> Поскольку к буферу обмена могут обращаться другие пользователи, не храните в нем конфиденциальные данные, включая пароли.  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>
- <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetAudioStream%2A>
- <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetDataObject%2A>
- [Практическое руководство. Чтение данных объекта из XML-файла](../../../programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)
- [Практическое руководство. Запись данных объекта в XML-файл](../../../programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)
