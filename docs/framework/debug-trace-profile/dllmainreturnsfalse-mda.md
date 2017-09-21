---
title: "Помощник по отладке управляемого кода dllMainReturnsFalse"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- managed debugging assistants (MDAs), DllMain returns false
- DllMainReturnsFalse MDA
- DllMain function
- MDAs (managed debugging assistants), DllMain returns false
ms.assetid: e2abdd04-f571-4b97-8c16-2221b8588429
caps.latest.revision: 12
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: be2fcbd608e15ecc9b0b17529558999d0dfa85c9
ms.contentlocale: ru-ru
ms.lasthandoff: 08/21/2017

---
# <a name="dllmainreturnsfalse-mda"></a>Помощник по отладке управляемого кода dllMainReturnsFalse
Помощник по отладке управляемого кода `dllMainReturnsFalse` (MDA) активируется в том случае, если управляемая функция `DllMain` в пользовательской сборке вызывается с причиной DLL_PROCESS_ATTACH и возвращает значение FALSE.  
  
## <a name="symptoms"></a>Признаки  
 Функция `DllMain` возвращает значение FALSE, свидетельствующее о сбое при ее выполнении. Это может привести к возникновению неопределенных проблем, поскольку функции `DllMain` обычно содержат важный код инициализации.  
  
## <a name="cause"></a>Причина  
 Функция `DllMain` вызывается с причиной DLL_PROCESS_ATTACH для инициализации библиотеки DLL при загрузке. Если она возвращает значение FALSE, значит инициализация библиотеки DLL завершилась сбоем.  
  
## <a name="resolution"></a>Решение  
 Проанализируйте код функции `DllMain` для указанной библиотеки DLL и определите причину сбоя при инициализации.  
  
## <a name="effect-on-the-runtime"></a>Влияние на среду выполнения  
 Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR. Он только выводит данные о возвращаемом значении для `DllMain`.  
  
## <a name="output"></a>Вывод  
 Сообщение, указывающее, что функция `DllMain` была вызвана с причиной DLL_PROCESS_ATTACH и вернула значение FALSE. Обратите внимание, что этот помощник по отладке кода вызывается только в том случае, если в управляемом коде реализована функция `DllMain`.  
  
## <a name="configuration"></a>Конфигурация  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dllMainReturnsFalse />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>См. также  
 [Диагностика ошибок посредством помощников по отладке управляемого кода](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)

