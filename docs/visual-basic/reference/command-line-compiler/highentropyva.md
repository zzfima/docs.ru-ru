---
title: /highentropyva (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 55568808bb94f98ce7a20016fc5a2a0a2ef23a38
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="highentropyva-visual-basic"></a>/highentropyva (Visual Basic)
Указывает, 64-разрядный исполняемый файл или исполняемый файл, помеченный атрибутом [/Platform: anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) параметр компилятора поддерживает технологию Address Space макета Randomization (ASLR) с высокой энтропией.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
 `+` &#124; `-`  
 Необязательно. Параметр отключен по умолчанию или при указании `/highentropyva-`. Параметр — Если указать `/highentropyva` или `/highentropyva+`.  
  
## <a name="remarks"></a>Примечания  
 Если этот параметр указан, совместимые версии ядра Windows можно использовать более высокие степени энтропии при ядра случайный выбор из своего структуры адресного пространства процесса в рамках ASLR. Если ядро использует более высоких степеней энтропии, можно выделить больше адресов областей памяти как стеки и кучи. Из-за этого сложнее подобрать расположение определенной области памяти.  
  
 Когда включен этот параметр, целевой исполняемый файл и модули, на которых она зависит необходимо обработать значения указателя, размер которых превышает 4 гигабайта (ГБ), когда эти модули выполняются как 64-разрядные процессы.  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
