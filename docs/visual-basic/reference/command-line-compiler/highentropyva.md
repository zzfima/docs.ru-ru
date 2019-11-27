---
title: -highentropyva
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 7934dcaada4675bf687624bef5ed1ea25e842832
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344241"
---
# <a name="-highentropyva-visual-basic"></a>-highentropyva (Visual Basic)
Указывает, является ли 64-разрядный исполняемый файл или исполняемый файл, помеченный параметром компилятора [-Platform: anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) , поддержкой случайного расположения макета адресного пространства (ASLR) с высокой энтропией.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
 `+` &#124; `-`  
 Необязательный элемент. Параметр отключен по умолчанию или при указании `-highentropyva-`. Параметр включен, если вы указываете `-highentropyva` или `-highentropyva+`.  
  
## <a name="remarks"></a>Примечания  
 Если указан этот параметр, совместимые версии ядра Windows могут использовать более высокие уровни энтропии, когда ядро случайным образом разметка адресного пространства процесса в рамках ASLR. Если ядро использует более высокие степени энтропии, то для областей памяти, таких как стеки и кучи, можно выделить большее количество адресов. Из-за этого сложнее подобрать расположение определенной области памяти.  
  
 Если параметр включен, целевой исполняемый файл и все модули, от которых он зависит, должны иметь возможность обрабатывать значения указателя, превышающие 4 гигабайта (ГБ), если эти модули работают как 64-разрядные процессы.  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
