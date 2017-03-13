---
title: "Практическое руководство. Запись текста в файлы в каталоге &quot;Мои документы&quot; в Visual Basic | Microsoft Docs"
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
  - "примеры [Visual Basic], текстовые файлы"
  - "файлы, запись в"
  - "текст, запись в файлы"
  - "запись в файлы, в папке "Мои документы""
ms.assetid: 1c726124-781d-4976-9baa-ed46814ff3fe
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Практическое руководство. Запись текста в файлы в каталоге &quot;Мои документы&quot; в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Объект `My.Computer.FileSystem.SpecialDirectories` позволяет получать доступ к специальным каталогам, таким как каталог **Мои документы**.  
  
## Процедура  
  
#### Чтобы записать новые текстовые файлы в каталог "Мои документы"  
  
1.  Укажите путь в свойстве `My.Computer.FileSystem.SpecialDirectories.MyDocuments`.  
  
     [!code-vb[VbFileIOWrite#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_1.vb)]  
  
2.  Используйте метод `WriteAllText` для записи текста в указанный файл.  
  
     [!code-vb[VbVbcnMyFileSystem#14](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_2.vb)]  
  
## Пример  
 [!code-vb[VbFileIOWrite#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_3.vb)]  
  
## Компиляция кода  
 Замените имя `test.txt` на имя файла, в который требуется выполнить запись.  
  
## Отказоустойчивость  
 Этот код возвращает все исключения, которые могут произойти при записи текста в файл.  Можно уменьшить вероятность возникновения исключений, используя элементы управления Windows Forms, такие как компоненты [OpenFileDialog](../Topic/OpenFileDialog%20Component%20\(Windows%20Forms\).md) и [SaveFileDialog](../Topic/SaveFileDialog%20Component%20\(Windows%20Forms\).md), которые позволяют пользователям выбирать только допустимые имена файлов.  Однако использование этих элементов управления не гарантирует полную надежность.  В период между моментом выбора пользователем файла и моментом выполнения кода файловая система может измениться.  Таким образом, при работе с файлами обработка исключений почти всегда является необходимой.  
  
## Безопасность платформы .NET Framework  
 Если код выполняется в контексте частичного доверия, исключение может возникнуть из\-за недостатка прав доступа.  Дополнительные сведения см. в разделе [Code Access Security Basics](../Topic/Code%20Access%20Security%20Basics.md).  
  
 В этом примере создается новый файл.  Если приложение создает файл, оно должно иметь разрешение на создание файла в соответствующем каталоге.  Для задания разрешений используется список управления доступом.  Если файл уже существует, приложению требуется лишь разрешение на запись.  Для повышения безопасности рекомендуется по возможности создавать файлы во время развертывания и предоставлять доступ на чтение только к одному файлу, а не доступ к каталогу с разрешением на создание.  По тем же соображениям рекомендуется сохранять данные в пользовательских каталогах, а не в корневом каталоге или каталоге **Program Files**.  Дополнительные сведения см. в разделе [ACL Technology Overview](http://msdn.microsoft.com/ru-ru/06fbf66d-6f02-4378-b863-b2f12e349045).  
  
## См. также  
 <xref:System.IO.Path.Combine%2A?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Devices.Computer>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>   
 <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>