---
title: "Недопустимое имя файла или номер"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3d7c8bae3df0e75a1c4f9afacdff681a553503d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="bad-file-name-or-number"></a>Недопустимое имя файла или номер
Произошла ошибка при попытке доступа к указанному файлу. Среди возможных причин этой ошибки являются:  
  
-   Инструкция ссылается на файл с именем файла или номер, который не был указан в `FileOpen` инструкции или был указан в `FileOpen` инструкции однако впоследствии был закрыт.  
  
-   Инструкция ссылается на файл с номером, который находится за пределами диапазона номеров файлов.  
  
-   Инструкция ссылается на имя файла или номер, который не является допустимым.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что имя файла задано в `FileOpen` инструкции. Обратите внимание, что при вызове `FileClose` оператор без аргументов, могут случайно закрыты все открытые файлы.  
  
2.  Если код создает номера файлов алгоритмически, убедитесь, что эти номера являются допустимыми.  
  
3.  Проверьте имена файлов, чтобы убедиться в том, что они соответствуют соглашениям операционной системы.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>  
 [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
