---
title: Помощник по отладке управляемого кода invalidMemberDeclaration
ms.date: 03/30/2017
helpviewer_keywords:
- invalid member declaration
- InvalidMemberDeclaration MDA
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c276df65497a0d8cafea80959b8193790c19ebba
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54667353"
---
# <a name="invalidmemberdeclaration-mda"></a>Помощник по отладке управляемого кода invalidMemberDeclaration
Помощник по отладке (MDA) управляемого кода `invalidMemberDeclaration` активируется для сообщения об ошибке, которая возникает при определении способа маршалинга параметров члена, вызываемого из COM.  
  
## <a name="symptoms"></a>Признаки  
 Значение HRESULT, свидетельствующее об ошибке, возвращается в COM без вызова управляемого метода.  
  
## <a name="cause"></a>Причина  
 Наиболее вероятная причина — несовместимый атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> в одном из параметров.  
  
## <a name="resolution"></a>Решение  
 Укажите допустимые атрибуты <xref:System.Runtime.InteropServices.MarshalAsAttribute> в параметрах.  
  
## <a name="effect-on-the-runtime"></a>Влияние на среду выполнения  
 Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.  
  
## <a name="output"></a>Вывод  
 Информационное сообщение с именем члена, именем типа и сообщением об ошибке.  
  
## <a name="configuration"></a>Конфигурация  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>См. также
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Диагностика ошибок посредством помощников по отладке управляемого кода](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Маршалинг взаимодействия](../../../docs/framework/interop/interop-marshaling.md)
