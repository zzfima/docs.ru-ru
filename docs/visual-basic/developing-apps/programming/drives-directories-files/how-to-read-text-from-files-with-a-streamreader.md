---
title: Как выполнить Чтение текста из файлов с помощью StreamReader (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- reading files [Visual Basic], text
- text, reading from files
- reading text from files [Visual Basic]
- files [Visual Basic], reading
ms.assetid: 384033c6-18f9-4d59-9610-36371226558f
ms.openlocfilehash: 0ce3bffc151f149773c5279e1da08f74319b00f7
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968704"
---
# <a name="how-to-read-text-from-files-with-a-streamreader-visual-basic"></a>Как выполнить Чтение текста из файлов с помощью StreamReader (Visual Basic)
Объект `My.Computer.FileSystem` предоставляет методы для открытия <xref:System.IO.TextReader> и <xref:System.IO.TextWriter>. Методы `OpenTextFileWriter` и `OpenTextFileReader` являются дополнительными методами и отображаются в IntelliSense, только если выбрана вкладка **Все**.  
  
### <a name="to-read-a-line-from-a-file-with-a-text-reader"></a>Чтение строки из файла с помощью средства чтения текста  
  
-   Используйте `OpenTextFileReader` метод, чтобы открыть <xref:System.IO.TextReader>, указав файл. В этом примере открывается файл с именем `testfile.txt`, считывается строка из него и отображается в окне сообщения.  
  
     [!code-vb[VbFileIORead#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#1)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Файл, который считывается, должен быть текстовым файлом.  
  
 По имени файла не всегда можно с уверенностью судить о его содержимом. Например, файл с именем Form1.vb может вовсе не быть исходным файлом Visual Basic.  
  
 Следует проверять все входные данные перед использованием их в приложении. Содержимое файла может отличаться от ожидаемого, поэтому может не удаться прочесть файл с помощью методов чтения.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Для чтения из файла сборке требуется уровень привилегий, предоставляемый классом <xref:System.Security.Permissions.FileIOPermission>. Если код выполняется в контексте частичного доверия, исключение может возникнуть из-за недостатка прав доступа. Дополнительные сведения см. в разделе [Основы управления доступом для кода](../../../../framework/misc/code-access-security-basics.md). Пользователь также должен иметь доступ к файлу. Дополнительные сведения см. в разделе [Общие сведения о технологии ACL](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229742(v=vs.100)).  
  
## <a name="see-also"></a>См. также
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:System.Windows.Forms.OpenFileDialog>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A>
- [Компонент SaveFileDialog](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md)
- [Чтение из файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
