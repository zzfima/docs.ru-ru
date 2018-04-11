---
title: Недопустимый режим файла
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a540135727eb97f4df5027e2ded7271e21bb4648
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="bad-file-mode"></a>Недопустимый режим файла
Операторы, используемые для управления содержимым файла должны соответствовать режим, в котором открыт файл. Возможные причины:  
  
-   Объект `FilePutObject` или `FileGetObject` инструкция указывает последовательный файл.  
  
-   Объект `Print` инструкция указывает файл, открытый в режиме доступа, отличный от `Output` или `Append`.  
  
-   `Input` Инструкция указывает файл, открытый в режиме доступа, отличный от`Input`  
  
-   Попытка записи в файл только для чтения.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Убедитесь, что `FilePutObject` и `FileGetObject` ссылаются только на файлы, открытые для `Random` или `Binary` доступа.  
  
-   Убедитесь, что `Print` указывает файл, открытый в `Output` или `Append` режим доступа. В противном случае используйте другой инструкции для размещения данных в файл или открыть файл в нужный режим.  
  
-   Убедитесь, что `Input` задает файл, открытый для `Input`. В противном случае используйте другой инструкции для размещения данных в файл или открыть файл в нужный режим.  
  
-   При записи в файл только для чтения, изменения состояния чтения и записи файла или не пытайтесь выполнить запись в него.  
  
-   Используйте функциональность объекта `My.Computer.FileSystem` .  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.FileSystem>  
 [Исправление неполадок, связанных с чтением из текстовых файлов и записью в такие файлы](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
