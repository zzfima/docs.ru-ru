---
title: Практическое руководство. Извлечение содержимого каталога "Мои документы" в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- My Documents directory
ms.assetid: 26560d01-7dda-4457-8e95-21db23d71aea
ms.openlocfilehash: 1d0536c65949dab7d431f3a4cb7b3293bddb7008
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-retrieve-the-contents-of-the-my-documents-directory-in-visual-basic"></a>Практическое руководство. Извлечение содержимого каталога "Мои документы" в Visual Basic
Объект <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> можно использовать для чтения из различных каталогов **Все пользователи**, таких как **Мои документы** или **Рабочий стол**.  
  
### <a name="to-read-from-the-my-documents-folder"></a>Чтение из папки "Мои документы"  
  
-   Для чтения текста из каждого файла в определенном каталоге используйте метод `ReadAllText`. В следующем коде определяется каталог и файл, а затем применяется метод `ReadAllText`, который считывает данные в строку с именем `patients`.  
  
     [!code-vb[VbVbcnMyFileSystem#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-retrieve-the-contents-of-the-my-documents-directory_1.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>
