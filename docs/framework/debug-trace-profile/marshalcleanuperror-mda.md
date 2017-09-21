---
title: marshalCleanupError MDA
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
- cleanup operations
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
- marshaling cleanup error
- MarshalCleanupError MDA
- memory, cleanup errors
ms.assetid: 2f5d9e7c-ae51-4155-a435-54347aa1f091
caps.latest.revision: 12
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ad81faae235513b5d7c6665c3598a443711a0d6d
ms.contentlocale: ru-ru
ms.lasthandoff: 08/21/2017

---
# <a name="marshalcleanuperror-mda"></a>marshalCleanupError MDA
Помощник отладки управляемого кода (MDA) `marshalCleanupError` активируется, когда при попытке очистить временные структуры и память, используемые для маршалинга типов данных между границами машинного и управляемого кода, в среде CLR возникает ошибка.  
  
## <a name="symptoms"></a>Признаки  
 При переходах между машинным и управляемым кодом возникает утечка памяти, не восстанавливается состояние среды, например культура потока, либо возникают ошибки при очистке <xref:System.Runtime.InteropServices.SafeHandle>.  
  
## <a name="cause"></a>Причина  
 Во время очистки временных структур возникла непредвиденная ошибка.  
  
## <a name="resolution"></a>Решение  
 Проверьте все реализации деструктора <xref:System.Runtime.InteropServices.SafeHandle>, метода завершения и особого упаковщика на наличие ошибок.  
  
## <a name="effect-on-the-runtime"></a>Влияние на среду выполнения  
 Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.  
  
## <a name="output"></a>Вывод  
 Сообщение с указанием операции, завершившейся со сбоем во время очистки.  
  
## <a name="configuration"></a>Конфигурация  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshalCleanupError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Диагностика ошибок посредством помощников по отладке управляемого кода](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Маршалинг взаимодействия](../../../docs/framework/interop/interop-marshaling.md)

