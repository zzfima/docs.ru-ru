---
title: exceptionSwallowedOnCallFromCom MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, informational
- informational messages
- managed debugging assistants (MDAs), exceptions
- exception handling, managed debugging assistants
- MDAs (managed debugging assistants), exceptions
- ExceptionSwallowedOnCallFromCOM MDA
ms.assetid: 55d6ab12-f251-4aab-aa64-aacbe9d9f974
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d68e3f8659b0d5fe212c58443fe9a8b42f9cef89
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="exceptionswallowedoncallfromcom-mda"></a>exceptionSwallowedOnCallFromCom MDA
Помощник отладки управляемого кода (MDA) `exceptionSwallowedOnCallFromCOM` активируется при возникновении исключения из кода среды CLR, вызываемого из COM посредством метода, который не имеет неуправляемого типа возвращаемого значения HRESULT.  
  
## <a name="symptoms"></a>Признаки  
 Вызов управляемого компонента из COM возвращает значение FALSE или 0. Кроме того, если метод имеет тип возвращаемого значения void, указание на возникновение исключения во время выполнения метода может отсутствовать. В этом случае исключение будет перехвачено без предупреждения и возвращено вызывающему объекту COM.  
  
## <a name="cause"></a>Причина  
 Возникло исключение, однако не существует приемлемого способа сообщить об этом.  
  
## <a name="resolution"></a>Решение  
 Сведения приведены исключительно для справки и необязательно указывают на наличие ошибки.  
  
## <a name="effect-on-the-runtime"></a>Влияние на среду выполнения  
 Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR. Он только выводит данные об исключениях, перехваченных без предупреждения.  
  
## <a name="output"></a>Вывод  
 Информационное сообщение с именем метода, именем типа и указанием на исключение.  
  
## <a name="configuration"></a>Конфигурация  
  
```xml  
<mdaConfig>  
  <assistants>  
    <exceptionSwallowedOnCallFromCom />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Диагностика ошибок посредством помощников по отладке управляемого кода](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [Маршалинг взаимодействия](../../../docs/framework/interop/interop-marshaling.md)
