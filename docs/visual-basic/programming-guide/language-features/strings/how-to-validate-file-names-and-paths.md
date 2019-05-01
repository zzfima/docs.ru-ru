---
title: Практическое руководство. Проверка имен файлов и путей в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: c8e01a0f5a3f99fdbc424d6cd7d224367c7bad08
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032179"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a>Практическое руководство. Проверка имен файлов и путей в Visual Basic
Этот пример возвращает `Boolean` значение, указывающее, представляет ли строка имя файла или путь. Проверка, если имя содержит символы, которые не допускаются в файловой системе.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbcnRegEx#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#4)]  
  
 В этом примере не проверяет, если имя неправильно поместил запятой или каталогов без имени, или если длина имени превышает максимальную длину, определенную системой. Он также не проверяет имеет ли приложение разрешение на доступ к ресурсу файловой системы с указанным именем.  
  
## <a name="see-also"></a>См. также

- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [Проверка строк в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
