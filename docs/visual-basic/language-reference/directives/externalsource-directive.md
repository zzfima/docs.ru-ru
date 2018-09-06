---
title: '#ExternalSource-директива (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- '#Externalsource'
- '#ExternalSource'
- vb.ExternalSource
- Externalsource
- vb.#ExternalSource
- ExternalSource
helpviewer_keywords:
- ExternalSource directive (#ExternalSource)
- '#ExternalSource directive'
ms.assetid: 243bc6a2-34c3-4eeb-a776-9fd2bf988149
ms.openlocfilehash: dcde8507eb033d0a47d5c5d3fa36176cd63b0856
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861795"
---
# <a name="externalsource-directive"></a>Директива #ExternalSource
Указывает сопоставление между определенными строками исходного кода и текста, внешним по отношению к источнику.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a>Части  
 `StringLiteral`  
 Путь к внешнему источнику.  
  
 `IntLiteral`  
 Номер строки в первой строке из внешнего источника.  
  
 `LogicalLine`  
 Строка, где произошла ошибка из внешнего источника.  
  
 `#End ExternalSource`  
 Завершает блок `#ExternalSource`.  
  
## <a name="remarks"></a>Примечания  
 Эта директива используется только компилятор и отладчик.  
  
 Исходный файл может содержать директивы внешнего источника, которые задают сопоставление определенных строк кода в исходном файле и внешнего источника, например ASPX-файла текста. Если ошибки, возникающие в указанном исходном коде во время компиляции, они определяются как поступающие от внешнего источника.  
  
 Директивы внешнего источника не влияют на компиляцию и не могут быть вложенными. Они предназначены для внутреннего использования только приложением.  
  
## <a name="see-also"></a>См. также  
 [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
