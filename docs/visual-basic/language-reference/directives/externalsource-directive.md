---
title: '#ExternalSource-директива'
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
ms.openlocfilehash: 146ab41d74b45acc4063e2463baca26c7caa4652
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586595"
---
# <a name="externalsource-directive"></a>Директива #ExternalSource
Указывает сопоставление между определенными строками исходного кода и текста, внешних по отношению к источнику.  
  
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
 Номер строки в первой строке внешнего источника.  
  
 `LogicalLine`  
 Строка, где произошла ошибка из внешнего источника.  
  
 `#End ExternalSource`  
 Завершает блок `#ExternalSource`.  
  
## <a name="remarks"></a>Примечания  
 Эта директива используется только компилятором и отладчиком.  
  
 Исходный файл может содержать директивы внешнего источника, которые задают сопоставление между определенные строки кода в файле исходного кода и текстом, внешним по отношению к источнику, например ASPX-файл. Если ошибки, возникающие в указанном коде источника во время компиляции, они определяются как поступающие из внешнего источника.  
  
 Директивы внешнего источника не влияют на компиляцию и не могут быть вложенными. Они предназначены для внутреннего использования только приложением.  
  
## <a name="see-also"></a>См. также  
 [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
