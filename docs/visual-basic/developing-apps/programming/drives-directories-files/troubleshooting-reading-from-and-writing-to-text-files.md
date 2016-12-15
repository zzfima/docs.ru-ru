---
title: "Исправление неполадок, связанных с чтением из текстовых файлов и записью в такие файлы (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ввод-вывод [Visual Basic], устранение неполадок с текстовыми файлами"
  - "чтение текстовых файлов, устранение неполадок"
  - "устранение неполадок файлового ввода-вывода"
  - "устранение неполадок - Visual Basic, текстовые файлы"
  - "запись текста в файлы, устранение неполадок"
  - "запись в файлы, устранение неполадок"
ms.assetid: a8e9b44d-facb-4718-8c0f-466537171182
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Исправление неполадок, связанных с чтением из текстовых файлов и записью в такие файлы (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

В этом разделе обсуждаются распространенные неполадки, с которыми приходится сталкиваться при работе с текстовыми файлами, и предлагаются способы их устранения.  
  
## Неполадки общего характера  
 К наиболее распространенным неполадкам, возникающим при работе с текстовыми файлами, относятся исключения безопасности, файловые кодировки или недопустимые пути.  
  
### Исключения безопасности  
 <xref:System.Security.SecurityException> создается при возникновении ошибки безопасности.  Часто это является результатом отсутствия у пользователя необходимых разрешений. Устранить эту проблему можно, предоставив дополнительные разрешения, или организовав работу с файлами в изолированном хранилище.  Дополнительные сведения см. в разделе [Разрешение вопросов, связанных с исключениями: System.Security.SecurityException](../Topic/Troubleshooting%20Exceptions:%20System.Security.SecurityException.md).  
  
### Кодировки файлов  
 Кодировки файлов, также называемые кодировками символов, определяют способ представления символов при обработке текста.  Непредвиденные символы в текстовом файле могут быть результатом неверной кодировки.  Одна кодировка может быть предпочтительнее другой с точки зрения возможности или невозможности оперирования языковыми символами, хотя обычно предпочитается Юникод.  Дополнительные сведения см. в разделах [Кодировки файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md) и <xref:System.Text.Encoding>.  
  
### Неверные пути  
 При анализе путей к файлам, особенно относительных путей, легко указать неверные данные.  Многие неполадки можно исправить, проверяя правильность указанного пути.  Дополнительные сведения см. в разделе [Практическое руководство. Анализ путей к файлам](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md).  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 [Чтение из файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)   
 [Запись в файлы](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)   
 [Анализ текстовых файлов с помощью объекта TextFieldParser](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)