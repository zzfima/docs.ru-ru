---
title: "Указано недопустимое имя для журнала событий"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: b1b158bd-f13f-4371-a8af-31c0e86ae6be
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fc5a2e93541063a129efaa0ce08fc19a98372126
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="an-invalid-name-was-specified-for-the-event-log"></a>Указано недопустимое имя для журнала событий
Для журнала событий было указано недопустимое имя. Обычно это является результатом недопустимых символов в имени, пустого имени файла или слишком длинного имени файла.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Если указанное имя содержит более восьми символов, убедитесь, что отсутствует конфликт с именами других журналов событий. При определении уникальности имени оцениваются только первые восемь символов.  
  
-   Если указывается путь, убедитесь, что он анализируется правильно.  
  
-   Проверьте имя на наличие недопустимых символов. Символы, которые нельзя использовать в имени файла: `<`, `>`, `:`, `"`, `/`, `\`и `|`.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Анализ путей к файлам](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)  
 [Практическое руководство. Переименование файла](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)  
 [Как: создавать и удалять журналы событий.](http://msdn.microsoft.com/en-us/af9b7da0-80c7-46ac-b7f7-897063ddd503)
