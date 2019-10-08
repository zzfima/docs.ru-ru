---
title: -highentropyva (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 58026ff84f1ff501bf767adebcfc01f7de5bf4a4
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005581"
---
# <a name="-highentropyva-visual-basic"></a>-highentropyva (Visual Basic)
Указывает, является ли 64-разрядный исполняемый файл или исполняемый файл, помеченный параметром компилятора [/Platform: anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) , поддержкой случайного распределения макета адресного пространства (ASLR).  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
 `+` &#124; `-`  
 Необязательный параметр. Параметр отключен по умолчанию или при указании `-highentropyva-`. Параметр включен, если задано значение `-highentropyva` или `-highentropyva+`.  
  
## <a name="remarks"></a>Примечания  
 Если указан этот параметр, совместимые версии ядра Windows могут использовать более высокие уровни энтропии, когда ядро случайным образом разметка адресного пространства процесса в рамках ASLR. Если ядро использует более высокие степени энтропии, то для областей памяти, таких как стеки и кучи, можно выделить большее количество адресов. Из-за этого сложнее подобрать расположение определенной области памяти.  
  
 Если параметр включен, целевой исполняемый файл и все модули, от которых он зависит, должны иметь возможность обрабатывать значения указателя, превышающие 4 гигабайта (ГБ), если эти модули работают как 64-разрядные процессы.  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
