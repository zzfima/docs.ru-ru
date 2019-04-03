---
title: Недопустимый режим файла
ms.date: 07/20/2015
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
ms.openlocfilehash: d3d0ebd003f178567ec9e9b19d6baccb8bc15f60
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819987"
---
# <a name="bad-file-mode"></a>Недопустимый режим файла
Операторы, используемые для управления содержимое файла должны соответствовать в режим, в котором был открыт файл. Возможные причины:  
  
-   Объект `FilePutObject` или `FileGetObject` инструкция указывает последовательный файл.  
  
-   Объект `Print` инструкция указывает файл, открытый в режиме доступа, отличное от `Output` или `Append`.  
  
-   `Input` Инструкция указывает файл, открытый в режиме доступа, отличное от `Input`  
  
-   Предпринята попытка записи в файл только для чтения.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Убедитесь, что `FilePutObject` и `FileGetObject` ссылаются только на файлы, открытые для `Random` или `Binary` доступа.  
  
-   Убедитесь, что `Print` указывает файл, открытый в `Output` или `Append` режим доступа. В противном случае используйте другой инструкции для размещения данных в файл или открыть файл в нужный режим.  
  
-   Убедитесь, что `Input` указывает файл, открытый в `Input`. В противном случае используйте другой инструкции для размещения данных в файл или открыть файл в нужный режим.  
  
-   Если вы создаете в файл только для чтения, изменить состояние чтения и записи файла или не пытайтесь для записи в него.  
  
-   Используйте функциональность объекта `My.Computer.FileSystem` .  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.FileSystem>
- [Устранение неполадок. Чтение из текстовых файлов и запись в такие файлы](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
