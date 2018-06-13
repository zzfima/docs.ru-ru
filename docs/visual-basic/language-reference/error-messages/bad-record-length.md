---
title: Недопустимая длина записи
ms.date: 07/20/2015
f1_keywords:
- vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
ms.openlocfilehash: b4b311e2eb504c485772091ed126b3beb71729cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585974"
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
