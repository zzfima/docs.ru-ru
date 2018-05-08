---
title: Используйте &#39;FileGetObject&#39; вместо &#39;FileGet&#39; при использовании аргумента типа &#39;объекта&#39;
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: 2edb80f6df95774e0ea5a7b51e57925845d7ba75
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="use-39filegetobject39-instead-of-39fileget39-when-using-argument-of-type-39object39"></a>Используйте &#39;FileGetObject&#39; вместо &#39;FileGet&#39; при использовании аргумента типа &#39;объекта&#39;
Метод `FileGet` включает аргумент типа `Object`. Чтобы избежать неоднозначности, следует использовать`FileGetObject` вместо `FileGet` .  
  
 Обратите внимание, что функциональные возможности, предлагаемые `My.Computer.Filesystem` , проще в использовании и обеспечивают большую производительность, чем `FileGet` или `FileGetObject`.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Замените `FileGet` объектом `FileGetObject`.  
  
2.  Приведите аргумент `Object` к более конкретному типу.  
  
## <a name="see-also"></a>См. также  
   
 [My.Computer.FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)
