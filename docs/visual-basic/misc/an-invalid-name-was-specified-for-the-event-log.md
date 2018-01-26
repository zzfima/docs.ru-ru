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
ms.openlocfilehash: 76e4082710a6786ec5e743ce606e849637c26512
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
 
