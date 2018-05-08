---
title: Практическое руководство. Проверка имен файлов и путей в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: ab3df335bc5bba21d386bb69b12d840990e629fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a>Практическое руководство. Проверка имен файлов и путей в Visual Basic
Этот пример возвращает `Boolean` значение, указывающее, представляет ли строка имя файла или путь. Проверяется, если имя содержит символы, которые не разрешены в файловой системе.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbcnRegEx#4](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-file-names-and-paths_1.vb)]  
  
 В этом примере не проверяет, если имя поместил неправильно двоеточия, или каталоги без имени или если длина имени превышает максимальную длину, определенная системой. Он также не проверяет имеет ли приложение разрешение на доступ к ресурсу файловой системы с указанным именем.  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO.Path.GetInvalidPathChars%2A>  
 [Проверка строк в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
