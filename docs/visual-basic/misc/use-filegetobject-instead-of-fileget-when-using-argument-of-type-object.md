---
title: При использовании аргумента типа Object используйте метод FileGetObject вместо метода FileGet
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: 60eaabc686070aced908116728f06d4e82b5cecb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54723398"
---
# <a name="use-filegetobject-instead-of-fileget-when-using-argument-of-type-object"></a>При использовании аргумента типа Object используйте метод FileGetObject вместо метода FileGet
Метод `FileGet` включает аргумент типа `Object`. Чтобы избежать неоднозначности, следует использовать`FileGetObject` вместо `FileGet` .  
  
 Обратите внимание, что функциональные возможности, предлагаемые `My.Computer.Filesystem` , проще в использовании и обеспечивают большую производительность, чем `FileGet` или `FileGetObject`.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Замените `FileGet` объектом `FileGetObject`.  
  
2.  Приведите аргумент `Object` к более конкретному типу.  
  
## <a name="see-also"></a>См. также

- [My.Computer.FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)
