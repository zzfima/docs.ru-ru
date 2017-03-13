---
title: "Практическое руководство. Проверка имен файлов и путей в Visual Basic | Microsoft Docs"
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
  - "логические значения"
  - "имена файла, проверка"
  - "пути, проверка"
  - "строки [Visual Basic], проверка"
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# Практическое руководство. Проверка имен файлов и путей в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Этот пример возвращает значение `Boolean`, определяющее, представляет ли строка имя файла или путь.  Проверка имения на содержание знаков, не допустимых в файловой системе.  
  
## Пример  
 [!code-vb[VbVbcnRegEx#4](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-file-names-and-paths_1.vb)]  
  
 В этом примере не выполняется проверка неправильно указанных двоеточий в имени, каталогов без имени, или длины имени, превышающей максимальную длину, определяемую системой.  Он также не проверяет, имеет ли приложение разрешение на доступ к ресурсу файловой системы с указанным именем.  
  
## См. также  
 <xref:System.IO.Path.GetInvalidPathChars%2A>   
 [Проверка строк в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)