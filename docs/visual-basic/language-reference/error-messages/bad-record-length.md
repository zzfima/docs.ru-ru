---
title: Недопустимая длина записи
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 747d62cb41ef841b4486e0c7108c37a86929683e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="bad-record-length"></a>Недопустимая длина записи
Некоторые из возможных причин этой ошибки:  
  
-   Длина переменной записи, указанной в `FileGet`, `FileGetObject`, `FilePut` или `FilePutObject` оператор отличается от длины, указанной в соответствующем `FileOpen` инструкции.  
  
-   Переменная в `FilePut` или `FilePutObject` инструкция или включает строку переменной длины.  
  
-   Переменная в `FilePut` или `FilePutObject` является или включает `Variant` типа.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что сумма размеров переменных фиксированной длины в определяемый пользователем тип, определение типа переменной записи совпадает со значением, заданным в `FileOpen` оператора `Len` предложения.  
  
2.  Если переменная в `FilePut` или `FilePutObject` инструкция или включает строку переменной длины, убедитесь, что строка переменной длины по крайней мере 2 символа короче длины записи, указанной в `Len` предложения `FileOpen` инструкция.  
  
3.  Если переменная в `FilePut` или `FilePutObject` является или включает `Variant` убедитесь, что строка переменной длины по крайней мере 4 байта короче длины записи, указанной в `Len` предложения `FileOpen` инструкции.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
