---
title: "Практическое руководство. Извлечение содержимого каталога &quot;Мои документы&quot; в Visual Basic | Документы Майкрософт"
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
- My Documents directory
ms.assetid: 26560d01-7dda-4457-8e95-21db23d71aea
caps.latest.revision: 13
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 39e1d8b4d7e613bf245769816ef24a7787f41e04
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-retrieve-the-contents-of-the-my-documents-directory-in-visual-basic"></a>Практическое руководство. Извлечение содержимого каталога "Мои документы" в Visual Basic
Объект <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> можно использовать для чтения из различных каталогов **Все пользователи**, таких как **Мои документы** или **Рабочий стол**.  
  
### <a name="to-read-from-the-my-documents-folder"></a>Чтение из папки "Мои документы"  
  
-   Для чтения текста из каждого файла в определенном каталоге используйте метод `ReadAllText`. В следующем коде определяется каталог и файл, а затем применяется метод `ReadAllText`, который считывает данные в строку с именем `patients`.  
  
     [!code-vb[VbVbcnMyFileSystem#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-retrieve-the-contents-of-the-my-documents-directory_1.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>
