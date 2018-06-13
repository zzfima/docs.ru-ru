---
title: -highentropyva (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fef3f922d3089eaca1762ffe35fa38cfe94baf22
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656339"
---
# <a name="-highentropyva-visual-basic"></a>-highentropyva (Visual Basic)
Указывает, 64-разрядный исполняемый файл или исполняемый файл, помеченный атрибутом [/Platform: anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) параметр компилятора поддерживает технологию Address Space макета Randomization (ASLR) с высокой энтропией.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
 `+` &#124; `-`  
 Необязательный. Параметр отключен по умолчанию или при указании `-highentropyva-`. Параметр — Если указать `-highentropyva` или `-highentropyva+`.  
  
## <a name="remarks"></a>Примечания  
 Если этот параметр указан, совместимые версии ядра Windows можно использовать более высокие степени энтропии при ядра случайный выбор из своего структуры адресного пространства процесса в рамках ASLR. Если ядро использует более высоких степеней энтропии, можно выделить больше адресов областей памяти как стеки и кучи. Из-за этого сложнее подобрать расположение определенной области памяти.  
  
 Когда включен этот параметр, целевой исполняемый файл и модули, на которых она зависит необходимо обработать значения указателя, размер которых превышает 4 гигабайта (ГБ), когда эти модули выполняются как 64-разрядные процессы.  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
