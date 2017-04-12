---
title: "/ highentropyva (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 34987930b3afd6d95d12190172a5a5e512106f8a
ms.lasthandoff: 03/13/2017

---
# <a name="highentropyva-visual-basic"></a>/highentropyva (Visual Basic)
Указывает ли 64-битный исполняемый файл или исполняемый файл, помеченный атрибутом [/Platform: anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) параметр компилятора поддерживает высокую энтропию случайный выбор макета адресного пространства (ASLR).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
 `+` &#124; `-`  
 Необязательный. Параметр отключен по умолчанию или если указать `/highentropyva-`. Параметр — Если указать `/highentropyva` или `/highentropyva+`.  
  
## <a name="remarks"></a>Примечания  
 Если этот параметр задан, совместимым версиям ядра Windows можно использовать более высокие степени энтропии при ядра случайный выбор из своего структуры адресного пространства процесса в рамках ASLR. Если ядро использует более высокие степени энтропии, можно выделить больше адресов, областям памяти, как стеки и кучи. Из-за этого сложнее подобрать расположение определенной области памяти.  
  
 Когда параметр включен, целевой исполняемый файл и модули, на которых она зависит необходимо обработать значения указателя, размер которых превышает 4 гигабайта (ГБ) при выполнении этих модулей как 64-разрядные процессы.  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
