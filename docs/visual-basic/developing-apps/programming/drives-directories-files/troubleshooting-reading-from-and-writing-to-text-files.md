---
title: Исправление неполадок, связанных с чтением из текстовых файлов и записью в них
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting file I/O
- writing text to files [Visual Basic], troubleshooting
- troubleshooting Visual Basic, text files
- I/O [Visual Basic], troubleshooting text files
- writing to files [Visual Basic], troubleshooting
- reading text files [Visual Basic], troubleshooting
ms.assetid: a8e9b44d-facb-4718-8c0f-466537171182
ms.openlocfilehash: dbc53ca3cc9ae9b2d14b925f891d0409b2b7debd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333790"
---
# <a name="troubleshooting-reading-from-and-writing-to-text-files-visual-basic"></a>Исправление неполадок, связанных с чтением из текстовых файлов и записью в такие файлы (Visual Basic)

В этом разделе обсуждаются распространенные проблемы, возникающие при работе с текстовыми файлами, и предлагаются способы их устранения.  
  
## <a name="common-problems"></a>Распространенные проблемы  

 Чаще всего при работе с текстовыми файлами возникают проблемы, связанные с исключениями безопасности, кодировкой файлов и неверными путями.  
  
### <a name="security-exceptions"></a>Исключения безопасности  

 Исключение <xref:System.Security.SecurityException> создается в случае ошибки безопасности. Обычно проблема возникает из-за отсутствия необходимых разрешений и устраняется путем добавления разрешений или работы с файлами в изолированном хранилище.  
  
### <a name="file-encodings"></a>Кодировки файлов  

 Кодировки файлов (или кодировки символов) определяют отображение символов при обработке текстов. При неправильной кодировке в текстовом файле могут появиться непредвиденные символы. Для большинства файлов больше подходят определенные кодировки (это связано с тем, какие языковые символы они могут или не могут обрабатывать), хотя обычно предпочтительной является кодировка Юникод. Дополнительные сведения см. в статьях [Кодировки файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md) и <xref:System.Text.Encoding>.  
  
### <a name="incorrect-paths"></a>Неверные пути  

 Прописывая пути к файлам (особенно если речь идет об относительных путях), легко ошибиться. Большинство неполадок можно устранить, просто проверив правильность указанного пути. Дополнительные сведения см. в разделе [Практическое руководство. Анализ путей к файлам](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md).  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- [Чтение из файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
- [Запись в файлы](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
- [Анализ текстовых файлов с помощью объекта TextFieldParser](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
