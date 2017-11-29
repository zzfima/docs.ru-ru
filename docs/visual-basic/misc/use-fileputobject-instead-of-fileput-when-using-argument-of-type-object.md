---
title: "Использовать &#39; FilePutObject &#39; Вместо &#39; FilePut &#39; При использовании аргумента типа &#39; объект &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8cba4af206e2dbf767fdb883ec81229a67842c57
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="use-39fileputobject39-instead-of-39fileput39-when-using-argument-of-type-39object39"></a>Использовать &#39; FilePutObject &#39; Вместо &#39; FilePut &#39; При использовании аргумента типа &#39; объект &#39;
`FilePut` Метод включает аргумент типа `Object`. Чтобы избежать неоднозначности, следует использовать`FilePutObject` вместо `FilePut` .  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Замените `FilePut` объектом `FilePutObject`.  
  
-   Приведите аргумент `Object` к более конкретному типу.  
  
-   Используйте функциональность объекта `My.Computer.FileSystem` .  
  
## <a name="see-also"></a>См. также  
 [НЕ в СБОРКЕ: Функция FilePutObject](http://msdn.microsoft.com/en-us/a0f52a1c-5ecc-4945-b18c-03147af61d6b)  
 [Объект My.Computer.FileSystem](../../visual-basic/language-reference/objects/my-computer-filesystem-object.md)  
 [Метод My.Computer.FileSystem.WriteAllBytes](http://msdn.microsoft.com/en-us/b1a24dc1-eac8-4e22-8ffa-cc3bacbaf826)
