---
title: Недопустимый режим файла
ms.date: 07/20/2015
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
ms.openlocfilehash: 1d85f49ce0aed44dea12c9ba16135425e6e2e431
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565752"
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
- [Устранение неполадок: Чтение и запись в текстовый файл](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
