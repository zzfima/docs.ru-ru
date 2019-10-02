---
title: '#Директива ExternalSource (Visual Basic)'
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
ms.openlocfilehash: ac7096e998dd8d2a416dc739e1d7625e1abff7a6
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696827"
---
# <a name="externalsource-directive"></a>Директива #ExternalSource
Указывает сопоставление между конкретными строками исходного кода и текстом, внешним по отношению к источнику.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a>Части  
 `StringLiteral`  
 Путь к внешнему источнику.  
  
 `IntLiteral`  
 Номер строки первой строки внешнего источника.  
  
 `LogicalLine`  
 Строка, в которой возникла ошибка во внешнем источнике.  
  
 `#End ExternalSource`  
 Завершает блок `#ExternalSource`.  
  
## <a name="remarks"></a>Примечания  
 Эта директива используется только компилятором и отладчиком.  
  
 Исходный файл может содержать директивы External Source, которые указывают на сопоставление между конкретными строками кода в исходном файле и внешним по отношению к источнику текстом, например ASPX-файлу. Если во время компиляции обнаружены ошибки в указанном исходном коде, они определяются как поступающие из внешнего источника.  
  
 Директивы External Source не влияют на компиляцию и не могут быть вложенными. Они предназначены только для внутреннего использования приложением.  
  
## <a name="see-also"></a>См. также

- [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
