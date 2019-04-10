---
title: При использовании аргумента типа Object используйте метод FileGetObject вместо метода FileGet
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: fdad64a4b35aa792c996d25a9fd72a9ce1126fbd
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59306928"
---
# <a name="use-filegetobject-instead-of-fileget-when-using-argument-of-type-object"></a>При использовании аргумента типа Object используйте метод FileGetObject вместо метода FileGet
Метод `FileGet` включает аргумент типа `Object`. `FileGetObject` вместо `FileGet` .  
  
 Обратите внимание, что функциональные возможности, предлагаемые `My.Computer.Filesystem` , проще в использовании и обеспечивают большую производительность, чем `FileGet` или `FileGetObject`.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Замените `FileGet` объектом `FileGetObject`.  
  
2. Приведите аргумент `Object` к более конкретному типу.  
  
## <a name="see-also"></a>См. также

- [My.Computer.FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)
