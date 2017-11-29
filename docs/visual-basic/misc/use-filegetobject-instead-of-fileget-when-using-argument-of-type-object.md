---
title: "Использовать &#39; FileGetObject &#39; Вместо &#39; FileGet &#39; При использовании аргумента типа &#39; объект &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 090b8088-895a-482a-9362-606596bac304
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 996e8a50f90c738bbc64c200125a785c0e9bcd58
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="use-39filegetobject39-instead-of-39fileget39-when-using-argument-of-type-39object39"></a>Использовать &#39; FileGetObject &#39; Вместо &#39; FileGet &#39; При использовании аргумента типа &#39; объект &#39;
Метод `FileGet` включает аргумент типа `Object`. Чтобы избежать неоднозначности, следует использовать`FileGetObject` вместо `FileGet` .  
  
 Обратите внимание, что функциональные возможности, предлагаемые `My.Computer.Filesystem` , проще в использовании и обеспечивают большую производительность, чем `FileGet` или `FileGetObject`.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Замените `FileGet` объектом `FileGetObject`.  
  
2.  Приведите аргумент `Object` к более конкретному типу.  
  
## <a name="see-also"></a>См. также  
 [НЕ в СБОРКЕ. Функция FileGetObject](http://msdn.microsoft.com/en-us/3eda786b-d1ee-4b44-9dd7-0ea6bff072c0)  
 [Объект My.Computer.FileSystem](../../visual-basic/language-reference/objects/my-computer-filesystem-object.md)
