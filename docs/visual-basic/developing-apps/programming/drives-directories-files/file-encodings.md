---
title: "Кодировки файлов (Visual Basic)"
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
- character encodings
- files, encoding
- Unicode, file encoding
- file encoding
ms.assetid: ea2c5f5f-bbb1-4150-9928-b9951fa6bc57
caps.latest.revision: 8
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6d4a12d3c6098271dad0a52a9c6799303b9fe81d
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="file-encodings-visual-basic"></a>Кодировки файлов (Visual Basic)
Кодировки файлов (или кодировки символов) определяют отображение символов при обработке текстов. Одна кодировка может быть предпочтительнее другой с точки зрения возможности или невозможности оперирования языковыми символами, хотя обычно предпочитается Юникод.  
  
 При чтении или записи в файлы несоответствие кодировок файлов может привести к исключениям или неверным результатам.  
  
## <a name="types-of-encodings"></a>Типы кодировок  
 Юникод является предпочтительной кодировкой при работе с файлами. Юникод — мировой стандарт кодировки символов, в котором используются 16-разрядные кодовые значения для представления всех символов, используемых в современных вычислениях, включая технические символы и специальные символы, используемые в издательском деле.  
  
 Предыдущие стандарты кодировок состояли из традиционных наборов знаков, таких как набор знаков ANSI Windows, использующий 8-разрядные кодовые значения, или комбинаций из 8-разрядных кодовых значений для представления символов, используемых в конкретном языке или географическом регионе.  
  
## <a name="encoding-class"></a>Класс Encoding  
 Класс <xref:System.Text.Encoding> представляет кодировку символов. В этой таблице перечислены типы доступных кодировок и дано их описание.  
  
|Имя|Описание|
|---|---|    
|<xref:System.Text.ASCIIEncoding>|Представляет кодировку ASCII символов Юникода.|  
|<xref:System.Text.UnicodeEncoding>|Представляет кодировку символов Юникода в формате UTF-16.|  
|<xref:System.Text.UTF32Encoding>|Представляет кодировку символов Юникода в формате UTF-32.|  
|<xref:System.Text.UTF7Encoding>|Представляет кодировку UTF-7 символов Юникода.|  
|<xref:System.Text.UTF8Encoding>|Представляет кодировку символов Юникода в формате UTF-8.|  
  
## <a name="see-also"></a>См. также  
 [Чтение из файлов](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)   
 [Запись в файлы](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)

